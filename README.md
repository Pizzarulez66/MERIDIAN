# MERIDIAN: The Industrial Grid

A technology-focused Minecraft modpack project built around **Mekanism** and **Immersive Engineering**. The design goal is not to add every popular tech mod; it is to make extraction, chemical processing, heavy fabrication, power generation, and logistics form one industrial system.

> **Project status: 0.1.0 — design and compatibility scaffold.** This is not yet a playable modpack release. The version target and candidate mod set have been researched, but recipe rebalance, quest data, and client/server smoke tests still need to be completed in-game.

## Target platform

- Minecraft: **1.21.1**
- Loader: **NeoForge 21.1.x** (baseline candidate: 21.1.267)
- Java: **21 or newer**
- Primary mods: **Mekanism** and **Immersive Engineering**

NeoForge 1.21.1 was selected because both pillars have maintained 1.21.1 NeoForge releases, and the scripting and questing tools needed for custom progression also have 1.21.1 NeoForge builds.

## Design in one sentence

**Mekanism is the chemical and precision-processing backbone; Immersive Engineering is the extraction, foundry, fabrication, and physical infrastructure backbone.** The player must build an industrial network that depends on both.

## The endgame: Project MERIDIAN

The long-term objective is to commission a regional-scale industrial grid, not simply craft the strongest machine. The project has four interdependent districts:

1. **Resource Basin** — Immersive Engineering mineral extraction and bulk handling feed ore into Mekanism processing lines.
2. **Chemical Works** — Mekanism separates, purifies, and upgrades materials and chemicals; its products become feedstock for IE alloying and fabrication.
3. **Power Spine** — an IE high-voltage distribution network links industrial sites, backed by a Mekanism Induction Matrix and a resilient IE fuel generator for black-start capability.
4. **Central Foundry** — IE metal presses, arc furnaces, and assemblers combine with Mekanism factories and advanced chemical products to produce the final Grid Synchronizer.

The questbook will combine automatic item/progression tasks with player-certified engineering checklists for physical builds. A quest mod cannot reliably prove that a player has built a properly routed power grid or a functioning factory layout without custom validation code, so the book will not pretend to automatically inspect those structures.

See [`docs/progression-and-endgame.md`](docs/progression-and-endgame.md) for the full campaign plan.

## Repository layout

```text
.
├── README.md
├── PROJECT_STATUS.md
├── docs/
│   ├── compatibility-matrix.md
│   ├── industrial-integration.md
│   ├── progression-and-endgame.md
│   └── validation-plan.md
├── modlist/
│   └── candidate-mod-list.md
├── kubejs/
│   └── server_scripts/
│       ├── README.md
│       └── 00_pack_baseline.js
└── quests/
    └── README.md
```

## What is intentionally not included yet

- No mod JARs are redistributed here.
- No untested recipes are injected into either mod's machine registry.
- No fabricated FTB Quests JSON is shipped as a fake-functional questbook.
- No generated server configs are committed before a clean first launch, because those configs should be produced by the exact tested mod versions.

## Development workflow

1. Build a minimal client and dedicated-server instance from `modlist/candidate-mod-list.md`.
2. Complete the smoke tests in `docs/validation-plan.md` before adding progression locks.
3. Add cross-mod recipes in small, named KubeJS files; test each recipe in JEI/EMI and in its target machine.
4. Build the FTB Quests chapters from `docs/progression-and-endgame.md` only after recipe IDs and unlock conditions are confirmed.
5. Export a launcher pack only after client/server parity, world creation, and a clean dedicated-server join have been verified.

## License and mod attribution

This repository contains original pack design, documentation, and configuration/scripts authored for this project. Individual mods retain their own licenses and distribution rules. Download mods from their official project pages; do not mirror their JARs here.
