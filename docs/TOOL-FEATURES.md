# Tool Features (Full Breakdown)

Effective date: 2026-02-27

This list covers end-user-visible tools and what each tool does in the app.

## Common capabilities (most tools)

- Uses token + active service from `Settings`
- Pull from Nitrado and/or load local files (tool dependent)
- Guided editing UI with field-level controls
- Copy/download export options (tool dependent)
- Push/upload back to Nitrado (tool dependent)

## Dashboard

File: [tools/index.html](tools/index.html)

- Launch cards for all user-visible tools
- Quick Reference links
- Drag-and-drop card ordering (saved locally)

## Settings

File: [tools/settings.html](tools/settings.html)

- Nitrado token management (add/select/store local)
- Active service loading + selection
- Platform selection (Auto/Xbox/PlayStation)
- Developer Debug Mode toggle
- FTP fallback summary (auto-derived per service)
- UI style preset selection
- Nitrado Controller strategy selection (`auto`/`api`/`ftp`) + API/FTP checks
- App updater actions (check/download/install)
- Account & Device Linking:
  - Create account
  - Sign in / refresh / sign out
  - Load sessions
  - Create link code / complete device link
  - Load linked devices

## Nitrado Customer Settings

File: [tools/dayz-nitrado-customer-settings.html](tools/dayz-nitrado-customer-settings.html)

- Fetch defaults and current panel settings
- Quick toggle writes
- Single key write by category/key/value
- Bulk apply from JSON input
- Start/stop/restart server actions

## File Browser Editor

File: [tools/dayz-file-browser-editor.html](tools/dayz-file-browser-editor.html)

- Browse server file paths
- Open/edit supported files in text editor
- Load local file into editor
- Upload edited content to Nitrado
- Download editor content locally

## RPT Error Panel

File: [tools/dayz-rpt-error-panel.html](tools/dayz-rpt-error-panel.html)

- Analyze pasted/local `.rpt/.log/.txt`
- Optionally fetch newest RPT from Nitrado
- Search + severity filters
- Pattern-based summary for common DayZ issues

## Weather Configurator

File: [tools/dayz-weather-configurator.html](tools/dayz-weather-configurator.html)

- Load `cfgweather.xml` (Nitrado/local)
- Edit weather systems (overcast/fog/rain/wind/storm/snowfall)
- Preview generated XML
- Copy/download/upload edited XML

## Server Globals Configurator

File: [tools/dayz-globals-configurator.html](tools/dayz-globals-configurator.html)

- Load `globals.xml` (Nitrado/local)
- Edit economy and lifecycle globals
- Spawn-control and timer settings
- Copy/download/upload edited XML

## Server Build Presets

File: [tools/dayz-server-build-presets.html](tools/dayz-server-build-presets.html)

- Multi-file profile management (new/duplicate/delete)
- Pull current build files from Nitrado into profile
- Push profile files back to Nitrado
- Edit profile content in raw JSON editors
- Import/export profiles as JSON

## CfgGameplay Presets

File: [tools/dayz-cfggameplay-presets.html](tools/dayz-cfggameplay-presets.html)

- Profile management for mission-root `cfggameplay.json`
- Pull from Nitrado / push to Nitrado
- Validate JSON content
- Import/export preset JSON

## Globals Presets

File: [tools/dayz-globals-presets.html](tools/dayz-globals-presets.html)

- Profile management for `db/globals.xml`
- Pull from Nitrado / push to Nitrado
- Validate XML content
- Import/export preset JSON

## Messages Presets

File: [tools/dayz-messages-presets.html](tools/dayz-messages-presets.html)

- Profile management for `db/messages.xml`
- Pull from Nitrado / push to Nitrado
- Message builder for new `<message>` entries
- Validate XML content
- Import/export XML

## CfgGameplay Configurator

File: [tools/dayz-cfggameplay-configurator.html](tools/dayz-cfggameplay-configurator.html)

