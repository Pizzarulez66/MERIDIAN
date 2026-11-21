# Mod selection and verification matrix

Status meanings:
- **Candidate** — intended for evaluation, not yet approved.
- **Version verified** — a matching 1.21.1 NeoForge release has been identified, but it still needs a full-pack test.
- **Dependency check** — required libraries/config APIs must be pinned too.

| Mod | Role | Side | Status / notes |
|---|---|---|---|
| ModernFix | Memory/loading/general fixes | Both | Version verified: 5.27.27+mc1.21.1 |
| FerriteCore | Memory optimization | Both | Matching 1.21.1 NeoForge line confirmed; pin exact file before packaging |
| Sodium | Renderer/FPS | Client | Version verified in research: 0.8.13 for 1.21.1 NeoForge; test with IE/Mekanism screens |
| ImmediatelyFast | UI rendering | Client | Version verified: 1.6.15+1.21.1-neoforge |
| Entity Culling | Occlusion culling | Client | 1.21.1 NeoForge supported; test machine displays and animated entities |
| More Culling | Block rendering culling | Client | 1.21.x NeoForge supported; Cloth Config dependency |
| Dynamic FPS | Background resource use | Client | 1.21.x NeoForge supported; pin exact file |
| Lithium | Game logic optimization | Both | Candidate; exact 1.21.1 NeoForge release not established in this pass |
| JEI | Recipe viewer | Client / optional server | 1.21.1 NeoForge supported; pin stable matching file |
| Jade | Machine/block info | Client / optional server | Candidate; verify matching file and plugins |
| Mouse Tweaks | Inventory controls | Client | Candidate; verify matching file |
| AppleSkin | Food HUD | Client | Candidate; verify matching file |
| Controlling | Keybind search | Client | Candidate; verify matching file |
| Xaero's Minimap | Navigation | Client | Candidate; verify matching file |
| Xaero's World Map | Navigation | Client | Candidate; verify matching file |
| Shulker Box Tooltip | Storage tooltip | Client | Candidate; verify matching file |
| Enchantment Descriptions | Enchantment help | Client | Candidate; verify matching file |
| spark | CPU/tick profiling | Both | 1.21.1 NeoForge supported |
| Observable | Block-entity profiling | Both | Candidate; verify NeoForge build and dependency metadata carefully |
| Not Enough Crashes | Crash reporting/handling | Both | 1.21–1.21.1 NeoForge supported |

## Pinning rules
1. Pin exact file versions, not "latest".
2. Confirm Minecraft 1.21.1 and NeoForge compatibility on the actual file page.
3. Record dependencies and side requirements.
4. Keep client-only mods out of the dedicated-server profile.
5. Save the downloaded jar filename and SHA-256 for each approved file.
6. Change one logical group at a time during testing.
