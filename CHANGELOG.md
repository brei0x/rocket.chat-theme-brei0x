# Changelog

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). Versioning: [SemVer](https://semver.org/).

## [Unreleased]

### Changed

- Renamed the repository to `rocketchat-dark-theme` so it is easier to find.

## [2.0.0] - 2026-11-16

### Changed

- Renamed the theme from Blackbort to Brei0x, and the repository to `rocket.chat-theme-brei0x`.
- Rewrote the theme for Rocket.Chat 9.0 on the Fuselage `--rcx-color-*` tokens. The CSS now lives
  in `brei0x.css` instead of the README.
- Raised text and syntax colors to WCAG AA: default text `#888889` to `#b4b4b5`, Darcula string,
  keyword, number and comment colors lightened.
- Status bullets and radio buttons keep their round shape.

### Removed

- The **Layout > Colors** values, a settings section that no longer exists in Rocket.Chat.
- Rules for legacy selectors gone with the React UI (`.side-nav`, `.message-form`, `.page-settings`,
  `.flex-tab`, `.message .reactions`...).

## [1.2.0] - 2017-05-18

### Added

- Focus border color for inputs, selects and text areas in the side panel (`.flex-tab`).

## [1.1.0] - 2017-03-29

### Added

- Darcula colors for highlight.js code blocks.

## [1.0.0] - 2017-03-29

### Added

- First release for the legacy Rocket.Chat 0.x UI: **Layout > Colors** values and Custom CSS.

[Unreleased]: https://github.com/brei0x/rocketchat-dark-theme/compare/v2.0.0...HEAD
[2.0.0]: https://github.com/brei0x/rocketchat-dark-theme/compare/v1.2.0...v2.0.0
[1.2.0]: https://github.com/brei0x/rocketchat-dark-theme/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/brei0x/rocketchat-dark-theme/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/brei0x/rocketchat-dark-theme/releases/tag/v1.0.0
