# Security & Data Handling (Transparency)

Effective date: 2026-02-20

This document explains how IC ToolSuite is packaged, what it accesses, what it stores, and what safety controls exist to keep user information local.

## High-level architecture

- IC ToolSuite is a desktop app built with Tauri.
- The UI is a set of local tool pages (HTML/JS/CSS) bundled into the app.
- There is no project-operated backend server.

In practical terms: the app runs locally, loads local tool pages, and only talks to third-party services when you explicitly use features that require them.

## What the app stores (local only)

IC ToolSuite stores settings on your device (webview local storage / app data). This can include:

- Nitrado API token(s) you enter (long-life token)
- Selected active Nitrado service id
- Platform selection, editor preferences, and tool settings
- Optional FTP host/user/password (only if you configure FTP fallback)

This data stays on your device unless you choose to upload a server file.

How to remove local data:

- Remove saved tokens/settings in the Settings tool.
- Or clear the app’s local storage/app data on your device.

## What the app sends over the network

The app only makes network requests to:

- Nitrado services you connect to (API calls and file upload/download actions you initiate)
- GitHub release endpoints used by the updater (release metadata), depending on build/workflow

IC ToolSuite does not send analytics/telemetry.

## What the app does NOT do

- No analytics/telemetry
- No advertising identifiers
- No background “phone home” server
- No reading browser history or browser saved passwords
- No keystroke logging

## Safety protocols in the tools

Designed behaviors to reduce risk:

- User-initiated network actions: download/upload calls occur only when you click a tool action.
- Explicit file targets: tools operate on specific filenames/paths you select (e.g. `types.xml`, `globals.xml`, `cfgweather.xml`).
- Validation hints (where available): some tools can warn about invalid structure, missing types, or risky edits.
- Small-change workflows: documentation encourages backups, diffs, and staged rollout.

## Release integrity (trust signals)

Official releases publish:

- Signature files (`*.sig`) for release assets
- SHA-256 checksums (`SHA256SUMS.txt`) so you can verify the exact bytes you downloaded

## Tool scope (what each tool does)

A complete per-tool feature list is maintained in:

- [TOOL-FEATURES.md](TOOL-FEATURES.md)
- [docs/tool-features.md](docs/tool-features.md)

## Notes on licensing

- Official releases are governed by the Binary EULA in [LICENSE](LICENSE).
- The project includes third-party dependencies (including open-source components); see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
