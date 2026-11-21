# MERIDIAN — The Industrial Frontier

> A long-form Minecraft technology campaign built around **Mekanism × Immersive Engineering**.

**Status:** Foundation / pre-production  
**Target:** Minecraft 1.21.1 · NeoForge  
**Core identity:** Industrial engineering, sustainable automation, exploration, and a world-scale megaproject.

MERIDIAN is about building an industrial civilization capable of restoring a dormant gateway to an unexplored frontier. The player's ultimate trophy is the **Meridian Core**, a multi-stage artifact assembled from five major industrial achievements. The Core is then used to construct and commission the **Meridian Gate**.

This is not intended to be a recipe grind for its own sake. The long-term grind should reward factory expansion, better logistics, reliable supply chains, and increasingly sophisticated engineering.

## The experience in one sentence

**Build the industry. Manufacture the impossible. Reopen the frontier.**

## Non-negotiable design pillars

1. **Mekanism and Immersive Engineering stay relevant.** Both must contribute meaningful production steps throughout the campaign; neither is merely an early-game stepping stone.
2. **Automation is the intended answer to scale.** Large requirements should encourage players to improve production rather than manually collect absurd quantities.
3. **Fair difficulty.** Every major cost needs a clear purpose, a discoverable recipe path, and a sustainable supply route.
4. **A real finale.** Crafting the Meridian Core is a major milestone, not the entire ending. Gate construction, commissioning, and the first frontier expedition complete the main arc.
5. **Optional post-game depth.** Ambitious players can expand the frontier, establish inter-world logistics, and pursue second-generation projects without being forced to do so to finish the campaign.
6. **Lean, stable implementation.** Add mods only when they solve a defined design problem. Verify exact versions, dependencies, server behavior, and performance before locking them.

## Main campaign

| Act | Name | Player achievement |
|---|---|---|
| I | Survey the Frontier | Establish a foothold, investigate the dormant Gate, and identify local resources. |
| II | Found the Works | Build the first extraction, coke/steel, power, and processing facilities. |
| III | Industrial Expansion | Develop advanced ore processing, chemical production, fabrication, and logistics. |
| IV | The Grid | Connect specialized industrial districts with dependable generation, storage, and distribution. |
| V | The Meridian Project | Manufacture the five Core components and assemble the Gate subsystems. |
| VI | Commissioning | Complete the activation sequence and open the Gate. |
| VII | Beyond the Gate | Explore the frontier and pursue optional expansion projects. |

## The Meridian Core

The Core is the campaign's equivalent of a pack-defining trophy item. Its five component families are currently:

- **Industrial Heart** — heavy fabrication, structural materials, and machinery.
- **Chemical Matrix** — advanced chemical synthesis and material transformation.
- **Power Singularity** — generation, storage, conversion, and distribution.
- **Control Lattice** — precision assemblies, automation, and logistics.
- **Astral Keystone** — exploration, rare finds, and recovered technology.

These are design roles, not locked recipes. Ingredient lists, quantities, and exact mod dependencies must follow compatibility research and production-chain prototypes.

## Technical baseline

- Minecraft **1.21.1**
- **NeoForge**; exact build to be pinned after validating the selected mod set.
- Core content pillars: **Mekanism** and **Immersive Engineering**.
- Script engine, quest stack, addons, optional storage/transport mods, and destination dimension remain provisional until tested.

## Repository map

- [`docs/vision.md`](docs/vision.md) — experience, design principles, and scope.
- [`docs/campaign-and-endgame.md`](docs/campaign-and-endgame.md) — campaign acts, Core components, Gate, and post-game.
- [`docs/industrial-systems.md`](docs/industrial-systems.md) — cross-mod production philosophy and district model.
- [`docs/mod-selection.md`](docs/mod-selection.md) — compatibility policy and candidate categories.
- [`docs/technical-architecture.md`](docs/technical-architecture.md) — pack structure, scripts, custom content, and implementation boundaries.
- [`docs/roadmap.md`](docs/roadmap.md) — milestones and acceptance criteria.
- [`docs/validation-plan.md`](docs/validation-plan.md) — boot, gameplay, server, balance, and performance tests.
- [`docs/decisions.md`](docs/decisions.md) — decisions made and questions intentionally left open.
- [`development/README.md`](development/README.md) — contributor workflow and definition of done.

## Current milestone: Foundation

The immediate goal is not to invent final recipes. It is to:

1. Verify exact 1.21.1 NeoForge builds for Mekanism and Immersive Engineering.
2. Establish a minimal bootable client and dedicated server.
3. Select a small, compatible quest and scripting stack.
4. Prototype one genuine IE → Mekanism production chain and one reverse/integrated chain.
5. Measure memory and startup behavior on modest hardware.
6. Only then begin the full progression and balance pass.

**Important:** Quest checklists may ask players to certify a build, but must not claim to inspect arbitrary multiblocks, measure throughput, or verify a live power network unless a tested detector or custom implementation actually does so.
