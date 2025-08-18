# ExtraEnemyCustomization
```
DISCLAIMER: EEC is meant to be used by rundown devs to make custom enemies with ease. It is not a client-side mod.
```
This mod is a fork of Flowaria's ExtraEnemyCustomization ([EEC_I](https://thunderstore.io/c/gtfo/p/EEC/EEC_I/)) with a several hotfixes since R8 and new features.  

This is a full EEC_I compile with a +X version bump, so it won't cause any issues if both are present in your profile. BepInEx will load and use the newest version, but it's recommended to uninstall the OG EEC.

All credit goes to Flowaria for their breathtaking work on GTFO.

<b>This mod is primarily maintained by Amorously and Dinorush, so please message them first for any questions, issues, or troubleshooting!</b>
- With the exception of bug fixes, please do not ask for new features.

# ***[Use this reference config to learn how to use this mod](https://github.com/hirnukuono/ExtraEnemyCustomization/raw/master/wikifiles/EEC%20Documentation.zip)***
Unzip them to your `YourRundownFolder/Custom/ExtraEnemyCustomization` path. (Note: updates occasionally)

# Changelog
Moved to the [Thunderstore Changelog](https://thunderstore.io/c/gtfo/p/hirnukuono/EEC_H/changelog)!

# Supported Features
+ ## Model Customization
  - `ShadowCustom`: Shadow Variant Customization (for most enemy models), with thermals and tumor support
  - `MaterialCustom`: Material Swapper for changing skin of emenies
  - `GlowCustom`: For edting color of enemy glowing in general, also provide feature to adding custom Pulse Effect
  - `LimbCustom`: Enemy Limb Health/Weak/ArmorSpot Customization
  - `MarkerCustom`: Bio-tracker Ping Icon/Behaviour Customization (with custom images / texts)
  - `ModelRefCustom`: ModelReference Custom for editing Bio-Tracker Ping position/Shooter Firing Position/Striker Tentacle Position
  - `ScannerCustom`: Bio-tracker screen customization per enemies (with real-time color changes)
  - `SilhouetteCustom`: Provides enemies silhouette to be able to see through the wall
  - `BoneCustom`: Powerful setting to change each enemy's bodypart scale/position/rotation or Add your own Prefab to it
  - `AnimHandleCustom`: Allows to directly edit animation timing values or punch scream sfx

+ ## Ability Customization
  - `FogSphereCustom`: Fog Sphere Ability's Fog Setting
  - `BirthingCustom`: Birthing Ability Customization
  - `HealthRegenCustom`: For Health Regen/Decay Enemy
  - `InfectionAttackCustom`: For Infectious Tentacle/Punch/Projectile
  - `ExplosiveAttackCustom`: For Explosive Tentacle/Punch/Projectile
  - `KnockbackAttackCustom`: For adding knockback for Tentacle/Punch/Projectile
  - `BleedAttackCustom`: For adding bleeding effect for Tentacle/Punch/Projectile
  - `DrainStaminaAttackCustom`: For draining victim's stamina
  - `DoorBreakerCustom`: DoorBreaker Ability Speed/Damage Customization
  - `ScoutScreamingCustom`: Change Scout Screaming GlowColor and FogColor along with Infectious FogSphere
  - `PouncerCustom`: For going insane, lugubrious even

+ ## EnemyAbility Customization
  - `BehaviourAbilityCustom`: Trigger Ability based on Cooldown, Distance, LOS, State
  - `DeathAbilityCustom`: Trigger Ability when enemies death triggered

  * ### Supported Abilities
      - `DoAnim`
      - `FogSphere`
      - `Explosion`
      - `SpawnEnemy`
      - `SpawnWave`
      - `EMP`
      - `Cloak`
      - `Chain`: Trigger multiple ability at once!

+ ## Striker Tentacle Customization
  - `StrikerTentacleCustom`
      - Striker Tentacle Model Type Customization
      - Striker Tentacle In/Out/Stay time Custom
  - `TentacleDefinitions`
      - <s>Work in Progress...</s>

+ ## Shooter Firing Customization
  - `ShooterFireCustom`
      - Shooter Projectile Setting Custom
      - Distance based Projectile Setting Swapper
  - `ProjectileDefinitions`
      - Custom Shooter Projectile Editing
      - Explosive Projectile `[Use ExplosiveAttackCustom if possible]`
      - Knockback Projectile `[Use KnockbackAttackCustom if possible]`
      - Bleeding Projectile `[Use BleedAttackCustom if possible]`
      - Infectious Projectile `[Use InfectionAttackCustom if possible]`
      - StaminaDrain Projectile `[Use DrainStaminaAttackCustom if possible]`

+ ## Detection Customization
  - `FeelerCustom`: Scout Feeler Count/Color/Distance Customization
  - `ScoutAnimCustom`: Customizable Scout Feeler Animation

+ ## Scout Wave Customization
  - Different wave settings per Scout Variants and active expedition
  - StopOnDead Setting for Scout alive orientated constant alarm
  - Random Picker for having different wave setting for single variant

+ ## Property Customization
  - `SpawnCostCustom`: You can edit Enemy's spawncost without editing population settings
  - `EventsCustom`: Trigger WardenObjectiveEvent!
      - OnSpawnedEvent
      - OnWakeupEvent
      - OnDeadEvent
      - Triggering LevelLayout's OnBossDeathEvent!
  - `DistantRoarCustom`: Play any custom sound or wave roar when specific wave enemies spawn

+ ## Miscellaneous Things
  - LiveEdit: Edit your config without rebooting the game **(disabled by default)**
  - Healer Enemies support: Negative damage will now heal players
  - Global Config: Flyer Stuck Check, and Amorously's vanilla WaveRoarFix **(disabled by default)**

+ ## Partial Data Integration
  - You can use a string GUID for any persistentID field if you're using PartialData!

# Credits
- peelz: Setup for future MTFO update
- mccad00: Enemy Marker icons
- Kasuromi: Providing code related to SpawnCost / helping a lot with PR review / transition to OG 2.0.0 support
- Dex: Providing code related to SilhouetteCustom
- dakkhuza: Helping with implementing EMP / Providing code related to Explosion
- Flowaria: You rock!
- Hinru: Keeping this plugin alive through modern GTFO / thermal shadows and tumors
- Amorously: Custom wave roars and WaveRoarFix implementation
- Doggy: Assistance with thermal shadow tumors
- Dinorush: Maintenance support and adding many recent features to EEC