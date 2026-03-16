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
- Dedicated Messages Editor for direct `messages.xml` editing with quick insert helpers
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

This repo contains the app project and tool pages. End-user installers are published in a separate releases repo.

### Download

Get the latest installers from the IC-ToolSuite-App releases:

https://github.com/ScullyXlife/IC-ToolSuite-App/releases

Desktop stable and Android beta artifacts are both published from the same releases feed.

### Windows install

1. Download one of these files:
   - `IC.ToolSuite_*_x64_en-US.msi` (Full)
   - `*_lite-map-sideload.msi` (Lite flavor, smaller installer)
2. Run the installer and follow the prompts.
3. If Windows SmartScreen warns you, choose "More info" then "Run anyway."

### Linux install (deb)

1. Download `IC ToolSuite_*_amd64.deb` from the releases page.
   - Lite flavor uses `*_lite-map-sideload.deb` and downloads tiled map packs on demand.
2. Install it with:

```bash
sudo dpkg -i "IC ToolSuite_*_amd64.deb"
sudo apt -f install -y
```

## Updates

Use Settings → App Updates inside the app to check and install updates.

## Build Workflows (Full + Lite)

Default/full workflows are unchanged and continue bundling map assets in the app package.

- Full dev: `npm run dev`
- Full build: `npm run build`
- Full signed build: `npm run build:signed`

Lite workflows exclude bundled map tiles from `dist/` and use on-demand map pack install in map tools.

- Lite dev: `npm run dev:lite`
- Lite build: `npm run build:lite`
- Lite signed build: `npm run build:signed:lite`

Map pack release helpers:

- Package map zips + update map manifest checksums/urls: `npm run maps:package`
- Package tools bundle (lite variant): `npm run tools:package:lite`

## Nitrado Token Setup (Required)

IC Tool Suite only needs a **single long-life Nitrado API token**.

- For most operations you do **not** need FTP host/user/password in IC Tool Suite.
- If Nitrado `file_server/upload` is unreliable for your service (common on some console servers), IC Tool Suite can use **FTP upload fallback**. Configure it in Settings → Nitrado Controller.
- Add your token in Settings → Nitrado Tokens, then click Load Services and select your server.
- In multi-service or multi-token setups, the app remembers token-to-service bindings to keep requests pinned to the correct stored token per service.

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

## Support

Discord support: https://discord.gg/nPugvHKhsk

## Privacy + Security

- Privacy policy: [PRIVACY.md](PRIVACY.md)
- Security/data handling: [SECURITY.md](SECURITY.md)

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
