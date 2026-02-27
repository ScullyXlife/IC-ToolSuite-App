# Iron Chronicle Tool Suite

**The Definitive Console DayZ Admin Toolkit (Nitrado-Focused)**

Cross-platform (Windows + Linux) desktop toolkit built by an active DayZ server owner to eliminate manual XML headaches for console admins.

Closed-source for now and built for the DayZ console admin community.

Not affiliated with Bohemia Interactive or Nitrado.

## Why This Exists

Console DayZ admins are forced to:

- Manually edit XML
- Balance the CE blindly
- Guess at RPT errors
- Fight unreliable file uploads
- Work around Nitrado quirks

Iron Chronicle Tool Suite was built to fix that.

## Core Capabilities (High-Level)

- Full Nitrado API integration (service-scoped long-life token)
- Guided XML & JSON editors (guardrails + export + upload)
- Drag-and-drop map visualizers (spawn points, event spawns, territories)
- CE balancing surfaces (types, limits library, globals, spawnable types)
- RPT log analysis (common pattern detection)
- Upload strategy controller (API + FTP fallback)
- Cross-tool Limits library integration (shared categories/tags/usage/value)
- Automatic updates (in-app updater)

Full details live here:

- Full Feature Breakdown: [TOOL-FEATURES.md](TOOL-FEATURES.md)

## What Makes This Different

- Built specifically for console servers
- Designed around Nitrado limitations (and the failure modes console admins actually hit)
- Real-world server-tested workflows
- Guardrails that help prevent economy-breaking mistakes
- Structured validation where possible (schemas / known-safe constraints)
- Designed by someone who runs servers, not just edits files

## Installation

This repo contains the End-user installers.

### Download

Get the latest installers from the IC-ToolSuite-App releases:

https://github.com/ScullyXlife/IC-ToolSuite-App/releases

### Windows install

1. Download one of these files:
   - `IC.ToolSuite_*_x64-setup.exe` (NSIS)
   - `IC.ToolSuite_*_x64_en-US.msi` (MSI)
2. Run the installer and follow the prompts.
3. If Windows SmartScreen warns you, choose "More info" then "Run anyway."

### Linux install (deb)

1. Download `IC ToolSuite_*_amd64.deb` from the releases page.
2. Install it with:

```bash
sudo dpkg -i "IC ToolSuite_*_amd64.deb"
sudo apt -f install -y
```

## Updates

Use Settings → App Updates inside the app to check and install updates.

## Release Automation (Maintainers)

Release packaging and publishing are handled by GitHub Actions for maintainers.

- Unified release workflow (desktop + mobile): [.github/workflows/release.yml](.github/workflows/release.yml)
- Mobile preflight validation: [.github/workflows/mobile-preflight.yml](.github/workflows/mobile-preflight.yml)
- Maintainer setup checklist: internal maintainer docs (private)

This is maintainer release infrastructure, not an end-user/local build path.

## Nitrado Token Setup (Required)

IC Tool Suite only needs a **single long-life Nitrado API token**.

- For most operations you do **not** need FTP host/user/password in IC Tool Suite.
- If Nitrado `file_server/upload` is unreliable for your service (common on some console servers), IC Tool Suite can use **FTP upload fallback**. Configure it in Settings → Nitrado Controller.
- Add your token in Settings → Nitrado Tokens, then click Load Services and select your server.

On the Nitrado long-life token page, enable this scope:

- **service**

That is the scope IC Tool Suite uses for service listing and file-server operations.

You can leave these unchecked unless you need them for other tools/scripts:

- `rootserver`
- `ssh_keys`
- `service_order`
- `user_edit`
- `user_info`

With `service` enabled, the token covers these API paths used by the app:

- `/services`
- `/services/{id}/gameservers/file_server`
- `/services/{id}/gameservers/file_server/list`
- `/services/{id}/gameservers/file_server/download`
- `/services/{id}/gameservers/file_server/upload`

## Nitrado Controller (Recommended)

In Settings → Nitrado Controller, choose an upload strategy:

- **Auto (default):** API upload first, then FTP fallback if upload fails
- **API:** force API upload
- **FTP:** force FTP upload

## Roadmap

Roadmap and long-term direction:

- [ROADMAP.md](ROADMAP.md)

## Support

Discord support: https://discord.gg/nPugvHKhsk

## Security + Privacy Transparency

This app is designed to work without a custom backend.

What it accesses:

- Nitrado API + Nitrado file server endpoints (only when you connect a token and initiate actions)
- GitHub release metadata (updater checks, depending on build/workflow)

What it stores (local only):

- Your app settings and any tokens/FTP settings you choose to save

What it does NOT do:

- No analytics/telemetry
- No ads
- No hidden remote server collecting data

Details: see [PRIVACY.md](PRIVACY.md).

More detail (architecture + data handling): see [SECURITY.md](SECURITY.md).

## Donations (Optional)

If IC Tool Suite saves you time, donations help fund development, testing, and release costs (no paywalls):

https://buy.stripe.com/9B6dRbbrp0Ly1y58aRgYU05

## License + Disclaimer

- License: Binary EULA for official releases (see [LICENSE](LICENSE))
- Not affiliated with Bohemia Interactive or Nitrado
- No paywalls, no API resale (optional donations are welcome)
- Privacy: no analytics/telemetry (see [PRIVACY.md](PRIVACY.md))

## Release Integrity

- Release builds are signed.
- Release assets include SHA-256 checksum hashes.
