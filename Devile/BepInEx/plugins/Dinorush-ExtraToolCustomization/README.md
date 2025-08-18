# ExtraToolCustomization

## Bug Fixes

### All Tools

Fixes tool ammo resetting to 100% when using a tool/picking up sentry with more than 100% ammo. Tools still cannot gain ammo above 100%.

### All Sentries

Fixes a bug where sentries that ran out of ammo while firing at a target would fire once immediately when given ammo.

Also improves the modern sentry targeting logic (Shotgun + Sniper Sentry use this in vanilla). The improved logic makes sentries less liable to stop targeting an enemy they just targeted or fail to target enemies through doors.

### Burst Sentry

Fixes burst sentry behavior. It could previously preserve remaining burst across activations, firing less than expected. Additionally, it had extended lock on time on initial placement or if it had no remaining burst after killing the last enemy in range.

In other words: Burst Sentry has faster initial lock-on time and its first burst is always a full burst. Likely makes Burst Sentry stronger, so use in vanilla at your own risk!

### Shotgun Sentry **(Requires MTFO)**

Allows `Sentry_FireTowardsTargetInsteadOfForward` in Archetype data to work on Shotgun Sentries.

## Tool Customization **(Requires MTFO)**

Un-hardcodes Sentry archetype IDs. They are instead determined by GearCategory according to the fire mode defined in PlayerOffline (`c:1`):
- 10: SemiArchetype
- 11: AutoArchetype
- 12: BurstArchetype
- 13: SemiArchetype (Shotgun)

Sentries can be customized via custom files under `Custom/ExtraToolCustomization/Sentry`. A template file will be generated on game start if no files exist. The files are formatted as lists of data objects. For example, see the base template:

```
[
  {
    "ArchetypeID": 0,
    "Name": "Sentry Gun",
    "BackDamage": false, // Enables/disables back damage for the sentry
    "FriendlyDamageMulti": 1f, // Modifier on damage dealt to players
    "DeployTime": 3, // Time for the sentry to deploy
    "ScanDelay": 1.5, // Time for the sentry to begin scanning after deploying or losing a target
    "PlacementTime": 0.6, // Time to place the sentry
    "PickupTime": 0.6, // Time to pick up the sentry
    "ScanColor": "#00895CFF", // Color of the scan beam
    "TargetColor": "#F0561AF4" // Color of the scan beam when a target is locked
  }
]
```

Mines can likewise be customized via custom files under `Custom/ExtraToolCustomization/Mine`. Base template:
```
[
  {
    "OfflineID": 0, // OfflineID can be used for Mine Deployer tools
    "ItemID": 0,
    "Name": "Mine Deployer",
    "Delay": 0.25, // Delay before the mine detonates
    "Radius": 2.5, // Radius of the capsule hit detection
    "DistanceMin": 3, // Distance within which maximum damage is dealt
    "DistanceMax": 15, // Maximum length of the capsule hit detection; distance past which minimum damage is dealt
    "DamageMin": 15,
    "DamageMax": 50,
    "Force": 1000, // Force applied to killed enemies
    "PlacementTime": 0.5, // Time to place a mine
    "PlacementCooldown": 2, // Time you can't do anything after placing a mine
    "PickupTime": 0.5, // Time to pick up a mine
    "BeamData": {
      "Color": "#FF0000FF", // Color of the beam
      "Width": 1, // Width of the beam
      "Length": 20 // Length of the beam, affects how far away the mine detects enemies
    },
    "LightData": {
      "Color": "#FF0000FF", // Color of the small blinking light on the mine
      "Intensity": 0.03, // Intensity of the light
      "Range": 1 // Range/size of the light
    }
  },
  {
    "OfflineID": 0,
    "ItemID": 0, // Item ID can be used for consumables OR Mine Deployer tools
    "Name": "Consumable Mine",
    "Delay": 0.25,
    "Radius": 2,
    "DistanceMin": 2.5,
    "DistanceMax": 12,
    "DamageMin": 10,
    "DamageMax": 35,
    "Force": 700,
    "PlacementTime": 0.5,
    "PlacementCooldown": 2, // Only matters if the mine has more than 1 use
    "PickupTime": 0.5, // Has no impact on consumable mines
    "BeamData": {
      "Color": "#FF0000FF",
      "Width": 1,
      "Length": 20
    },
    "LightData": {
      "Color": "#FF2020FF", // Consumable mines' lights remain static and do not blink
      "Intensity": 0.3,
      "Range": 0.8
    }
  }
]
```