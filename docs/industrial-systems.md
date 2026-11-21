# Industrial Systems — Making IE and Mekanism Work Together

## Design objective

The pack's defining feature is not that both mods are installed. It is that their systems form a coherent industrial economy. Each mod should have distinct strengths, and cross-mod production should be intentional rather than incidental.

## Working industrial districts

### Resource Basin
Responsibilities:
- Mining and resource acquisition.
- Sorting and bulk storage.
- Primary crushing, washing, and enrichment.
- Early material handling and transport.

IE contribution: visible material handling, conveyors, crusher/squeezer-style processing where appropriate, and physical factory infrastructure.

Mekanism contribution: ore-processing progression and later efficiency upgrades.

### Chemical Works
Responsibilities:
- Fluid and gas production.
- Chemical intermediates.
- Specialty materials.
- Safe storage and distribution.

Mekanism should be a major pillar here. IE and compatible addons may contribute feedstocks or supporting infrastructure where recipes support it.

### Power Station
Responsibilities:
- Early and mid-tier generation.
- Advanced generation.
- Energy storage and distribution.
- Redundancy and capacity planning.

The pack should present multiple viable generation routes where practical. Avoid making one generator the only sensible choice for the entire game.

### Central Foundry
Responsibilities:
- Coke/steel and structural materials.
- Alloys and advanced fabrication.
- Precision assemblies.
- Meridian Core components and Gate hardware.

IE should retain a strong identity in heavy fabrication and physical infrastructure. Mekanism should provide advanced materials and processing that feed the foundry.

## Cross-mod chain requirements

Before a chain is accepted into the campaign, document:
1. Input items/fluids/gases and their source.
2. Processing machine and recipe.
3. Output and downstream use.
4. Power and throughput assumptions.
5. Whether the chain is automatable.
6. Whether the recipe is available on both client and dedicated server.
7. Whether it creates a progression loop or bypass.

A good chain creates interdependence without making one mod feel like a tax.

## Prototype chains to investigate

These are research targets, not confirmed recipes:
- IE coke/steel and structural production feeding Mekanism advanced processing.
- Mekanism chemical outputs feeding IE fabrication or addon processes where supported.
- IE power generation and infrastructure supporting Mekanism machinery at an appropriate stage.
- Mekanism advanced materials feeding IE heavy assemblies.
- Shared logistics and storage supporting the four districts.

## Progression pacing

- Early: IE and Mekanism should both appear, but avoid requiring a full parallel tech tree immediately.
- Mid: require the player to combine materials and infrastructure from both systems.
- Late: Core components should require several independent industrial chains.
- Endgame: the Gate should test the complete industrial network, not one mod's final machine.

## Balance measurements

For each major contract, estimate:
- Manual crafting time.
- Automated production time at a plausible early, mid, and late setup.
- Power demand.
- Number of distinct production chains.
- Whether a player can reasonably scale the chain.
- Whether the cost is meaningful or merely tedious.

Do not balance by raw item count alone. Consider machine time, power, logistics, and prerequisite investment.
