# Changelog
## 1.8.18 Patch Notes
- Added Global setting to remove bleed on down.

## 1.8.17 Patch Notes
- Hotfix for clients crashing when a SpawnEnemy ability is used.

## 1.8.16 Patch Nodes
- Fixed Checkpoints causing OnDeadEvents to run.
- Fixed LevelLayoutIDs not applying to all Property events.
- Added DoGlobalFallback field to SpawnEnemy abilities to force spawns to occur even if the enemy despawns.

## 1.8.15 Patch Notes
- Added LevelLayoutIDs field to EventsCustom to restrict events to specific levels.
- Fixed ShooterFireCustom not applying on enemies that had just woken up.
- Potentially fixed an issue in the ShooterFireCustom routinue for flyers?

## 1.8.14 Patch Notes
- Added RequireEABAllowed field to BehaviorAbilityCustom to restrict the ability usage if the enemy can't use normal abilities.
- Added StopRootMotion field to DoAnim to restrict animation movement.
- Fixed health-damaging FogCustom only affecting host.
- Fixed EMP and StandStill animations overriding each other and enabling enemy movement early.
- Fixed issues where EMP and StandStill animations could allow enemies to perform actions they shouldn't when interrupted.
- Fixed SpawnProjectiles with "FindTargetIfInvalid" set targeting downed players.
- Enabled LiveEdit by default.

## 1.8.13 Patch Notes
-  MaterialCustom now supports flyer bodies (but not tentacles).
-  EMP now smoothly gets interrupted by wakeups.
-  Fixed EMP or StandStill animations remaining stuck after finishing if the enemy began it during certain states (e.g. attack, scream)
-  Fixed EMP or StandStill animations causing the enemy to "slide" with its current velocity.
-  Fixed certain abilities that halted the enemy causing it to act after being interrupted by foam.
-  A forced exit on BehaviourAbilityCustom is now considered a forced exit for ChainedAbility.
-  Added customization for ForceExitOnConditionMismatch to BehaviourAbilityCustom to separate exit conditions from enter conditions.
-  Expanded AllowWhileAttack on BehaviourAbilityCustom to additionally check if the enemy started an attack rather than only checking if their attack was out (e.g. tongue is extending to its target).

## 1.8.12 Patch Notes
- Added field to DistantCustomRoar for dynamic custom wave roars support. Note this is subject to change in the future, hence lack of documentation.
- Added (silent) Krakens to WaveRoarFix so they will no longer use the striker wave roar when they spawn.
- Fixed an incompatibility with the Oxygen plugin which caused oxygen health drain to increase health instead. Note that EEC health draining fog still breaks if used in conjunction with Oxygen.
- Added MaxRange field to custom tentacle fields.
- Fixed EMP resetting to default lights; this is meant to be a simple stopgap until a more comprehensive refactor is done.
- Added EnemyMinRange and EnemyMaxRange fields to Explosions, which set explosion radius values exclusively for enemies.
- Fixed explosions causing "taken damage" effects when 0 damage was dealt.
- Added HitEnemies field to Projectiles to allow them to hit other enemies.

## 1.8.11 Patch Notes
- Fixed accidental revert of DistantRoarCustom's None, OldDistantRoar, and Custom wave roar overrides in recent updates.

## 1.8.10 Patch Notes
- Fixed LiveEdit support! Many thanks to Hirnu and Dinorush for the aid.

## 1.8.9 Patch Notes
- At Becky's behest, adds support for health-modifying fog.

## 1.8.8 Patch Notes
- Fixed ChainedAbility not working on clients.
- Fixed SpawnProjectile sound not working on clients.
- Fixed DoAnim errors.
- Fixed Enemies that woke up during EMP animations getting stuck in hibernate.
- Fix infection sound @ origin & add customization.

# 1.8.7 Patch Notes
- Fixed issue where Custom, OldDistantRoar, and None roar sound overrides did not work for DistantRoarCustom.

## 1.8.6 Patch Notes
- Refactored code for DistantRoarCustom and NewShadows.
- Made internal namespaces consistent (EEC vs ExtraEnemyCustomization).
- Fixed issue where shadow enemies with tumors didn't have any thermals on their tumors.

## 1.8.5 Patch Notes
Dinorush has made some more contributions <3
```
Features:
  Chained:
    - ExitAllInForceExitOnly: Only exits the chained abilities early if the exit was forced. Overrides ExitAllInForceExit, which always exits the chained abilities early whenever it exits.
  EMP:
    - ActivateDuration: The time that the enemy remains in the EMP state after activating. Previously hardcoded to 5s.
  SpawnProjectile:
    - SoundID: Sound to play when the event fires.
    - FindTargetIfInvalid: Finds the closest visible player target when the enemy AI has no target. Useful for states like hibernating and patrolling.

Bug Fixes:
  Chained:
    - Fixed timer variables being tied to the ability settings rather than the instanced behaviors, causing undefined results when multiple enemies with the same Chained ability were active.
```

