# Rocket.Chat Theme - Brei0x

Dark graphite theme for Rocket.Chat: neutral grays, a single blue accent, square corners
and Darcula-style code blocks.

<p align="center">
  <a href="https://github.com/brei0x/rocketchat-dark-theme/actions/workflows/ci.yml"><img src="https://github.com/brei0x/rocketchat-dark-theme/actions/workflows/ci.yml/badge.svg?branch=main" alt="CI"></a>
  <a href="https://github.com/brei0x/rocketchat-dark-theme/releases/latest"><img src="https://img.shields.io/github/v/release/brei0x/rocketchat-dark-theme?sort=semver" alt="Latest release"></a>
  <a href="https://github.com/brei0x/rocketchat-dark-theme/blob/main/LICENSE"><img src="https://img.shields.io/github/license/brei0x/rocketchat-dark-theme" alt="License"></a>
</p>

---

![Rocket.Chat Theme - Brei0x](docs/screenshot.jpg "Rocket.Chat Theme - Brei0x")

## Prerequisites

- Rocket.Chat **9.0** or later, web client or desktop app. Built and checked on 9.0.0.
- An administrator account (permission `edit-privileged-setting`) to change the Custom CSS setting.

The theme is a single stylesheet that overrides Rocket.Chat's Fuselage color tokens. It does not
apply to the iOS and Android apps, which ignore Custom CSS.

## Install

1. Copy the content of [`brei0x.css`](brei0x.css).
2. Paste it in **Administration > Workspace > Settings > Layout > Custom CSS**, then save.
3. Reload the page.

Upgrade, removal and troubleshooting: [docs/SETUP.md](docs/SETUP.md).
Changes between versions: [releases](https://github.com/brei0x/rocketchat-dark-theme/releases).
