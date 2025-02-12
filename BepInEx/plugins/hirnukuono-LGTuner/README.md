# AdvancedWardenObjective

This mod is basically Flowaria LGTuner with a small tweak that enables lgtuning dimension levellayouts. Also added: directional plugcap overrides.

This is a full LGTuner compile with a +X version bump, bepinex should use the newest version. if any problems arise, delete the older LGTuner.dll (dependencies satisfied).

All credit goes to Flowaria for his breath-taking work on GTFO. We miss you and wish you the best in all aspects of life.

## Changelog

### V1.1.2
hotfix for issue reported by RLC, thanks cheese. if there was no tech complex either natively or loaded as extra shards, stupid choice of material handling location prevented lgtuner function. fixed.

### V1.1.1
partial rework of hirnugeos material handling, fixing elevator when not complex service (would brick textures if other)


### V1.1.0
hirnugeos_elevator finished, geos building logic simplified a bit.

### V1.0.9
ceilings of hirnugeos tiles fixed, were absent due to a stupid logic error. dimensions that are outside are still without ceilings.

### V1.0.8
added HirnuGeos, check HIRNUGEOS.md and rundown HirnuGeosDemo for details

### V1.0.7
same check on createdimension. sorry for spam.

### v1.0.6
previous version produces smelly bricks if TileOverrides is empty. (using only zoneoverrides for example) .. thank you Ceb for reporting!

### V1.0.5
TileOverrides X=0 Z=0 Geomorph="any elevator geomorph" (first in list of tileoverrides for the layout) .. reality or any non-static dimension.

### V1.0.4
plugs and plug caps should not get messed up anymore, removed some stupid. not all.

### V1.0.3
now able to override also plugs that are just separators for different zone's walls (used to work only on plugs with void on the other side), thanks thyunsus for the unrelenting testing work.

### V1.0.2
thyunsus requested the ability to override plugcaps (lgtuned floodways tile with mining caps doesn't look very cool). done.

"LeftPlug": "Assets/AssetPrefabs/Complex/Service/Plugs/env_plug_8mheight_cap_floodways_01.prefab", //West Direction Plug Prefab
"RightPlug": "Assets/AssetPrefabs/Complex/Service/Plugs/env_plug_8mheight_cap_floodways_02.prefab", //East Direction Plug Prefab

### V1.0.1

initial.
