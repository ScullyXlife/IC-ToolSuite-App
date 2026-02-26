# Tool Features List

[Home](./index.md) · [Tool Features](./tool-features.md) · [Support Discord](https://discord.gg/nPugvHKhsk)

Effective date: 2026-02-17

This document summarizes the user-facing features of every tool page in the tools directory.

## Common capabilities (most tools)

- Nitrado integration via the shared proxy (token + active service selected in Settings)
- Load configuration from Nitrado and/or from a local file
- Edit in a guided UI (lists, forms, guardrails)
- Export results (copy to clipboard and/or download)
- Optional validation hints (when a schema/validator exists)
- Optional Nitrado debug log panel (shown when Developer Debug Mode is enabled)

## Tool-by-tool features

### Dashboard

File: [tools/index.html](../tools/index.html)

- Tool launcher cards with one-line descriptions
- Quick Reference section with direct links to tools
- Tool card reordering via drag and drop (persisted locally)
- Admin-only tool visibility gating (hidden unless enabled/unlocked)

### Settings

File: [tools/settings.html](../tools/settings.html)

- Manage Nitrado tokens (add, store locally, pick active token)
- Select active server service (load services, choose, use service)
- Platform selection (Auto, Xbox, PlayStation)
- Developer Debug Mode toggle (shows extra diagnostics/logging across tools)
- FTP credential storage (per service; used as a fallback channel where needed)
- UI style preset selector (theme preset for tool pages)
- Admin Live Ops access gate (unlock/lock admin tools)
- Nitrado Controller: upload strategy selector (Auto/API/FTP) + connectivity checks
- App updater controls (check, download, install)

### Nitrado Customer Settings

File: [tools/dayz-nitrado-customer-settings.html](../tools/dayz-nitrado-customer-settings.html)

- Fetch Defaults and Fetch Current from Nitrado panel settings endpoints
- Quick Toggles UI for boolean-like settings (writes immediately)
- Write a single setting by category + key + value
- Bulk Apply JSON (accepts Nitrado export JSON or a category map JSON; sequential writes)
- Start, Stop, Restart server actions (Nitrado API)
- Applies log output for auditing what was written

### File Browser Editor

File: [tools/dayz-file-browser-editor.html](../tools/dayz-file-browser-editor.html)

- Browse server directories (list path, go up, refresh)
- Open editable file types into a text editor pane
- Load current file from Nitrado
- Load a local file into the editor
- Upload edited content back to Nitrado (uses shared Nitrado I/O when available)
- Download current editor content to a local file
- Nitrado debug output panel (when enabled)

### RPT Error Panel

File: [tools/dayz-rpt-error-panel.html](../tools/dayz-rpt-error-panel.html)

- Analyze local .rpt/.log/.txt input or pasted log text
- Optional download newest (or named) RPT from Nitrado, then analyze
- Search and severity filters (Errors, Warnings, optional Info)
- Summarizes common DayZ server patterns (CE warnings, missing files, dynamic event disabled, stack traces, crash-log blocks)

### Weather Configurator

File: [tools/dayz-weather-configurator.html](../tools/dayz-weather-configurator.html)

- Load cfgweather.xml from Nitrado or local file
- Edit weather systems (Overcast, Fog, Rain, Wind, Storm, Snowfall)
- Generate/preview XML output
- Copy output to clipboard
- Download edited cfgweather.xml
- Upload edited cfgweather.xml to Nitrado

### Server Globals Configurator

File: [tools/dayz-globals-configurator.html](../tools/dayz-globals-configurator.html)

- Load globals.xml from Nitrado or local file
- Edit server economy and lifecycle globals (entity caps, cleanup timers, persistence-related globals)
- Spawn control section (high-level economy control surface)
- JSON/XML output preview (copy to clipboard)
- Download edited globals.xml
- Upload edited globals.xml to Nitrado
- Nitrado debug panel

### CfgGameplay Configurator

File: [tools/dayz-cfggameplay-configurator.html](../tools/dayz-cfggameplay-configurator.html)

- Load cfggameplay.json from Nitrado or local file
- Edit major gameplay tuning categories:
  - General Settings, Player Data
  - Stamina System, Shock System, Movement, Drowning
  - Weapon Obstruction
  - Base Building (Hologram + Construction)
  - UI & Map, Vehicles
  - References to preset file arrays and world data sections
- JSON output preview (copy to clipboard)
- Download edited cfggameplay.json
- Upload edited cfggameplay.json to Nitrado
- Nitrado debug panel

### Spawn Point Editor

File: [tools/DayZ_Spawn_Visualizer.html](../tools/DayZ_Spawn_Visualizer.html)

- Load cfgplayerspawnpoints.xml from Nitrado or local file
- Interactive map visualization (pan, zoom)
- Drag and drop spawn points on the map (updates x/z in the XML)
- Spawn section selector (All / Fresh / Hop / Travel)
- Delete selected spawn point (removes a <pos> node from XML)
- Single-section workflow (keep only Fresh OR Hop OR Travel to minimize total spawns)
- XML safety: hides map points when XML is invalid; preserves XML declaration on serialize
- Copy XML and format XML output
- Download edited cfgplayerspawnpoints.xml
- Upload edited cfgplayerspawnpoints.xml to Nitrado
- Nitrado debug panel

### Event Spawns Editor

File: [tools/dayz-cfgeventspawns-editor.html](../tools/dayz-cfgeventspawns-editor.html)

- Load cfgeventspawns.xml from Nitrado or local file
- Event list with search/filter
- Position list per event
- Edit selected position attributes (x, z, optional y, optional a)
- Add and delete positions
- Interactive map visualization (pan, zoom)
- Drag and drop event spawn points on the map (updates x/z)
- Copy and download exported XML
- Upload edited cfgeventspawns.xml to Nitrado
- Nitrado debug panel

### Territories Editor

File: [tools/dayz-territories-editor.html](../tools/dayz-territories-editor.html)

- Load mission env territory files from Nitrado or local file (preset selector for common *_territories.xml names)
- Territory search and list
- Edit territory properties (including numeric color)
- Zones list and zone editing (per territory)
- Interactive map visualization
- Export section (copy/download)
- Upload edited territories file to Nitrado
- Nitrado debug panel

### MapGroupProto Editor

File: [tools/dayz-mapgroupproto-editor.html](../tools/dayz-mapgroupproto-editor.html)

- Load mapgroupproto.xml from Nitrado or local file
- Group search and list with point and lootmax visibility for balancing
- Edit group properties (including loot max)
- Containers list and container editing (loot caps and filters)
- Normalize Lootmax action (adds missing lootmax based on point count)
- Export section (copy/download)
- Upload edited mapgroupproto.xml to Nitrado
- Nitrado debug panel

### Event Groups Editor

File: [tools/dayz-cfgeventgroups-editor.html](../tools/dayz-cfgeventgroups-editor.html)

- Load cfgeventgroups.xml from Nitrado or local file
- Optional load mapgroupproto.xml for validation context
- Group search and list
- Edit selected group settings
- Children list and child editing
- Validation section (guardrails for strict file expectations)
- Export section (copy/download)
- Upload edited cfgeventgroups.xml to Nitrado
- Nitrado debug panel

### Spawnable Types Editor

File: [tools/dayz-spawnabletypes-editor.html](../tools/dayz-spawnabletypes-editor.html)

- Load cfgspawnabletypes.xml from Nitrado or local file
- Type search and list
- Edit selected type
- Edit attachments blocks and per-block details
- Edit cargo presets
- Edit damage ranges
- Cross-link helpers to Types.xml data (where available)
- Types tags integration via Limits library
- Validation section
- Export section (copy/download)
- Upload edited cfgspawnabletypes.xml to Nitrado
- Nitrado debug panel

### Types.xml Editor

File: [tools/dayz-types-editor.html](../tools/dayz-types-editor.html)

- Load types.xml from Nitrado or local file
- Search/filter types list
- Edit economy values (nominal/min/lifetime/restock and related economy knobs)
- Edit flags
- Edit categories, usage, and value tiers
- Limits Library integration (load list definitions for categories/tags/usage/value)
- Validation section
- Export section (copy/download)
- Upload edited types.xml to Nitrado
- Nitrado debug panel

### CfgLimitsDefinition Editor

File: [tools/dayz-cfglimitsdefinition-editor.html](../tools/dayz-cfglimitsdefinition-editor.html)

- Load cfglimitsdefinition.xml from Nitrado or local file
- Use cached lists (for fast reuse across tools)
- Edit list primitives:
  - Categories
  - Tags
  - Usage flags
  - Value flags
- XML preview
- Copy XML
- Download and upload edited cfglimitsdefinition.xml
- Nitrado debug panel

### Admin Live Ops (restricted)

File: [tools/admin-live-ops.html](../tools/admin-live-ops.html)

- Access gate (admin code unlock)
- Execution modes:
  - Console Bridge (mission scripts + file uploads)
  - Nitrado Command API (when supported)
- Console Bridge installer and status check
- Folder picker for mission/profile paths
- Upload local bridge files (init.c, adminCommands.c)
- Website-style action buttons for common admin actions (builds or sends command templates)
- Command log output and Nitrado debug log

### Documentation

File: [tools/documentation.html](../tools/documentation.html)

- Built-in documentation for tool workflows and safe editing
- Sections covering setup and per-tool usage notes

### Legal & Privacy

File: [tools/legal.html](../tools/legal.html)

- In-app privacy statement and legal notes (effective date displayed)
- MIT license note and third-party dependency pointers
- Not affiliated disclaimer

### Tool Template (developer scaffold)

File: [tools/TOOL_TEMPLATE.html](../tools/TOOL_TEMPLATE.html)

- Baseline page scaffold for adding new tools (layout, styling, navigation)
- Includes shared UI baseline script and Nitrado proxy hook

---

[Back to Home](./index.md) · [Support Discord](https://discord.gg/nPugvHKhsk)
