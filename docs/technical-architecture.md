# Technical Architecture

## Goals

Build a reproducible Minecraft 1.21.1 NeoForge pack that supports:
- Datapack/config-driven recipe and loot changes where possible.
- A quest-driven campaign.
- Bespoke MERIDIAN items and mechanics without fragile one-off hacks.
- Client and dedicated-server parity.

## Layered implementation

### Layer 1 — Modpack configuration and datapacks

Use mod configs and vanilla datapacks for straightforward tuning, tags, loot, advancements, and recipes when the relevant recipe type supports data-driven definitions. Keep changes small and documented.

### Layer 2 — Quest system

A quest system should handle:
- Chapter structure and narrative.
- Item submission and recipe milestones.
- Unlocks and explanatory contracts.
- Player-certified construction checklists.

Do not claim quests can inspect arbitrary multiblocks, measure throughput, or verify a live power network unless a tested detector or custom implementation actually does so.

FTB Quests is a candidate, not yet installed. Its full required dependency chain must be pinned and tested before adoption.

### Layer 3 — Dedicated MERIDIAN content

Use a small dedicated NeoForge mod with mod ID `meridian` for:
- Namespaced item/block registrations.
- Meridian Core component items.
- The Meridian Field Regulator and other custom progression components.
- Gate controller and activation state.
- Server-authoritative interaction and teleportation.
- Custom structures or dimension hooks if required.
- Networking, persistence, and data generation.

Do not start with a large custom mod before the basic pack boots. Begin with a small item-and-recipe vertical slice, then grow the mod only when a tested feature requires it.

## Proposed namespaces and naming

- Mod ID: `meridian` (subject to availability check).
- Initial integration item: `meridian:field_regulator`.
- Future item IDs: `meridian:industrial_heart`, `meridian:chemical_matrix`, `meridian:power_singularity`, `meridian:control_lattice`, `meridian:astral_keystone`, `meridian:meridian_core`.
- Gate block/controller IDs should be decided after the implementation route is chosen.
- Use stable IDs once published; avoid renaming content after worlds exist.

## Repository layout target

```text
MERIDIAN/
├── README.md
├── docs/
│   ├── vision.md
│   ├── campaign-and-endgame.md
│   ├── industrial-systems.md
│   ├── mod-selection.md
│   ├── technical-architecture.md
│   ├── vertical-slice.md
│   ├── roadmap.md
│   ├── validation-plan.md
│   └── decisions.md
├── development/
│   └── README.md
├── pack/
│   ├── manifest/
│   ├── config/
│   └── defaultconfigs/
└── meridian-mod/
```

Do not create empty placeholder configs that imply a working pack exists. Add each directory when it contains tested content.

## Gate implementation options

### Option A — Existing dimension/portal mod
Pros: faster, less custom code, potentially lower maintenance.
Cons: less control over presentation, destination, and activation behavior.

### Option B — Custom Gate mechanics with an existing destination
Pros: bespoke activation and visual identity without immediately owning a full dimension.
Cons: requires a custom mod and careful server testing.

### Option C — Dedicated custom dimension
Pros: complete control over worldgen, structures, progression, and atmosphere.
Cons: highest development and maintenance cost; requires careful server, save, and worldgen testing.

**Current recommendation:** prototype B first, then decide whether C adds enough value to justify its cost.

## Authority and multiplayer rules

- Progression state that affects the world must be server-authoritative.
- Never rely on a client-only script for Gate activation or item rewards.
- Test two clients joining the same dedicated server.
- Verify persistence across server restart and dimension changes.
- Avoid quest objectives that can be completed client-side but fail to synchronize.

## Version discipline

Maintain a locked manifest containing:
- Minecraft version.
- NeoForge build.
- Java runtime requirement.
- Mod filename, version, project/source URL, side, dependencies, and test status.
- Config/datapack/custom-mod revision.
- Known incompatibilities.

Do not label a build stable until it has passed the validation plan.
