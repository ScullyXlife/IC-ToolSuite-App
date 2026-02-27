# Security & Data Handling (Transparency)

Effective date: 2026-02-20

This document summarizes how IC ToolSuite handles data and security at a high level.

## High-level architecture

- IC ToolSuite is a desktop app built with Tauri.
- The UI is a set of local tool pages (HTML/JS/CSS) bundled into the app.
- Optional account/session features use a project-operated auth service.

## What the app stores (local only)

IC ToolSuite stores app settings on your device (local storage/app data), including tokens/settings you choose to save.

How to remove local data:

- Remove saved tokens/settings in the Settings tool.
- Or clear the app’s local storage/app data on your device.

## What the app sends over the network

The app only makes requests required for features you use:

- Nitrado operations you initiate
- Update/release metadata checks
- Optional account actions (register/sign-in/session/device linking)

IC ToolSuite does not send analytics/telemetry.

## What the app does NOT do

- No analytics/telemetry
- No advertising identifiers
- No hidden background data collection
- No reading browser history or browser saved passwords
- No keystroke logging

## Safety protocols in the tools

Designed behaviors to reduce risk:

- User-initiated network actions
- Explicit file targets selected by you
- Validation hints where available

## Release integrity (trust signals)

Official releases publish:

- Signature files (`*.sig`) for release assets
- SHA-256 checksums (`SHA256SUMS.txt`) so you can verify the exact bytes you downloaded

## Tool scope (what each tool does)

Feature list:

- [TOOL-FEATURES.md](TOOL-FEATURES.md)

## Notes on licensing

- Official releases are governed by the Binary EULA in [LICENSE](LICENSE).
- The project includes third-party dependencies (including open-source components); see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
