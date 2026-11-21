# Phase 1: The Industrial Bridge

## Objective
Create a small, testable progression chain that proves the pack's cross-mod design before expanding the campaign.

## Chain
1. **Foundation — IE**
   - Coke Oven produces Coal Coke and Creosote Oil.
   - Blast Furnace provides Steel.
   - Metal Press supplies precision plates and fabrication components.
2. **Material preparation — Mekanism**
   - Enrichment and infusing produce advanced material intermediates.
   - Processing is automatable and JEI-visible.
3. **Fabrication — cross-mod**
   - IE steel plates and fabrication parts meet Mekanism alloy/material outputs.
   - A first custom MERIDIAN component (working name: Field Regulator) should use both mods' outputs.
4. **Milestone**
   - Field Regulator unlocks the next set of power, automation and industrial infrastructure objectives.
   - This milestone is a recipe/progression gate—not a claim that the modpack can detect factory layout or throughput.

## Roles
- Immersive Engineering: physical fabrication, steel, plates, wires, treated materials, machinery.
- Mekanism: enriched materials, alloys, chemical processing, scalable processing and advanced machine components.
- MERIDIAN custom content: a limited number of milestone components that intentionally bind both industrial ecosystems.

## Design constraints
- Keep recipe inputs renewable or automatable where practical.
- Avoid recipe inflation and arbitrary stacks of rare ingredients.
- Use tags where they are stable and semantically appropriate.
- Expose recipe and usage information in JEI.
- Every objective must have an in-game way to verify completion.
- Do not assume quest software can inspect multiblock formation or factory throughput unless that detection is actually implemented.