- Load `cfggameplay.json` (Nitrado/local)
- Edit gameplay systems (stamina/shock/movement/vehicles/base building/UI/map)
- Preview/copy/download/upload JSON

## Spawn Point Editor

File: [tools/DayZ_Spawn_Visualizer.html](tools/DayZ_Spawn_Visualizer.html)

- Load `cfgplayerspawnpoints.xml` (Nitrado/local)
- Interactive map (pan/zoom/drag spawn points)
- Section filtering (Fresh/Hop/Travel)
- Add/remove/update spawn points
- Copy/download/upload XML

## Event Spawns Editor

File: [tools/dayz-cfgeventspawns-editor.html](tools/dayz-cfgeventspawns-editor.html)

- Load `cfgeventspawns.xml` (Nitrado/local)
- Event list + search/filter
- Edit/add/remove event positions
- Interactive map point dragging
- Copy/download/upload XML

## Territories Editor

File: [tools/dayz-territories-editor.html](tools/dayz-territories-editor.html)

- Load mission `*_territories.xml` files (Nitrado/local)
- Territory list + search
- Edit territory + zone properties
- Interactive map editing
- Copy/download/upload XML

## Underground Triggers Editor

File: [tools/dayz-underground-triggers-editor.html](tools/dayz-underground-triggers-editor.html)

- Load mission-root `cfgundergroundtriggers.json` (Nitrado/local)
- Trigger list (add/delete/select/edit)
- Breadcrumb list (add/delete/select/edit)
- Map-based trigger box move/resize and breadcrumb dragging
- Utilities (scaffold hallway, breadcrumb helpers, format/copy JSON)
- Push edited JSON to Nitrado

## MapGroupProto Editor

File: [tools/dayz-mapgroupproto-editor.html](tools/dayz-mapgroupproto-editor.html)

- Load `mapgroupproto.xml` (Nitrado/local)
- Group search/list and property editing
- Container list editing (loot caps/filters)
- Normalize `lootmax` helper
- Copy/download/upload XML

## Event Groups Editor

File: [tools/dayz-cfgeventgroups-editor.html](tools/dayz-cfgeventgroups-editor.html)

- Load `cfgeventgroups.xml` (Nitrado/local)
- Optional `mapgroupproto.xml` context load
- Group + children editing
- Validation checks
- Copy/download/upload XML

## Spawnable Types Editor

File: [tools/dayz-spawnabletypes-editor.html](tools/dayz-spawnabletypes-editor.html)

- Load `cfgspawnabletypes.xml` (Nitrado/local)
- Type search/list and editing
- Edit attachments/cargo/damage ranges
- Types/limits integration helpers
- Validation + copy/download/upload XML

## Types.xml Editor

File: [tools/dayz-types-editor.html](tools/dayz-types-editor.html)

- Load `types.xml` (Nitrado/local)
- Search/filter type entries
- Edit economy values, flags, categories, usage, tiers
- Limits library integration
- Validation + copy/download/upload XML

## Loadout Builder

File: [tools/dayz-loadout-builder.html](tools/dayz-loadout-builder.html)

- Build character loadout preset JSON
- Add/remove survivor type restrictions
- Add/remove body slots and item entries
- Load `types.xml` (Nitrado/local) for item autocomplete
- Copy/download generated JSON
- Upload generated loadout JSON to mission `custom/` on Nitrado

## CfgLimitsDefinition Editor

File: [tools/dayz-cfglimitsdefinition-editor.html](tools/dayz-cfglimitsdefinition-editor.html)

- Load `cfglimitsdefinition.xml` (Nitrado/local)
- Edit shared list primitives (categories/tags/usage/value)
- XML preview and copy
- Download/upload edited XML

## Documentation

File: [tools/documentation.html](tools/documentation.html)

- In-app documentation and workflow notes
- Setup + tool usage reference sections

## Legal & Privacy

File: [tools/legal.html](tools/legal.html)

- In-app legal/privacy transparency page
- Copyright, release integrity, third-party notices
- Affiliation disclaimer