## 1.8.4 Patch Notes
- You can now use modded events, including ones from AWO or EOS, in Property -> EventsCustom
- Added InjectLib as a hard dependency for this functionality.

## 1.8.3 Patch Notes
 - Dinorush has made some contributions!
```
Fixes 2 primary bugs:
  -  Collision effects (explosion, bleed, etc.) firing for every single client rather than only the local client*
  -  Projectiles that collide with walls or players still triggering LifetimeDone events after 5 seconds

*Since explosions can trigger on walls, they are entirely determined by the host instead
```
- Updated EEC wiki documentation

## 1.8.2 Patch Notes
- Fixed DistantRoarCustom config not clearing itself properly
- Fixed issue with roar sizes where the biggest roar size for a roar sound would play regardless of if that enemy is present in the wave
- Updated Thunderstore links to Hirnu's EEC GitHub repo

## 1.8.1 Patch Notes
- Implemented Amorously's WaveRoarFix
- Fixed Pouncer and added option for Immortal, Nightmare Striker, Nightmare Shooter, Old Distant Roar, Custom, and No wave roar sounds
- Retroactively changed `"WaveRoarOverride"` in DistantRoarCustom to `"RoarSound"`, sorry

<b>Add the following configs to your Global & DistantRoarCustom to use the new features:</b>

### Global.json
```
  "WaveRoarFix.AutoAddUnused": true 
  // If true, vanilla ids for the unused wave roars will be internally added to DistantRoarCustom (can still be overridden)
```

### (Property.json -> DistantRoarCustom)
```
  "OnlyUseOverrides": false,
  "RoarSound": "Striker", // Accepted enums: Striker, Shooter, Birther, Shadow, Tank, Flyer, Immortal, Bullrush, Pouncer, Striker_Berserk, Shooter_Spread, None, OldDistantRoar, Custom
  "RoarSize": "Unchanged", // Accepted enums: Unchanged, Small, Medium, Big
  "IsOutside": "Unchanged" // BoolBase: "Unchanged", true, false
```

## 1.8.0 Patch Notes
- Implemented Hirnu's TumorShadowFix into ShadowCustom
- Fixed DistantRoarCustom not playing sounds when OnlyForSurvivalWave is true
- EEC Enemies can now use any vanilla survival wave roar

<b>Add the following configs to your ShadowCustom to use the new features:</b>
### (Model.json -> ShadowCustom)
```
  "Type": "LegacyShadows", // Accepted enums: LegacyShadows, NewShadows
  "IncludeThermals": true, // If "NewShadows", is visible in thermal sights
  "TumorVisibleFromBehind": true // If "NewShadows", tumors will become visible when viewed from the back
```

- Since R7, enemy IDs have been hardcoded to their wave roar sounds, and custom enemies would error/default to the Striker wave roar.

<details>
  <summary><b>Versions 1.7.9 - 1.7.0</b></summary>
<br>

## 1.7.9 Patch Notes
- hirnukuono recompile from GTFOModding GitHub v1.7.7 (seems to include pouncers)
- presents itself as v1.7.9 so u can test using this alongside EEC_I install
- fixes explosion damage
- fixes CustomScoutWaves
- most other features yet untested (all models, all abilities, all texture related stuff)
- testing feedback welcome, maybe do a pull request to EEC_I if success
- will deprecate this if EEC_I gets updated

## 1.7.8 Patch Notes
- Added PouncerCustom
- Updated to BepInEx 3.0.0

## 1.7.7 Patch Notes
- Resolved Various MarkerCustom Issue
- HealthInfo now sync lot more accurately
- Added Option to Resize MarkerCustom Elements `SpriteScale`, `TextScale`, `DistanceTextScale`

## 1.7.6 Patch Notes
- Improved Performance for LimbCustom
- Fixed Bug where enemies can't break door when DoorBreakerCustom is set in specific condition

## 1.7.5 Patch Notes
- Bleeding Now can be cured by medipack from other player

## 1.7.3-4 Patch Notes
- LiveEdit now work as intended

## 1.7.2 Patch Notes
- Health Info now sync Properly

## 1.7.1 Patch Notes
- Added `MarkerTextHealthBar~` settings to `MarkerCustom`
- Fixed Issue
  - ScannerCustom Performance Improvement
  - Shadows not being shown on termal scope
  - Networking nullrefs
  - Limb Destruction not working

## 1.7.0 Patch Notes
- Updated to Latest BepInExPack

</details>