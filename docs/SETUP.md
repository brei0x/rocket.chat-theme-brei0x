# Setup

## Compatibility

| Rocket.Chat | Theme |
| --- | --- |
| 9.0 and later (Fuselage UI) | `brei0x.css`, version 2.x |
| 0.x (legacy Blaze UI, 2017) | version 1.x, see git history. Does not work on any current release. |

Current releases no longer have the **Layout > Colors** settings the 1.x theme relied on, and the React UI
dropped every legacy selector it targeted (`.side-nav`, `.message-form`, `.page-settings`...).
Version 2.x only uses the `--rcx-color-*` tokens and the `.hljs` classes.

## Install

1. Sign in with an administrator account.
2. Open **Administration > Workspace > Settings > Layout**. The **Customize** button on the
   workspace home page leads to the same screen.
3. Expand **Custom CSS** and paste the full content of [`brei0x.css`](../brei0x.css), replacing any
   previous Brei0x or Blackbort CSS.
4. Save, then reload the page. Desktop app users reload with `Ctrl+R` / `Cmd+R`.

Rocket.Chat serves the setting at `/theme.css`. To check it was saved:

```bash
curl -s https://chat.example.com/theme.css | head -n 3
```

## How it works

Rocket.Chat injects three palettes of `--rcx-color-*` variables, one per area: `:root`,
`.rcx-content--main, .rcx-tile` and `.rcx-sidebar--main, .rcx-sidebar-rail, .rcx-sidepanel, .rcx-navbar`.
The theme redefines every token on the same selectors with `!important`, so it wins over the theme each
user picks in **My Account > Accessibility & appearance**:

- Light, Dark and "Match system" all render as Brei0x.
- **High contrast is overridden too.** Users who rely on it lose it while the theme is active.

Text colors meet WCAG AA (4.5:1) on their surfaces. Color changes can still break contrast in
parts of the UI the tokens do not cover, so check a test workspace before production.

## Upgrade Rocket.Chat

Token names can change between major releases. After a major upgrade, list the tokens the
client actually ships and compare them with `brei0x.css`. In the browser console, on any room:

```js
[...document.getElementById('app-layout-palette').sheet.cssRules[0].style].filter((p) => p.startsWith('--rcx-color-')).sort().join('\n')
```

A token missing from `brei0x.css` falls back to the user's own theme. A token in `brei0x.css`
that no longer exists is ignored.

## Remove

Clear the **Custom CSS** field, save and reload. Users get their own theme back.

## Release a version

Versions follow [SemVer](https://semver.org/): a token or selector change that needs a newer
Rocket.Chat is a major, a new styled area a minor, a color fix a patch.

1. Merge the change into `main` through a pull request (squash).
2. Set the version in the header comment of `brei0x.css` and add a dated section to `CHANGELOG.md`
   with its compare link, in the same pull request.
3. Tag the merge commit on `main` and publish the release with the changelog section as notes:

```bash
git switch main && git pull
```

```bash
git tag -s v2.0.1 -m "v2.0.1"
```

```bash
git push origin v2.0.1
```

```bash
gh release create v2.0.1 --title "v2.0.1" --notes-file notes.md
```

## Troubleshooting

- **No change after saving**: reload the page. Browser caches can keep the old `/theme.css`;
  force-reload with `Ctrl+Shift+R` / `Cmd+Shift+R`.
- **Theme only partly applied**: the field holds an invalid rule before the theme, or a truncated
  paste. Paste the file again, alone.
- **Mobile app unchanged**: expected, the native apps ignore Custom CSS.
