# Compatibility and platform matrix

Research snapshot: **2026-11-21**. This is a candidate matrix, not a statement that the complete mod set has been tested together.

## Platform

| Component | Candidate | Evidence / constraint | Status |
|---|---|---|---|
| Minecraft | 1.21.1 | Current files for both core mods and the selected scripting/quest tooling target this version. | Selected |
| Loader | NeoForge 21.1.x; baseline 21.1.267 | NeoForge 21.1.267 is listed as a current 1.21.1 build; KubeJS 1.21.1 docs require NeoForge 21.1.199 or newer. | Selected; lock exact build during instance creation |
| Java | 21+ | Mekanism 1.21.1 targets Java 21+. | Required |

## Core and integration mods

| Mod | Candidate version | Loader/version support | Role | Status |
|---|---:|---|---|---|
| Mekanism | 10.7.19.85 | NeoForge 1.21.1 | Chemical processing, factories, logistics, advanced power and endgame systems. | Confirmed file exists |
| Mekanism Generators | 10.7.19.85 | NeoForge 1.21.1 | Gas-burning, fission/fusion and other Mekanism power options. | Confirmed file exists; keep version aligned with Mekanism |
| Immersive Engineering | 12.4.2-194 | NeoForge 1.21.1 | Excavation, coke/steel chain, Crusher, Arc Furnace, Metal Press, Assembler, wires and physical infrastructure. | Confirmed file exists |
| Immersive Petroleum | 4.5.0-39 | NeoForge 1.21.1; requires IE 12.4.2-194 | Oil extraction/refining and an IE-native liquid-fuel branch. | Confirmed compatible dependency pair |
| KubeJS | 2101.7.2-build.381 | NeoForge 1.21.1 | Recipe and pack scripting. | Confirmed release candidate; resolve Rhino dependency via launcher |
| Rhino | 2101.2.7-build.81 or newer | NeoForge 1.21.1 | Required scripting runtime for KubeJS. | Minimum documented by KubeJS 1.21.1 install guide; select compatible release |
| KubeJS Mekanism | 2101.1.7-build.18 | NeoForge 1.21.1 | Adds Mekanism machine recipe APIs and chemical support to KubeJS. Requires KubeJS and Mekanism; its 1.21.1 build is marked Beta. | Confirmed file exists; **test before treating as release-stable** |
| Immersive Engineering JS | 2101.1.1 | NeoForge 1.21.1 | KubeJS compatibility for most IE recipes. A newer 1.1.2 file is listed for Forge, while 1.1.1 is the listed NeoForge file. | Candidate; verify on target instance before use |

## Questing and optional logistics

| Mod | Candidate | Dependency / role | Status |
|---|---|---|---|
| FTB Quests | 2101.1.39 | 1.21.1 NeoForge. Requires FTB Library, FTB Teams, and Architectury API. | Confirmed file exists |
| FTB Library | 2101.1.40 | 1.21.1 NeoForge. | Confirmed file exists |
| FTB Teams | 2101.1.12 | 1.21.1 NeoForge. | Confirmed file exists |
| Architectury API | Latest compatible 1.21.1 NeoForge file | Required by FTB Quests; let the launcher resolve a matching dependency. | Dependency confirmed; exact file not pinned here |
| Applied Energistics 2 | 19.2.20 | Optional late-game digital planning/storage layer. Do not make it the only logistics solution. | Confirmed file exists; optional |
| Create + Steam 'n' Rails NeoForge port | Latest compatible 1.21.1 pair | Optional freight rail infrastructure; rails should support the factories rather than replace the two core mods. | Optional; test as a separate feature branch |

## Important compatibility notes

- **Power is a shared FE/Forge Energy ecosystem, not a bespoke IE↔Mekanism bridge.** The intended design uses that common energy interface to connect IE generation/distribution with Mekanism consumers/storage. Both connection directions, connector types, cable limits, and measured throughput still need to be tested in-game.
- KubeJS Mekanism's 1.21.1 build is marked Beta. The current KubeJS Mekanism documentation states it needs KubeJS 2101.7.2-build.303+ and Mekanism 10.7.14.79+; the selected candidates exceed those minimums.
- Immersive Engineering JS is a rewritten integration, not the old KubeJS Immersive Engineering addon. Its 1.21.1 NeoForge file is 2101.1.1. Do not substitute the 1.1.2 Forge file.
- Avoid adding networking mods that conflict with Mekanism's 1.21.1 chemical API without checking their declared compatibility. In particular, do not assume an older LaserIO/AppMek-style release works with Mekanism 10.7.19.
- No claim is made that the full combination is conflict-free until M1/M2/M3 in the validation plan pass.

## Research links

- [Mekanism releases](https://www.curseforge.com/minecraft/mc-mods/mekanism/files/all)
- [Mekanism 10.7.19.85 release details](https://modrinth.com/mod/mekanism/version/10.7.19.85)
- [Mekanism Generators files](https://www.curseforge.com/minecraft/mc-mods/mekanism-generators/files/all)
- [Immersive Engineering files](https://www.curseforge.com/minecraft/mc-mods/immersive-engineering/files/all)
- [Immersive Petroleum 4.5.0-39](https://modrinth.com/mod/immersivepetroleum/version/1nu6ZI52)
- [KubeJS 1.21.1 files](https://www.curseforge.com/minecraft/mc-mods/kubejs/files/all)
- [KubeJS 1.21.1 installation guide](https://kubejs-wiki.tysontheember.dev/1.21.1/start/installation/)
- [KubeJS Mekanism 1.21.1 recipe documentation](https://kubejs-wiki.tysontheember.dev/1.21.1/addons/mekanism/)
- [KubeJS Mekanism files](https://www.curseforge.com/minecraft/mc-mods/kubejs-mekanism/files/all)
- [Immersive Engineering JS files](https://www.curseforge.com/minecraft/mc-mods/immersive-engineering-js/files/all)
- [FTB Quests 1.21.1 files](https://www.curseforge.com/minecraft/mc-mods/ftb-quests-forge/files/all)
- [FTB Library 1.21.1 files](https://www.curseforge.com/minecraft/mc-mods/ftb-library-forge/files/all)
- [FTB Teams 1.21.1 files](https://www.curseforge.com/minecraft/mc-mods/ftb-teams-forge/files/all)
- [AE2 files](https://www.curseforge.com/minecraft/mc-mods/applied-energistics-2/files/all)
- [Steam 'n' Rails NeoForge 1.21.1 port](https://modrinth.com/project/create-steam-n-rails-1.21.1)
