# Product Roadmap

Iron Chronicle Tool Suite is already strong at editing, visualization, Nitrado integration, and guardrails.

This roadmap is about becoming the default console DayZ admin platform by adding “dependency features”: diagnostics, cross-file intelligence, safe presets, and rollback.

No dates promised. Priorities can shift based on Nitrado/DayZ changes and real-world console server behavior.

## Phase 1 — CE Intelligence Layer

Instead of only editing values, add a read-only analysis layer that answers: “Is my economy healthy?”

- Economy Health Scan (Types / Globals / Spawnables-aware)
  - Flag extreme `nominal/min` ratios
  - Detect overspawn risks (high nominal + low restock + broad usage)
  - Detect dead economy patterns (min > nominal, lifetime too short/too long, categories that never show)
  - Flag cleanup / lifetime contradictions
- Visual scoring
  - Green = healthy
  - Yellow = risky
  - Red = broken
- Output that matters
  - Plain-English findings
  - “Most likely cause” hints
  - Links that jump to the right editor with the right file pre-selected

## Phase 2 — Preset Engine

Make safe configuration reusable.

- Presets
  - Balanced Vanilla+
  - Hardcore
  - High-loot PvP
- Spawn density templates (by tier and category)
- Community-submitted presets (import/export)
- Safety model
  - Preset “scope” (what it changes)
  - Preview before apply
  - Validation + warnings before upload

## Phase 3 — Multi-File Impact Awareness

Cross-file awareness is the step most console tooling never does well.

- References & integrity checks
  - While editing `types.xml`: show references in `cfgspawnabletypes.xml`, `cfgeventgroups.xml`, and (when applicable) event spawns
  - While editing event spawns: detect “event exists but no matching group” and the inverse
  - While editing limits: show which files/types are using categories/tags/usage/value
- “Impact panel” in editors
  - What this change touches
  - What can break
  - Suggested follow-up edits

## Phase 4 — Snapshot + Diff System (Rollback-Grade)

Give console admins a real safety net.

- Snapshot server config state
  - One-click snapshot of: Globals, Types, Spawnable Types, Event Groups, Event Spawns, Limits, Gameplay
- Diff viewer
  - XML-aware diff (ignore formatting noise)
  - JSON diff (stable key ordering)
- Rollback
  - Restore any snapshot set (single file or full pack)
  - “Restore then restart” checklist

## Phase 5 — Error Pattern Learning (Assistant-Level RPT)

Your RPT panel already recognizes patterns. Make it actionable.

- Probable-fix suggestions
  - What it likely means
  - What file it points to
  - Which editor is most relevant
- Deep links
  - “Open Types editor filtered to this classname”
  - “Open Gameplay schema section”
- Pattern library that grows over time
  - Curated rules (not ML-driven telemetry)
  - Versioned so results are predictable

## Phase 6 — Community Integration (Ecosystem Gravity)

Build trust and reuse without turning into a marketplace.

Everything here stays aligned with the project goal: open-source, free-to-use tooling for DayZ console admins (no paywalls).

- Import shared preset packs
- “Verified safe” badges (rule-based validation + community review)
- Pack metadata
  - Supported maps
  - Intended playstyle
  - Required mods (where applicable)

## What Will Make IC Tool Suite Untouchable

### One‑Click Server Sanity Check

A single button that scans everything important and returns an admin-friendly verdict.

- Scan
  - Globals
  - Types
  - Spawnable Types
  - Spawn files
  - Limits
  - Event links (groups ↔ spawns ↔ proto)
- Return
  - Broken
  - Risky
  - Clean
- Output
  - Findings grouped by severity
  - Exact file + section hints
  - Suggested next actions (and links to the right tool)

## Versioning Intent

Current version is `0.1.x`.

- Don’t rush `1.0`.
- `1.0` should be symbolic and mean:
  - Presets (Phase 2)
  - CE health scan (Phase 1)
  - Snapshot + diff + rollback (Phase 4)

This isn’t just an editor suite. It’s console DayZ infrastructure.
