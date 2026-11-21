# Development Roadmap

## Milestone 0 — Core baseline
**Goal:** Establish a minimal, reproducible 1.21.1 NeoForge installation.

- [ ] Pin exact NeoForge build.
- [ ] Install only Mekanism and Immersive Engineering plus mandatory dependencies.
- [ ] Clean client boot and world save/reload.
- [ ] Dedicated-server boot and client join.
- [ ] Record memory and startup behavior.

**Exit criteria:** Core client and dedicated server work reliably.

## Milestone 1 — Industrial vertical slice
**Goal:** Prove that the two core mods form a meaningful progression loop.

- [ ] IE Coke Oven → Coal Coke and Creosote Oil.
- [ ] IE Blast Furnace → Steel.
- [ ] IE steel supplies Mekanism Steel Casing progression.
- [ ] Mekanism Enrichment Chamber and Metallurgic Infuser production.
- [ ] Implement `meridian:field_regulator` in the dedicated mod.
- [ ] Test IE and Mekanism energy transfer separately from item/fluid logistics.
- [ ] Verify recipe visibility and quest tracking once a quest stack is selected.
- [ ] Measure production time, power use, memory, and tick behavior.

**Exit criteria:** A player can progress from basic resources to a small automated industrial setup with both pillars contributing and craft the first MERIDIAN-specific integration item.

## Milestone 2 — Campaign and progression
**Goal:** Build the full Overworld campaign.

- [ ] Select and validate quest stack.
- [ ] Implement Acts I–IV.
- [ ] Build the four industrial district chapters.
- [ ] Add contracts, diagrams, and clear sourcing hints.
- [ ] Implement sustainable supply routes for bulk materials.
- [ ] Add the five Meridian component chapters.
- [ ] Balance costs against realistic automation.

**Exit criteria:** The player can reach the Meridian Project through coherent, testable progression.

## Milestone 3 — Meridian Core and Gate prototype
**Goal:** Make the endgame mechanically real.

- [ ] Implement five component items.
- [ ] Implement the Meridian Core recipe and quest chapter.
- [ ] Prototype Gate controller/activation.
- [ ] Choose existing destination vs custom dimension.
- [ ] Test activation, persistence, multiplayer, and failure cases.
- [ ] Add audiovisual feedback and a clear first-arrival experience.

**Exit criteria:** A player can craft the Core, complete the Gate project, activate it, and reach the destination reliably.

## Milestone 4 — Frontier and post-game
**Goal:** Give the destination meaningful reasons to explore and build.

- [ ] Design frontier resources and their uses.
- [ ] Add structures and recoverable technology.
- [ ] Add outpost and logistics objectives.
- [ ] Add optional second-generation engineering projects.
- [ ] Ensure the main campaign is complete before post-game quotas.

**Exit criteria:** The destination supports a distinct optional gameplay loop without destabilizing the main campaign.

## Milestone 5 — Release hardening
**Goal:** Deliver a reproducible, multiplayer-ready pack.

- [ ] Full client and dedicated-server regression tests.
- [ ] Fresh world and existing save tests.
- [ ] Quest sync and progression persistence tests.
- [ ] Performance tests on target hardware.
- [ ] Final mod manifest and dependency audit.
- [ ] Known-issues list and installation instructions.
- [ ] Release notes and versioned backup.

**Exit criteria:** All critical validation checks pass; no known progression blockers or server-start failures remain.

## Scope control

If a feature threatens stability or performance, defer it rather than compromising the core campaign. The custom dimension is explicitly allowed to move later in the schedule.
