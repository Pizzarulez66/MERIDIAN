# Industrial integration plan

The point of MERIDIAN is to make the two mods form a production network, not to bolt one mod's machines onto the other as decoration.

## 1. Division of labor

### Immersive Engineering: extraction, material forming, and physical plant

- Mineral deposits and Excavators establish location-based resource infrastructure.
- Conveyors, chutes, crates, and silos move and buffer bulk materials.
- Coke Oven and Blast Furnace introduce a slower, physical early metallurgy chain.
- Crusher, Arc Furnace, Alloy Kiln, Metal Press, and Assembler provide heavy material preparation and component fabrication.
- Biodiesel/Diesel generation and the IE wire system supply a resilient plant-level power backbone.

### Mekanism: precision processing, chemistry, and high-density power

- Enrichment, purification, chemical injection, dissolution, washing, and crystallization provide staged ore upgrading.
- Electrolytic Separator, Chemical Infuser, Pressurized Reaction Chamber, and other chemical machines form an industrial chemical plant.
- Factories and Logistical Transporters automate repetitive processing and routing.
- Induction Matrix provides centralized energy buffering; advanced generator and endgame systems provide high-output power.

## 2. Planned cross-mod production loop

```text
IE mineral survey / Excavator
            |
            v
IE Crusher + bulk handling
            |
            v
Mekanism ore-processing stages
            |
            v
Mekanism refined metal / chemical intermediates
            |
            v
IE Alloy Kiln / Arc Furnace / Metal Press / Assembler
            |
            v
High-grade industrial components
            |
            +----> Mekanism machine upgrades / advanced plant modules
            |
            +----> MERIDIAN Grid Synchronizer and expansion hardware
```

The exact recipes and outputs will be selected after registry IDs and machine schemas are checked in the loaded instance. The repository deliberately does not ship guessed item IDs or untested machine recipe JSON.

## 3. Integration layers

### Shared energy network

Mekanism and Immersive Engineering both participate in the Forge Energy ecosystem. The proposed layout uses IE connectors/relays and high-voltage wires for long-distance plant distribution, with Mekanism Universal Cables used for local machine buses and the Induction Matrix used for buffering. The pack must test IE→Mekanism and Mekanism→IE transfer separately; connector/cable loss, transfer limits, and sided capabilities must be measured rather than assumed.

### Ore and metallurgical chain

IE extraction should be the bulk-resource input, not a competing route that bypasses the Mekanism processing tiers. The first baseline is Mekanism 3x processing; a later chapter introduces chemical injection for selected high-value ores. IE Arc Furnace and Assembler recipes will consume selected Mekanism outputs and turn them into distinct industrial parts. IE's steel/alloy machinery remains useful for materials that are best produced in its multiblocks.

### Chemicals and fuel

Immersive Petroleum adds an IE-native oil branch. The player uses its crude-oil extraction and refining as a fuel/economy line for IE industry. Mekanism's gas chemistry remains a separate, explicit system; no invisible conversion between IE liquids and Mekanism gases will be implied. Where a cross-system conversion is desired, it must be represented by an explicit, balanced machine recipe with a clear input/output and quest explanation.

### Logistics

The baseline keeps the physical identity of the two mods visible: IE conveyors and bulk storage for plant floors; Mekanism transporters and bins for machine routing. AE2 is optional and late-game, intended for high-volume planning and remote access rather than replacing all physical infrastructure. Create trains are an optional expansion for inter-site freight.

## 4. Script strategy

- Use KubeJS Mekanism for Mekanism recipe changes; its documented API exposes machine recipe builders and chemical inputs.
- Use Immersive Engineering JS only after its exact NeoForge build is verified in the instance; alternatively use IE's native datapack recipe types where the schema is documented and testable.
- Keep each integration line in its own file, e.g. `10_ie_to_mekanism.js`, `20_mekanism_to_ie.js`, and `30_endgame_components.js`.
- Remove or replace duplicate recipes explicitly; never add a new route without evaluating whether it creates a cheaper exploit or bypasses a technology milestone.
- Every custom recipe must have a matching JEI/EMI visibility check and at least one in-world machine test.

## 5. Balance rules

1. IE extraction is a sustained bulk feed, not a free replacement for all mining.
2. Mekanism multipliers must cost infrastructure: chemicals, power, and staged machines.
3. The pack should not let a single early recipe produce both mods' late-game materials.
4. Every advanced IE component should have at least one role in a Mekanism-facing machine line or MERIDIAN requirement; every major Mekanism intermediate should feed at least one IE fabrication line.
5. Any recipe change must preserve byproducts (slag, secondary outputs, spent chemicals) where they are meaningful.
