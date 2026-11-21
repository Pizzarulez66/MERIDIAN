# Phase 1 recipe proposals (not yet implemented)

These are design proposals. Verify item IDs, recipe serializers, tags, and existing recipe behavior against the exact installed versions before turning them into JSON.

## Field Regulator (proposed MERIDIAN milestone item)
Proposed ingredients:
- IE steel plate or steel-sheet equivalent
- Mekanism Enriched Alloy
- IE copper wire or wire-component equivalent
- A redstone/precision control ingredient

Purpose: represents industrial control hardware that combines mechanical fabrication with advanced materials.

## Material routing
| Material | Primary system | Proposed use |
|---|---|---|
| Steel | IE | Structural and fabricated components |
| Copper wire / wire components | IE | Electrical connections |
| Enriched Alloy | Mekanism | Advanced material component |
| Redstone / control ingredient | Vanilla/Mekanism | Signal and control logic |
| Field Regulator | MERIDIAN | Unlock and recipe component for next progression stage |

## Implementation notes
- Avoid duplicating default recipes unless there is a clear progression reason.
- Prefer a new milestone recipe to blanket changes to core-mod recipes.
- Do not use fake recipe IDs or invented item IDs in a released datapack.
- Validate every recipe in JEI after datapack reload.
