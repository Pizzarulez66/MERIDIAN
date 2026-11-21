# Technical Architecture

## Goals

Build a reproducible Minecraft 1.21.1 NeoForge pack that can support:
- Datapack/config-driven recipe and loot changes where possible.
- Scripted progression and content where justified.
- A quest-driven campaign.
- Bespoke MERIDIAN items and mechanics without fragile one-off hacks.
- Client and dedicated-server parity.

## Layered implementation

### Layer 1 — Modpack configuration
Use mod configs and datapacks for straightforward tuning, tags, loot, and recipes when the relevant mod supports them. Keep changes small and documented.

### Layer 2 — Quest and script integration
A quest system should handle:
- Chapter structure and narrative.
- Item submission and recipe milestones.
- Unlocks and explanatory contracts.
- Player-certified construction checklists.

A script engine may handle:
- Custom recipes and progression gates.
- Custom items/fluids only where supported and maintainable.
- Event-driven interactions that are documented and tested.
- Integration glue between installed mods.

The exact quest and scripting stack is not selected yet. Verify 1.21.1 NeoForge compatibility before committing to an implementation.

### Layer 3 — Dedicated MERIDIAN content
If the Gate requires custom blocks, interactions, a portal, a dimension, or reliable structure logic beyond the script engine's capabilities, implement a small dedicated mod.

A dedicated mod should own:
- Namespaced item/block registrations.
- Meridian Core component items.
- Gate controller and activation state.
- Server-authoritative interaction and teleportation.
- Custom structures or dimension hooks if required.
- Networking, persistence, and data generation.

Do not start with a large custom mod before the basic pack boots. First prototype the smallest mechanic that proves the approach.

## Proposed namespaces and naming

- Mod ID: `meridian` (subject to availability check).
- Item IDs: `meridian:industrial_heart`, `meridian:chemical_matrix`, `meridian:power_singularity`, `meridian:control_lattice`, `meridian:astral_keystone`, `meridian:meridian_core`.
- Gate block/controller IDs should be decided after the implementation route is chosen.
- Use stable IDs once published; avoid renaming content after worlds exist.

## Repository layout target

The repository can evolve toward:

```text
MERIDIAN/
├── README.md
├── docs/
│   ├── vision.md
│   ├── campaign-and-endgame.md
│   ├── industrial-systems.md
│   ├── mod-selection.md
│   ├── technical-architecture.md
│   ├── roadmap.md
│   ├── validation-plan.md
│   └── decisions.md
├── development/
│   └── README.md
├── pack/
│   ├── manifest/          # locked mod list and versions
│   ├── config/
│   ├── defaultconfigs/
│   ├── kubejs/            # only if selected
│   └── quests/            # quest exports
└── meridian-mod/          # only if a custom mod is justified
```

Do not create empty placeholder configs that imply a working pack exists. Add each directory when it contains tested content.

## Gate implementation options

### Option A — Existing dimension/portal mod
Pros: faster, less custom code, potentially lower maintenance.
Cons: less control over presentation, destination, and activation behavior.

### Option B — Custom Gate mechanics with an existing destination
Pros: bespoke activation and visual identity without immediately owning a full dimension.
Cons: still requires a custom mod or a sufficiently capable, tested scripting solution.

### Option C — Dedicated custom dimension
Pros: complete control over worldgen, structures, progression, and atmosphere.
Cons: highest development and maintenance cost; requires careful server, save, and worldgen testing.

**Current recommendation:** prototype B first, then decide whether C adds enough value to justify its cost. Keep the destination choice open until worldgen and performance are tested.

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
- Config/datapack/script revision.
- Known incompatibilities.

Do not label a build stable until it has passed the validation plan.
