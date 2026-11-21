# MERIDIAN Vertical Slice — The Steel-to-Systems Loop

**Status:** First gameplay prototype specification; recipes and runtime behavior still require in-game validation.

## Purpose

Prove that Immersive Engineering and Mekanism are not two disconnected tech mods. The first playable slice should take the player from visible, physical industry into advanced machine infrastructure, then make the two systems meet in a small MERIDIAN-specific engineering product.

This slice is intentionally small. It is not the full campaign or the final balance pass.

## Chain A — IE establishes the industrial material base

1. Build an Immersive Engineering Coke Oven.
2. Process coal into Coal Coke and collect Creosote Oil.
3. Use Coal Coke in the Blast Furnace to turn iron into steel.
4. Use the Engineer's Manual to progress into the Metal Press and produce metal plates.

The Coke Oven's creosote byproduct and the steel chain give IE a meaningful early industrial identity. Steel is not treated as an arbitrary quest token: it is the structural material that opens the next tier.

## Chain B — IE steel unlocks Mekanism machinery

Mekanism's Steel Casing recipe uses steel, osmium, and glass. MERIDIAN should preserve the ordinary recipe/tag path so IE-produced steel can supply Mekanism's machine infrastructure.

The player then uses Mekanism to establish:
- Enrichment Chamber processing.
- Metallurgic Infuser alloy production.
- Energized Smelter automation.
- A basic energy storage and distribution setup.

This is the first direct cross-mod progression bridge: IE's Coke Oven and Blast Furnace become a practical route into Mekanism machine construction.

## Chain C — Mekanism precision materials return to MERIDIAN engineering

The first bespoke integration item is provisionally named **Meridian Field Regulator**.

Its intended recipe role is to consume:
- An IE-produced steel plate (or another verified IE fabrication component).
- A Mekanism Enriched Alloy.
- A copper/electrical component selected after the exact item tags and recipes are inspected.

The Regulator is a MERIDIAN item, not a renamed vanilla ingredient. It represents the first stable interface between heavy mechanical fabrication and precision chemical/electrical engineering. It will later appear in the Control Lattice and Gate control systems.

Implementation route:
- Register the item in the dedicated `meridian` NeoForge mod.
- Define its recipe in the mod's data resources or a vanilla datapack if the chosen recipe type permits it.
- Do not use KubeJS or CraftTweaker.
- Keep the recipe server-authoritative and visible in the chosen recipe viewer.

## Power integration test

A separate test should verify whether an IE generator and IE wire network can reliably power Mekanism machines through the shared energy capability in the selected releases.

Test cases:
1. IE generator → IE connector/wire → Mekanism machine.
2. Mekanism energy cube → Mekanism machine.
3. Chunk boundary and chunk unload/reload behavior.
4. Dedicated-server operation and two-client visibility.

Do not claim the energy network is validated until the actual in-game test passes.

## Logistics integration test

After power passes, test item and fluid transfer separately:
- IE conveyors/chutes into inventories accepted by Mekanism machines.
- Mekanism logistical transporters into IE inventories.
- IE fluid pipes and Mekanism mechanical pipes with compatible fluid handlers.
- Chunk unload/reload and sided input/output configuration.

Avoid adding a third logistics mod until these native routes have been tested.

## Acceptance criteria

The vertical slice is complete only when:
- [ ] Coke Oven and Blast Furnace form and operate on a dedicated server.
- [ ] IE steel can be used in Mekanism Steel Casing progression.
- [ ] At least one Mekanism machine chain runs from the resulting infrastructure.
- [ ] The Meridian Field Regulator can be crafted from actual IE and Mekanism components.
- [ ] The custom item has a stable registry ID and survives save/reload.
- [ ] Recipe visibility is confirmed in the selected recipe viewer.
- [ ] No recipe bypasses the intended industrial progression.
- [ ] Power and logistics results are documented separately, including failures.
- [ ] Memory and tick performance are recorded on a representative small factory.

## Why this is the first slice

It proves the pack's central identity with a limited mod count. It also gives the project a real custom item and a concrete reason to create the `meridian` mod before investing in the much larger Gate and destination systems.
