# HirnuGeos
geomorph custom tiles, without unity compressed asset bundles.

## details
generated at runtime, using the subcomplex set for the zone. assimilates wall and floor textures that are borrowed from LG_PrefabSpawners of loaded assets, depending on complex. same tile will look different on mining and service (floodways).

all geos are single-area tiles with roomsize Medium (coverage 10)

on dimensions with levelgen and IsOutSide true, the ceiling is left out. enjoy the sun.

## usage
always load extra shard "Tech" if complexset of level is mining or service! (the lamp fixtures and the gencluster require it)

lgtune tileoverrides (maybe even zoneoverrides, haven't tested) the following names on similarly sized i-tile, hub-tile, deadend-tile. (these tiles are always size medium). check HirnuGeosDemo custom/LGTuner/ for examples.

## tiles
### hirnugeos_i
a very basic straight hallway 16 x 64, some markers for lockers etc.

### hirnugeos_i_areatest
hallway spliced into 2 parts, unfinished, just a test tile.

### hirnugeos_hub
4-way hub with a central pillar with all storage and terminal markers going around it.

### hirnugeos_deadend
16x16 room with terminal marker in the middle and locker markers on the far wall, a resource room.

### hirnugeos_hub_gencluster
hub but has a marker for gencluster in the middle, no central pillar, wall has a 16x24 hole to accommodate. make sure to add a gencluster to the zone in levellayout. (gencluster will be replaced by some other structure if not, see HirnuGeosDemo)

### hirnugeos_hub_reactor
hub but reactor, startup and shutdown tested to work.

## hirnugeos_elevator
since lgtuner 1.1.0: hub but elevator. zone 0 area b builds south, and, u have to override the plug to be nogate (otherwise a secdoor or even a bulkdoor), see hirnugeosdemo how it can be done. cargo cage levitates a bit, sorry. altitude overrides work immediately around 0,0.
