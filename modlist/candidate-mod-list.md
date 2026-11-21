# Candidate mod list

This is a researched candidate list for a 1.21.1 NeoForge instance, not a frozen export manifest. Install through CurseForge/Modrinth or the launcher's dependency resolver, then record exact file IDs in the release manifest after M1 passes.

## Core gameplay

| Include | Mod | Candidate release | Why it belongs |
|---|---|---|---|
| Required | Mekanism | 10.7.19.85 | Central chemical-processing and advanced-technology pillar. |
| Required | Mekanism Generators | 10.7.19.85 | Mekanism's power-generation progression; keep its version aligned with Mekanism. |
| Required | Immersive Engineering | 12.4.2-194 | Physical engineering, extraction, metallurgy, fabrication, and wire infrastructure. |
| Recommended | Immersive Petroleum | 4.5.0-39 | IE-native crude oil, extraction, and refining; its selected release requires IE 12.4.2-194. |

## Pack-authoring tools

| Include | Mod | Candidate release | Notes |
|---|---|---|---|
| Required | KubeJS | 2101.7.2-build.381 | Server-side recipe/progression scripting. |
| Required | Rhino | 2101.2.7-build.81+ | KubeJS runtime; use a compatible release satisfying the KubeJS install guide. |
| Required | KubeJS Mekanism | 2101.1.7-build.18 | Beta build; needed for clean Mekanism recipe builders/chemical APIs in scripts. |
| Candidate | Immersive Engineering JS | 2101.1.1 NeoForge | Adds KubeJS compatibility to most IE recipes; confirm loading and schema on the chosen NeoForge build. |
| Recommended | FTB Quests | 2101.1.39 | Structured campaign and endgame book. |
| Required by Quests | FTB Library | 2101.1.40 | FTB Quests dependency. |
| Required by Quests | FTB Teams | 2101.1.12 | FTB Quests dependency. |
| Required by Quests | Architectury API | Compatible 1.21.1 NeoForge build | FTB Quests dependency; let launcher resolve compatible file. |

## Optional expansion modules

| Module | Candidate | Rule for inclusion |
|---|---|---|
| Digital storage | Applied Energistics 2 19.2.20 (NeoForge 1.21.1) | Add late, after the physical IE/Mekanism logistics loop works. It must not replace every conveyor/transporter line. |
| Freight rail | Create + Steam 'n' Rails NeoForge port for 1.21.1 | Keep as an infrastructure expansion only. Test as a separate branch so it cannot destabilize the core pack. |

## Deliberately excluded from the first pass

- Large kitchen-sink content mods and unrelated magic/adventure suites.
- Multiple competing pipe, cable, and digital-storage systems.
- Unverified Mekanism integrations targeting older chemical APIs.
- Shader/rendering stacks until the baseline client is stable.
- Extra world-generation and structure mods until ore distribution and Excavator balance are established.

## Version discipline

Do not mix Minecraft versions or loaders. For the initial lockfile, all included JARs must explicitly declare Minecraft 1.21.1 and NeoForge. Do not use the Forge build of an otherwise similarly named 1.21.1 addon.
