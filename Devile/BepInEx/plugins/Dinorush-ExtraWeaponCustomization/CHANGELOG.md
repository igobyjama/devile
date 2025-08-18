## v3.7.3

**Features and Adjustments**

- Trigger
  - `null` and "Null" are now supported alternative names of "Invalid".
  - Changed the default empty trigger from "Invalid" to `null`.

**Bug Fixes**

- Misc
  - Fixed pierce weapons using incorrect distance between pierce hits and hitting in the wrong order

## v3.7.2

**Features and Adjustments**

- Armor Pierce, Shot Mod Debuff
  - Added field "GlobalID": Causes all players that apply the debuff to share the same modifier rather than creating separate ones.
    - Provided as an ID to support sharing across weapons/properties, as long as the fields are the same.

## v3.7.1

**Bug Fixes**

- Reference Property
  - Fixed not working at all

## v3.7.0

**Features and Adjustments**

- Auto Aim
  - Added new fields:
    - "UseTrigger": Changes the locking to only search enemies that have been triggered upon.
    - "Trigger": Inactive unless UseTrigger is enabled. Adds enemies triggered upon to the possible lock targets.
  - Added callback events (see new trigger):
    - Locked (Default): Invoked whenever auto aim is fully locked.
    - Unlocked: Invoked whenever auto aim is no longer fully locked.
    - New Lock: Invoked whenever auto aim fully locks onto a new target.
- Added new triggers:
  - Clip: Triggers whenever the ammo in the magazine changes.
  - Stagger: Triggers whenever an enemy is staggered.
  - Reference: Triggers whenever the referenced property invokes a callback event.
    - Only implemented by Auto Aim currently, but may add more in the future.

**Bug Fixes**

- Misc
  - Fixed search algorithms working incorrectly when rooms are on top of each other.

## v3.6.10

**Bug Fixes**

- General
  - Fixed normal (i.e. 0 hitsize) pierce shots having inconsistent hit detection

## v3.6.9

**Features and Adjustments**

- Stacking Mod Effects (e.g. Shot Mod, Fire Rate Mod)
  - Added field "CombineCap": Determines the maximum number of activations when CombineModifiers is used.
    - Differs from "Cap", which caps the total modifier rather than the stored activations.

**Bug Fixes**

- Multi Shot, Fire Shot
  - Fixed hit triggers not happening in several cases

## v3.6.8

**Bug Fixes**

- Armor Pierce
  - Fixed enemy limbs with armor type still counting as armor with a 1.0 multiplier

## v3.6.7

**Features and Adjustments**

- Fire Rate Mod
  - Melee weapons now also have their auto swing time scaled to remain the same based on charge time.

**Bug Fixes**

- Temp Properties
  - Fixed Override causing properties to run behavior they shouldn't in some cases

## v3.6.6

**Bug Fixes**

- Stacking Mod Effects (e.g. Shot Mod, Fire Rate Mod)
  - Fixed "OverrideStackType" not working correctly with "CombineModifiers".

## v3.6.5

**Features and Adjustments**

- Stacking Mod Effects (e.g. Shot Mod, Fire Rate Mod)
  - Added field "OverrideStackType": Determines how the modifier is calculated based on the trigger amount.
- Added new Trigger:
  - Health: Triggers whenever health changes, applying Amount based on current health.
    - Similar to HealthShotMod, but usable on anything with a trigger!

## v3.6.4

**Bug Fixes**

- Explosive
  - Fixed not applying self-damage

## v3.6.3

**Bug Fixes**

- Explosive
  - No longer affected by GtfXP's BulletResistance
  - Fixed triggering friendly fire voicelines from self-damage

## v3.6.2

- Removed debug logging for Projectile's "StatChanges"

## v3.6.1

**Features and Adjustments**

- Projectile
  - Added field "StatChanges": A list of stat changes to apply to the projectile over time.

## v3.6.0

**Features and Adjustments**

- Added new Effects:
  - ShotModDebuff: Applies a ShotMod on the enemy that affects all players and weapons.
  - ArmorShred: Reduces enemy armor for all players and weapons.
- Base Data
  - Added field "DebuffIDs" to specify which ShotModDebuffs and ArmorShreds apply to the weapon.
- Stack Type & Stack Layer
  - Separated Max from Min; no longer depends on the Effect's Mod to determine which to use.

**Bug Fixes**

- Auto Aim
  - Fixed reticle disappearing until re-wielding if removed by TempProperties
- Speed Mod, Spread Mod
  - Fixed some cases where reset would not work correctly
- Melee Landed Trigger
  - Fixed not triggering when hitting enemy corpses

## v3.5.10

**Bug Fixes**

- Damage Over Time
  - Fixed incompatibility with [DamageSync](https://thunderstore.io/c/gtfo/p/randomuserhi/DamageSync/)

## v3.5.9

**Bug Fixes**

- Projectile
  - Fixed it no longer working after a checkpoint

## v3.5.8

**Features and Adjustments**

- Damage Over Time
  - StackLimit no longer removes the oldest instance if it has more remaining damage than the new instance

**Bug Fixes**

- Misc
  - Fixed UseParentMod on multiple effects not functioning properly in some cases 

## v3.5.7

**Bug Fixes**

- Charge Exponent
  - Fixed it not applying at all
- Shrapnel
  - Fixed projectiles not rendering for other players

## v3.5.6

**Features and Adjustments**

- Explosive
  - Added field "HitClosestFirst": Hits enemies in order of ascending distance.

## v3.5.5

**Features and Adjustments**

- Trigger
  - Added a PerTarget trigger: Tracks an Activate trigger separate for each enemy, applying on its Apply trigger.
    - Requires hit-based triggers.
    - Can be formatted as "Per[Activate]On[Apply]" (e.g. "PerHitOnKill") or using object format with name "PerTarget".
  - ApplyDelay now accepts a list of delays, applying the stored activations for each timing.

**Bug Fixes**

- Fixed projectile's spawn-protection applying to players in front of the user rather than behind

## v3.5.4

**Bug Fixes**

- Fixed error that occurred when other players fired a gun
- Fixed melee weapons doing Unwield triggers twice

## v3.5.3

**Features and Adjustments**

- Trigger
  - Added an Unwield trigger.

## v3.5.2

**Features and Adjustments**

- Added new Effect:
  - SpeedMod: Applies a modifier to the user's movement speed.
- Explosive
  - Added field "EnableMineFX": Creates the tripmine explosion visual effect.

## v3.5.1

**Features and Adjustments**

- Ammo Mod, Ammo Regen
  - Added new field "BypassReserveCap": Ammo can be added to reserves past 100% capacity.

## v3.5.0

**Features and Adjustments**

- Added new Effects:
  - Health Shot Mod: Applies a modifier to shots/melees depending on the user's current health.
  - Shrapnel: Causes bullets to fire out from where bullets land. [Gun]
- Added new Trait:
  - Charge Exponent: Modifies the exponent applied to melee charge attacks. [Melee]

- Health Mod
  - Added new field "ApplyToTarget": Applies health changes to the player hit (if occurred on a hit trigger).
- Trigger
  - Added a Shrapnel Landed trigger and a Shrapnel damage type to accommodate Shrapnel.
- Misc
  - Custom shot behavior now now pulls from the firing weapon rather than held weapon for better mod compatibility.

**Bug Fixes**

- Health Mod
  - Fixed CancelRegen ignoring GtfXP's regen delay modifier
- Fire Shot
  - Fixed bullets visually coming from the weapon even when fired from another position
- Foam
  - Fixed enemies on clients immediately unfoaming
- Noise
  - Fixed UseNoiseSystem doing nothing if FakeAlertRadius <= WakeUpRadius

## v3.4.3

**Bug Fixes**

- Projectile
  - Fixed projectiles having 0 aim/hip spread

## v3.4.2

**Bug Fixes**

- Misc
  - Fixed an incompatibility with GTFOReplay

## v3.4.1

**Bug Fixes**

- Misc
  - Fixed some issues with the EWC logic overriding vanilla shot logic

## v3.4.0

**Features and Adjustments**

- Fire Rate Mod
  - Added new field "ForceUpdate": Forces the weapon to update its current shot cooldown when this effect triggers.
    - Useful for syncing FireRateMods with low durations to other clients, among other things.
- Projectile
  - Improved performance by checking for collisions less frequently the longer it lives.
    - Check rate changes from Frames/s to 20/s over 1s in the air.
- Misc
  - Improved shot performance of all weapons with custom data
    - All such weapons now purely use EWC logic, which seems to give ~30% performance boost with pierce guns

## v3.3.4

**Bug Fixes**

- Data Swap
  - Fixed an issue that occurred after returning to checkpoint, bricking the weapon

## v3.3.3

**Bug Fixes**

- Projectile 
  - Fixed nullref that occurred when other players' projectiles despawned

## v3.3.2

**Bug Fixes**

- Reference Property
  - Fixed several issues when used in tandem with Temp Properties' Override field
- Projectile
  - Fixed homing targeting the enemy hit when spawned by a FireShot on hit

## v3.3.1

**Features and Adjustments**

- Damage Trigger
  - Added field "IgnoreXpMod": Ignores GtfXP damage modifiers.

**Bug Fixes**

- Damage Trigger
  - Fixed GtfXP modifiers not being considered for bullet damage
- Misc
  - Fixed network effects with Init triggers causing null ref errors in the lobby
- Data Swap
  - Fixed GtfXP AmmoEfficiency applying inversely to weapons with DataSwap

## v3.3.0

**Features and Adjustments**

- Reference Trigger
  - Added field "ResetOnTrigger": Causes Activate triggers to apply as Reset triggers to Properties.
- Triggers
  - Moved "Apply" and "Cancel" to be Trigger Holder fields.
  - Moved "ConsumeThresholdOnActivate" field to Trigger Holder as "ConsumeThreshold".
  - Added Trigger Holder fields:
    - "Apply", "Cancel": As described above.
      - Their customization was not needed 99.9% of the time and this allows Reset triggers to use them.
    - "ConsumeThreshold": As described above.
    - "CancelReduceAmount": When nonzero, reduces stored triggers by the amount rather than clearing them.

**Bug Fixes**

- Foam
  - Fixed melee not applying foam bubbles to terrain
- Noise
  - Fixed not being usable on melee weapons
- Drop Trigger
  - Fixed not occurring on melee weapons
- Misc
  - Fixed melee causing errors when hitting terrain

## v3.2.8

**Features and Adjustments**

- Triggers
  - Added new trigger "Miss": Triggers after failing to land hits from a bullet/explosive.
    - Can use Damage Types to specify what types of hits avoid a miss.
    - Included by "RunHitTriggers" fields on Fire Shot and Multi Shot.
  - Kill
    - Now also occur as soon as kill hitmarkers appear, which should make it more responsive for clients.

**Bug Fixes**

- Triggers
  - Fixed MaxPerShot on Hit triggers counting terrain hits

## v3.2.7

- Removed accidental debug explosive graphics
    
## v3.2.6

**Features and Adjustments**

- Misc
  - Improved accuracy of search algorithms (used in Explosive, Projectile, etc.)
    - Hopefully Explosive failing to hit should not occur anymore. If it does, it (should) output position data to the log that might help debug it.

## v3.2.5

**Bug Fixes**

- Ammo Mod
  - Fixed overflowing magazine by 1 when adding ammo to a different weapon off of a hit/fire trigger

## v3.2.4

**Bug Fixes**

- Fixed custom weapon data causing SpecialCooldownTime to do nothing 

## v3.2.3

**Features and Adjustments**

- Health Mod
  - Negative heals now give visual feedback.

**Bug Fixes**

- Misc
  - Improved optimization for enemy/player search algorithms (used in Explosive, Projectile, etc.)

## v3.2.2

**Bug Fixes**

- Fixed errors that occurred when KillIndicatorFix was not installed

## v3.2.1

**Bug Fixes**

- Pierce Multi
  - Fixed *any* hit (bullet, explosive, or DoT) counting as a pierce, rather than only bullet hits
  - Fixed ModDamageType not applying

## v3.2.0

**Features and Adjustments**

- Enforce Fire Rate
  - Now works with Burst and Semi-Automatic weapons.
- Triggers
  - Added new triggers:
    - **Start Firing**: Triggers when the user starts firing, before the first shot fires. [Gun]
      - On burst guns, triggers at the start of a burst.
      - On semi-auto guns, triggers before each shot.
    - **End Firing | Stop Firing**: Triggers when the user stops firing, after the last shot fires. [Gun]
      - On burst guns, triggers at the end of a burst.
      - On semi-auto guns, triggers after each shot.

**Bug Fixes**

- Reserve Clip
  - Fixed incorrect burst weapon behavior when the true reserves were empty

## v3.1.0

**Features and Adjustments**

- Auto Aim
  - Added new fields:
    - "LockedColor": Color of the reticle when a target is fully locked and automatic aim should be used.
    - "LockingColor": Color that the reticle fades into when locking and remains at for locked targets when automatic aim should not be used.
    - "LockScale": Scalar applied to the reticle graphic size.
- Hit Taken & Damage Taken Triggers
  - No longer incompatible with CConsole

## v3.0.9

**Bug Fixes**

- Spread Mod
  - Fixed CombineModifiers instantly decaying visually, even if it actually decayed over time

## v3.0.8

**Features and Adjustments**

- Damage Types
  - Added type "Glue" to adjust Foam applications with Shot Mod.

## v3.0.7

**Features and Adjustments**

- Fire Shot
  - Added field "UserUseAimDir": If FireFrom is set to User, offsets fire from the center of view rather than the original shot.
    - Previously always true. When false, naively uses the last ray traced, primarily for use directly on Fire/Hit triggers.

**Bug Fixes**

- Custom Shot
  - Fixed vanilla tracers still being created if the shot wasn't canceled entirely

## v3.0.6

**Features and Adjustments**

- Damage Over Time, Explosive, Fire Shot
  - Added field "UseParentShotMod": Uses the parent shot's modifiers and group modifiers, otherwise copies them into new instances.

**Bug Fixes**

- Noise
  - Fixed SoundID not working

## v3.0.5

**Features and Adjustments**

- Damage Over Time
  - Added field "CalcShotModsPerTick": Applies shot mods per tick rather than at the time of firing.
- Damage Over Time & Explosive
  - Can now use DOT and Explosive-type triggers respectively if explicitly specified.
    - There are no guards against infinite loops. The developer must implement guards themselves.
  - Increased precision on damage and stagger data sent over the network.
    - Fixes lower values rounding to unintended values, e.g. 1.0 stagger rounding to ~0.75.
- Damage Trigger
  - Added field "ClampToHealth": Clamps damage to the max health of the target.
    - Enabled by default (same as before).

**Bug Fixes**

- Damage Over Time
  - Fixed stagger being unaffected by shot modifiers
- Projectile
  - Fixed shot modifiers being pulled from the last shot fired
- Bullet Landed & Charge Landed Triggers
  - Fixed applying when a directly struck enemy died

## v3.0.4

**Bug Fixes**

- Custom Shot Behavior
  - Fixed weapons effects applying to other things they shouldn't, e.g. sentries
- Damage Over Time
  - Fixed error that could sometimes occur if the team wiped before a DOT finished

## v3.0.3

**Features and Adjustments**

- Damage Over Time
  - Moved glow position to be higher (prioritizes chest -> head -> base).
- Explosive
  - No longer causes hits if damage dealt is 0.
    - Prehit triggers can still occur before ShotMods are taken into account.

**Bug Fixes**

- Explosive
  - Fixed hit detection failing in some direct hit scenarios
- Stack Mods
  - Fixed override Stack Layer not applying

## v3.0.2

**Bug Fixes**

- Trigger
  - Fixed melee not setting the correct damage type

## v3.0.1

**Bug Fixes**

- Fixed hitting player components without damageable hitboxes
- Fixed errors from other players swapping weapons

## v3.0.0

**Features and Adjustments**

- Added new Effects:
  - Spread Mod: Applies a spread modifier.
  - Noise: Creates detectable noise where triggers occur.
  - Reference Trigger: Sends Apply and Reset triggers to other properties.

- Accelerate
  - Renamed field "EndDamageMod" to "EndShotMod" - previous name will remain supported.
  - Renamed field "DamageStackLayer" to "ModStackLayer" - previous name will remain supported.
  - Added new fields
    - "ModStatType": Specifies whether to modify Damage, Precision, or Stagger.
    - "ModDamageType": The damage type to restrict stat modifications to.
    - "StoreModOnGroup": Stores the stat modification on the shot group.
      - See wiki for details.
- Damage Mod
  - Renamed to Shot Mod - previous name will remain supported.
  - Now stores modifications on shots themselves, rather than calculating on hit.
    - This makes them work much better with projectiles and delayed effects.
  - Added new fields:
    - "StatType": Specifies whether to modify Damage, Precision, or Stagger.
    - "DamageType": The damage type to restrict stat modifications to.
    - "StoreOnGroup": Stores the stat modification on the shot group.
      - See wiki for details.
    - "CalcOnHit": Legacy support, works as it did previously.
- Damage Mod Per Target
  - Renamed to Shot Mod Per Target - previous name will remain supported.
  - Now stores modifications on shots themselves, rather than calculating on hit.
  - Added new fields:
    - "StatType": Specifies whether to modify Damage, Precision, or Stagger.
    - "DamageType": The damage type to restrict stat modifications to.
    - "StoreOnGroup": Stores the stat modification on the shot group.
      - See wiki for details.
    - "CalcOnHit": Legacy support, works as it did previously.
- Damage Over Time, Explosive
  - Renamed field "IgnoreDamageMods" to "IgnoreShotMods" - previous name will remain supported.
  - "IgnoreShotMods" now ignores the precision multiplier from Tumor Multi.
- Data Swap
  - Added field "EndFiring": Forces the weapon to stop firing even if the fire mode is the same.
    - Useful when swapping on a hit trigger.
- Pierce Multi
  - Added field "ModDamageType": The damage type to restrict damage modifications to.
    - Set to "Bullet" by default to keep backwards compatibility.
- Projectile
  - Ricochet now bounces up to 3 times in one frame to reduce the possibility of it going through walls.
  - Added new fields:
    - "RicochetSpeedMod": Modifier applied to projectile speed upon ricocheting.
    - "RicochetSpeedAngleFactor": Fraction of RicochetSpeedMod that is determined by the bounce angle.
      - Perpendicular bounces apply the fraction fully, while parallel bounces apply none.
- Silence
  - Modified "CrossDoors":
    - Renamed to "CrossDoorMode" - previous name will remain accepted
    - Now accepts values "Normal", "None", or "NoPenalty". Default is "Normal".
    - true/false value is deprecated. true is interpreted as "Normal".
- TumorMulti
  - Now ignored by IgnoreShotMods on other properties due to internal shot modifier changes.
- Trigger
  - Added Cancel trigger category. Acts like Reset but doesn't reset the parent property.
  - Refactored fields for categories. Now ALL categories inherit the following fields:
    - "Cap", "Chance", "Threshold", "Cooldown", "CooldownThreshold", "ResetDelay"
    - Specify a category's field by prefixing the name, e.g. "ApplyThreshold".
  - Added new fields:
    - "ConsumeThresholdOnActivate": When Activate occurs, decreases tracked activations by Threshold.
    - "ApplyAboveThreshold": Only applies the stored activations that were stored when or after Threshold was reached.
    - "CancelDelay": Delay in seconds after a Cancel trigger occurs before the cancel applies.
- Bullet Landed & Charge Landed Triggers
  - Now support activating on terrain only by appending "Terrain" to the name, e.g. "BulletLandedTerrain".
- Kill Triggers
  - Host now also benefits from the allowed delay on enemy kills.
  - Added fields:
    - MaxDelay: The maximum allowed amount of time since the enemy was hit before it died.
      - Previously always 0.5s.
    - RequireDidKill: Requires the parent weapon to have your last hit on the target.

- Misc.
  - Removed KillIndicatorFix as a dependency since kill tracking is done interally now.

**Bug Fixes**

- Damage Mod, Damage Mod Per Target, Fire Rate Mod, Recoil Mod
  - Fixed stacks decaying faster than they should with Combine Modifiers.
- Damage Over Time, Damage Mod Per Target
  - Fixed errors with PreHit triggers
- Projectile
  - Fixed RicochetOnHit not appearing on the template.
- Reserve Clip
  - Fixed some cases where the weapon would not automatically reload.
- Misc.
  - Fixed delayed logic not applying exactly when it should in edge cases.

## v2.3.1

**Bug Fixes**

- Pierce Multi
  - Fixed not applying to Multi Shot, Fire Shot, or Thick Bullet

## v2.23.0

**Features and Adjustments**

- Auto Aim
  - Reticle fades away at its last location rather than moving to the center of the screen.
- Damage Over Time
  - Added new fields:
    - "EndDamageFrac": Specifies the portion of damage to be dealing at the end of duration.
    - "Exponent": The exponent used to interpolate from 1 at the beginning to EndDamageFrac at the end.
- Damage Type Triggers
  - Added fields:
    - "UniqueCap": Maximum number of activations allowed per unique target.
    - "UniqueConsumeOnTrigger": Consume UniqueThreshold counts when the trigger occurs.
      - Previously always enabled.
- Enforce Fire Rate
  - No longer spawns tracers for extra shots (to improve performance slightly).
- Trigger
  - Added new Trigger "Setup": Triggers when entering the level.

**Bug Fixes**

- Hit Triggers
  - Fixed melee not firing triggers when landing non-direct hits
- Projectile
  - Fixed cases where ricochet projectiles with HitSizeWorld > 0 would go through walls

## v2.22.1

**Features and Adjustments**

- Trigger
  - Added new movement-based triggers:
    - Crouch/CrouchEnd - Triggers when crouching or standing respectively.
    - Sprint/SprintEnd - Triggers when starting or ending sprint respectively.
    - Jump/JumpEnd - Triggers when jumping/falling or landing respectively.

## v2.22.0

**Features and Adjustments**

- Trigger
  - Damage Type Triggers
    - Added field "MaxPerShot": Specifies the number of times the trigger may apply for a single shot/pellet.
    - Now allows OR specifications in types using the pipe character '|'.
      - E.g. "HitEnemy|Player" occurs on an enemy or player hit. The trigger name can be specified anywhere.

## v2.21.2

**Features and Adjustments**

- Misc
  - Updated APIs for [GTFOReplay](https://thunderstore.io/c/gtfo/p/randomuserhi/GTFOReplay/) to use.

## v2.21.1

**Bug Fixes**

- Auto Aim
  - Fixed an issue with Weakspot targeting that caused undefined weakspot prioritization on targets with multiple

## v2.21.0

**Features and Adjustments**

- Auto Aim & Projectile
  - Weakspot targeting now aims for the closest (angle) weakspot if all are blocked by body parts.
    - May help in cases where body parts overlap but the weakspot can still be hit.

**Bug Fixes**

- Data Swap
  - Fixed not applying or clearing properly for other players when used with TempProperties
- Projectile
  - Fixed friendly homing weapons not homing correctly, especially when using AutoAim homing

## v2.20.0

**Bug Fixes**

- Foam
  - Fixed enemy unfoaming visuals not scaling with FoamTime
  - Fixed FoamTime not applying if an environment bubble applies the last foam to an enemy
  - (Potentially) Fixed clients' inability to see Foam

## v2.19.5

**Bug Fixes**

- Trigger
  - Fixed ApplyDelay and ResetDelay not functioning

## v2.19.4

**Features and Adjustments**

- Trigger
  - Added field "ApplyOverrideAmount": Forces the total applied amount to match this value.
    - Useful primarily for Threshold, when you want to apply less or more than the required amount.

## v2.19.3

**Bug Fixes**

- Projectile
  - Fixed incorrect visual rotation lerp behavior

## v2.19.2

**Features and Adjustments**

- Projectile
  - Added field "HitSizeFriendly": The hit detection radius in meters for players.
    - Previously, always matched "HitSize".

## v2.19.1

- Added missing changelog for v2.19.0

## v2.19.0

**Features and Adjustments**

- Added new Trait:
  - "HitmarkerCooldown": Sets a cooldown on how frequently the weapon can generate hitmarkers.
- Foam
  - Added new field "BubbleLifetime": Specifies how long bubbles last before disappearing.

**Bug Fixes**

- DamageOverTime
  - Fixed DamageOverTime breaking forever in some rare cases when applied to players.
- Explosive
  - Fixed "ScreenShakeInnerRadius" being read as "ScreenShakeRadius"
- Foam
  - Fixed client bubbles not having correct visual stats (size/expand speed).

## v2.18.4

**Bug Fixes**

- Auto Aim 
  - Fixed yet more nullrefs that occurred when used against crystalline.

## v2.18.3

**Bug Fixes**

- Projectile
  - Fixed critical error in collision logic when speed approached 0.

## v2.18.2

**Bug Fixes**

- Auto Aim
  - Fixed nullrefs that occurred when used against crystalline with "Weakspot" mode.

## v2.18.1

**Features and Adjustments**

- Fire Shot
  - Changed field "ApplySpreadPerShot" to "Spread": Now specifies the spread of the shots. Uses the weapon's spread if less than 0.
    - Previous name is accepted, but deprecated.
- Multi Shot
  - Changed field "ApplySpreadPerShot" to "Spread": Now specifies the spread of the shots. Uses the weapon's spread if less than 0.
    - Previous name is accepted, but deprecated.
  - Renamed field "IgnoreSpread" to "UseAimDir" for clarity.
    - Previous name is accepted.

**Bug Fixes**

- Projectile
  - Fixed ricochet not being synced to other clients.

## v2.18.0

**Features and Adjustments**

- Fire Shot
  - Added new fields:
    - "RunHitTriggers": Enables running hit triggers (e.g. Hit, BulletLanded) from bullets fired by this property.
    - "FireFrom": Determines where and in which direction the shot is fired.
  - Deprecated field "FireFromHitPos"; use "FireFrom" instead.
- Multi Shot
  - Added new field "RunHitTriggers": Enables running hit triggers (e.g. Hit, BulletLanded) from bullets fired by this property.
- Projectile
  - Added new fields:
    - "RicochetCount": The number of times the projectile can ricochet off walls.
    - "RicochetOnHit": Allows the projectile to ricochet off targets hit.
  - Deprecated field "RunHitTriggers"; use it on Fire Shot or Multi Shot instead.
- Triggers
  - Added new trigger "ChargeLanded": Triggers when melee hits anything, applying an activation for the corresponding charge strength.
- Charge Trigger
  - Removed deprecated field "Scale".

**Bug Fixes**

- Projectile
  - Fixed a nullref that could occur when projectiles went too far out of bounds.

## v2.17.5

**Bug Fixes**

- Explosive
  - Fixed hitting through damaged or foamed doors

## v2.17.4

**Bug Fixes**

- DamageMod, DamageModPerTarget, FireRateMod, RecoilMod
  - Fixed "Cap" not applying when "CombineModifiers" is used.

## v2.17.3

**Features and Adjustments**

- Explosive
  - Added new screen shake fields:
    - "ScreenShakeIntensity": Strength of screen shake applied by explosions.
    - "ScreenShakeFrequency": Frequency of the screen shake effect.
    - "ScreenShakeDuration": Duration of the screen shake effect.
    - "ScreenShakeInnerRadius": Radius in which the screen shake applies at full strength. Uses explosion inner radius if 0.
    - "ScreenShakeRadius": Maximum radius in which the screen shake applies. Uses explosion radius if 0.
      - "Exponent" is used to scale between the two radii.
  - Added option in the Config file to disable screen shake from this.
- TumorMulti
  - Added field "OverrideWeakspotMulti": Overrides the tumor's weakspot multiplier, setting the total multiplier to "TumorDamageMulti".

**Bug Fixes**

- Misc
  - Fixed C-Foam Tripmine behavior being modified to do glue damage independent of target health.

## v2.17.2

**Features and Adjustments**

- Misc
  - Exposed shot APIs for [GTFOReplay](https://thunderstore.io/c/gtfo/p/randomuserhi/GTFOReplay/) to use.

## v2.17.1

**Features and Adjustments**

- DamageMod, DamageModPerTarget, FireRateMod, RecoilMod
  - Renamed fields:
    - "RefreshPrevious" to "CombineModifiers"
    - "DecayTime" to "CombineDecayTime"
      - "DecayTime" is still accepted, but "RefreshPrevious" is **not**.
- Misc
  - Adjusted damage APIs

## v2.17.0

**Features and Adjustments**

- DamageMod, DamageModPerTarget, FireRateMod, RecoilMod
  - Added new fields: 
    - "RefreshPrevious": Trigger applications refresh existing stacks.
    - "DecayTime": Only applies when RefreshPrevious is enabled. Specifies the time it takes for one stack to decay.
- Misc
  - Exposed APIs for [GTFOReplay](https://thunderstore.io/c/gtfo/p/randomuserhi/GTFOReplay/) to use.

**Bug Fixes**

- Projectile
  - Fixed client projectiles pulling the wrong projectile property.
    - Would usually make them not appear at all, so this fixes that too.

## v2.16.3

**Features and Adjustments**

- Projectile
  - Renamed field "Speed" to "MinSpeed".
    - "Speed" is still an accepted alternate name.
  - Added new field "MaxSpeed": Specifies a maximum speed.
    - Only MinSpeed is used if MaxSpeed < MinSpeed (preserves previous behavior)

**Bug Fixes**

- Auto Aim & Hold Burst
  - Shot/burst cooldown is now based on the last fired shot rather than the canceled shot.
  - Fixed shot/burst cooldown modifiers not applying on canceled shots.

## v2.16.2

**Features and Adjustments**

- Explosive
  - GtfXP weapon damage modifiers now affect friendly fire damage.
- Foam
  - Now applies damage modifiers to direct hit foam applied.
  - Added new fields:
    - "IgnoreDamageMods": Ignores damage modifiers when applying direct hit foam.
    - "BubbleIgnoreModifiers": Bubbles ignore modifiers applied on direct hits (weakspot, armor, damage mods).
      - Enabled by default (same behavior as before)

## v2.16.1

**Bug Fixes**
- Foam
  - Fixed Foam fields not pulling from the correct property when multiple Foam or Projectile properties existed.

## v2.16.0

**Features and Adjustments**

- Foam
  - Added new field "BubbleOnDoors": Allows bubbles to be created on doors.
  - Foam Time now affects bubbles.
  - Foam Time is now properly supported for various different sources.
    - On unfoamed targets, sources contribute an amount of foam time proportional to their foam amount.
    - On foamed targets, an individual source can never extend foam time past its own value.

**Bug Fixes**

- Auto Aim & Projectile Homing
  - Fixed client locking/homing still targeting broken weakspots. 
- Damage Type Triggers
  - Fixed doors that had been hit with foam counting for Lock type triggers.
- Explosive
  - Fixed a crash that occurred when hitting something with a Hit trigger.
- Foam
  - Now properly foams doors.

## v2.15.1

**Features and Adjustments**

- Foam
  - Added new fields:
    - FoamTime: Specifies the time targets will be foamed for when foamed by this effect's direct hits.
    - FoamTimeType: Determines how FoamTime interacts with the target's normal foam time.
      - Naive; stable only for foam effects with the same values. Different foam effects (including bubbles) will override with their own logic!
    - IgnoreBackstab: Ignores backstab when calculating direct hit foam applied.
      - Previously was always true.
- Triggers
  - Added new damage types
    - Foamed: Included when the target is foamed.
    - Unfoamed: Included when the target is not foamed.
      - Players and Locks are considered unfoamed.
  - Prehit
    - Now includes backstab multipliers for effects that utilize it.

**Bug Fixes**

- Explosive
  - Fixed a crash that occurred when hitting something with the BulletLanded trigger.

## v2.15.0

**Features and Adjustments**

- Added new Effect:
  - Foam: Applies foam where bullets land.
- HealthMod
  - Added new field "StopBleed": Stops EEC bleeds when the effect is triggered.
- Projectile
  - Adjusted HomingSetting.StopSearchMode "NoValid" flag
    - Renamed to "Invalid". "NoValid" is still accepted for backwards compatibility.
    - Now only stops search if a target is not found when a search is attempted.
      - Fully separates it from "Dead" since you can combine them as needed.
- Triggers
  - Added new triggers:
    - "HitTaken": Applies when the user takes damage.
    - "DamageTaken": Applies when the user takes damage, scaling with the damage taken.

## v2.14.2

**Features and Adjustments**

- Ammo Regen
  - Added new field "ResetWhileFull": Sets accumulated buffers to 0 when they are unable to apply.
- Projectile
  - Adjusted HomingSetting.StopSearchMode
    - "Dead" now only stops search after a homing target dies.
    - Added flag "NoValid" which stops search if there is no homing target at any point (old "Dead" behavior).

## v2.14.1

**Bug Fixes**

- Projectile
  - Fixed Hit & Kill triggers not working when TempProperties existed on the weapon

## v2.14.0

**Features and Adjustments**

- Ammo Mod
  - Now supports melees. "ReceiverSlot" must be specified.
- Damage Over Time
  - Added Glow fields ("GlowColor", "GlowIntensity", "GlowRange")
- Explosive
  - Added field "Exponent": The exponent used in damage falloff calculation.
  - Added field "GlowIntensity"
- Fire Shot
  - Added new fields:
    - "FireFromHitPos": Fires bullets from the position and angle they landed at.
    - "HitTriggerTarget": When used with "FireFromHitPos" and a position-based trigger, allows shots fired to hit the same target they were triggered on.
- Projectile
  - Added field "GlowIntensity"
  - Removed alternate names "Color" and "Range" from Projectile's "GlowColor" and "GlowRange".

**Bug Fixes**

- Fire Shot, Multi Shot
  - Fixed other players' shotguns having higher spread than they should.
- Reference Property
  - Fixed it failing to be read from the JSON in object form

## v2.13.1

**Features and Adjustments**

- Charge Trigger
  - "Min" and "Max" fields renamed to "MinRequired" and "MaxRequired" respectively.
  - Added new fields:
    - "Min": Modifier applied to trigger amount at MinRequired charge.
    - "Max": Modifer applied to trigger amount at MaxRequired charge.
    - "Exponent": Exponent applied when between MinRequired and MaxRequired.
  - Deprecated field "Scale", since its effect can be done by other fields.

**Bug Fixes**

- Bullet Landed Trigger
  - Fixed applying twice when hitting something
- Charge & Damage Trigger
  - Fixed them being entirely replaced with Hit triggers

## v2.13.0

**Features and Adjustments**

- Projectile
  - Added new field "ApplyAttackCooldown": Hits cause enemies to suffer attack cooldowns, preventing usage of tongues and canceling shooter barrages.
    - Previously always on.

**Bug Fixes**

- BackstabMulti
  - Fixed it not applying at all from v2.12.0 changes.
- Hit Trigger
  - No longer causes Temp Properties-applied Projectile or ThickBullet to modify the triggering bullet after piercing a target.

## v2.12.0

**Features and Adjustments**

- New Effect: FireShot
  - Fires a shot (without recoil or sound).
- Projectile
  - Added new field "RunHitTriggers": Hits cause hit triggers to occur.
    - Previously always on.
- Triggers
  - Added new Trigger "PreHit": Applies before damage calculations run.
  - Added new fields:
    - ResetDelay: Delay in seconds after a Reset trigger occurs before the reset is applied.
    - ResetResetDelay: Delay in seconds before Reset triggers are reset.
      - Relevant when used with the "UniqueThreshold" field.
  - Hit, Damage, Charge
    - Added new field "UniqueThreshold": The minimum amount of activations on an individual enemy that must occur before the trigger runs.

**Bug Fixes**

- Misc
  - Fixed some IL2CPP warnings printing to the console.

## v2.11.2

**Bug Fixes**

- Ammo Regen
  - Fixed some cases where it would remain active on second drop onwards.
- Data Swap
  - Fixed some magazine rounding issues.

## v2.11.1

**Bug Fixes**

- Temp Properties
  - Fixed ResetTriggersOnEnd not applying.
- Misc
  - Fixed properties not getting cleared properly when swapping weapons with CConsole.

## v2.11.0

**Features and Adjustments**

- All
  - Added new field "ID": An optional unique identifier for use by ReferenceProperty.
    - Only unique within its weapon's property list.
- Added new property "ReferenceProperty":
  - Directly references another property by ID.
    - Cannot reference properties on other weapons.
    - Can preserve the referenced property across Temp Properties.
  - Can be implicitly added without an object block by directly using an ID as a property.
- Projectile
  - Added new field "HitFromOwnerPos": Hit direction uses the owner's position relative to the target.
    - Useful to prevent homing projectiles from dealing back damage when curving behind enemies.

**Bug Fixes**

- Misc
  - Fixed some IL2CPP warnings printing to the console.

## v2.10.2

**Bug Fixes**

- Projectile
  - Fixed model scale having extreme effects on projectile size

## v2.10.1

**Features and Adjustments**

- Projectile
  - Added new field "TrailCullOnDie": Trails disappear immediately when the projectile dies.
    - Default is true, although it varied by projectile type in the past.
- Triggers
  - Most hit-based code now check that an enemy has health before applying hit effects.
    - This prevents hit effects from running on enemies that died moments ago.

**Bug Fixes**

- Ammo Mod
  - Fixed having +1 bullet in the mag in some cases where the trigger ran at the same time the gun was fired.
- Projectile
  - Fixed glow not working on projectiles without an innate glow effect.
- Temp Properties
  - Fixed some properties running local code when triggered for a remote player.

## v2.10.0

**Features and Adjustments**

- Damage Over Time
  - Removed "Stacks" as a valid field.
- Projectile
  - Added new fields:
    - "TrailColor"
    - "TrailWidth"
    - "TrailTime"
    - "HitCooldown": Time before the projectile can hit the same enemy again.
    - "HitIgnoreWallsDuration": Time after a hit where the projectile ignores walls.
      - Useful for homing projectiles to avoid dying to hitting the ground immediately after piercing an enemy.
  - Added new HomingSettings field:
    - "SearchStayOnTarget": Forces the projectile to home on its current target until it dies.
  - Deprecated "Color" and "Range" as valid names for "GlowColor" and "GlowRange" respectively, given similarities to Trail fields.

**Bug Fixes**

- Accelerate, Fire Rate Mod
  - Fixed fire rate not syncing for other players.

## v2.9.0

**Features and Adjustments**

- Explosive
  - Now accepts all triggers. Triggers without a position component explode directly on the user.
- Triggers
  - Field "Activate" now also supports the alt. name "Name".
  - Added new field "ApplyDelay": Delay before applications are actually applied.
  - Removed DamageType field from triggers - it is now only specified in the name.
  - Added new damage types:
    - Body
    - Armor
    - Flesh
    - Enemy
    - Player
    - Lock
      - Players & Locks always use Body and Flesh types.
- All Individual Triggers
  - Added field "Amount": The amount of activations applied when triggered.
    - This is a field for the expanded trigger objects of "Hit", "Reload", etc.

**Bug Fixes**

- Ammo Mod, Ammo Regen
  - No longer reduces ammo to 100% when above max capacity. Does not grant positive ammo change above max capacity.
- Enforce Fire Rate
  - Other players with this trait now stop firing when they should.
- Projectile
  - Potentially fixed an issue where projectiles occasionally wouldn't spawn if another player fired projectiles of the same type

## v2.8.0

**Features and Adjustments**

- Added new Trait:
  - Ammo Regen: Continually modifies magazine/reserve ammo counts. 
- Wall Pierce
  - Added new field "RequireOpenPath": Requires all doors to be open (or opening) to the target, not just security doors.

**Bug Fixes**

- Enforce Fire Rate
  - Fixed bonus shots not incrementing Extra Recoil Data scaling progress

## v2.7.1

**Bug Fixes**

- Data Swap
  - Fixed inconsistent reload behavior with AutoReloadPlus
- Stack Layer
  - "Max": Fixed modifiers of 1 still applying.
  - "Override": Fixed inactive modifiers still overriding.

## v2.7.0

**Features and Adjustments**

- Ammo Mod
  - Added field "UseRawAmmo": Grants raw ammo values instead of whole bullets.
  - Added field "ReceiverSlot": Determines which weapon should receive the ammo.
- Damage Over Time
  - Replaced field "Stacks" with "StackLimit": Determines the maximum number of DOT instances for a single target.
    - "Stacks" is deprecated; support will be removed in a future version.
- Enforce Fire Rate
  - Modified to fire more bullets instead of merely scaling damage/bullet cost.
    - Ensures consistent behavior for triggers and breaking limbs.
- Health Mod
  - Added field "CancelRegen": Incurs damage taken regen delay if enabled.
    - Previously was disabled for positive heals and enabled for negative heals.
- Stack Type
  - Added "Max" | "Min": Picks the highest or lowest modifier (if the mod is > 1 or < 1 respectively).
- Triggers
  - Added field "CooldownThreshold": Minimum number of activations before Cooldown applies.
  - Added field "ActivateResetDelay": Delay after last activation before stored triggers are cleared.
  - Added field "CooldownOnApplyThreshold": Minimum number of applications before CooldownOnApply applies.
  - Added field "ApplyResetDelay": Delay after last application before the counter for cooldown threshold is reset.

**Bug Fixes**

- Data Swap
  - Updates reticle size on archetype swap
- GtfXP Compatibility
  - Melees apply melee damage modifiers rather than gun damage modifiers to their DOTs and Explosives.
  - Explosive is now affected by player ExplosionResistance.

## v2.6.0

**Features and Adjustments**

- Accelerate
  - Changed to an Effect. EndFireRate/ShotDelay apply a modifier based on `[EndFireRate]/[BaseFireRate]`.
  - Added field "EndFireRateMod": Alternative to other fields that specifies the modifier applied to fire rate at full acceleration.
  - Added field "FireRateStackLayer": Determines how this effect stacks with other fire rate modifiers.
  - "DamageStackLayer" alternative names replaced with "DamageLayer".
- Bio Ping
  - Changed to an Effect.
  - Added field "CooldownPerTarget": Specifies an individual cooldown per enemy.
  - Added field "Trigger": Same as any other Effect.
    - Default changed to "Hit" rather than "BulletHit".
  - Deprecated field "DamageType". This is specified by the Trigger now.

**Bug Fixes**

- Accelerate
  - Fixed continuous growth ("AccelExponent": "e") not applying
  - Fixed reset triggers not being synced

## v2.5.0

**Features and Adjustments**

- Auto Aim
  - Added field "TargetPriority": Determines how locking chooses an enemy.
  - Added field "HomingOnly": Disables automatic aiming. Should only be used with homing projectiles.
- Projectile
  - Added field "HomingSettings": An object of many customizeable fields to add homing to projectiles.
  - Further improved performance for piercing projectiles
- Triggers
  - Added field "ResetPreviousOnly": Reset triggers only reset previous triggers.
    - Useful if you want to apply on a trigger but also clear any previously applied occurrences.

**Bug Fixes**

- Projectile
  - Fixed a few networking issues
- Wall Pierce
  - Can now hit padlocks through walls
  - Can now hit padlocks with Projectile
  - Can now hit padlocks using the wider hitbox with ThickBullet

## v2.4.6

**Bug Fixes**

- Explosive
  - Fixed hitting enemies behind the door a bullet landed on

## v2.4.5

**Features and Adjustments**

- Projectile
  - Now stores properties on fire rather than using current properties on impact.
    - TempProperties activating/resetting won't affect projectiles in flight.

## v2.4.4

**Features and Adjustments**

- Ammo Cap
  - Added field "ApplyOnDrop": Apply ammo cap modifiers on drop (was always true).
- Explosive
  - Field "SoundID" now also accepts names of sounds. 

**Bug Fixes**

- Ammo Cap
  - Fixed AmmopackRefillRel and AmmopackRefill not being accepted names for the field.

## v2.4.3

**Bug Fixes**

- Bio Ping
  - Fixed DamageType not being customizable

## v2.4.2

**Features and Adjustments**

- Added new Trait:
  - Bio Ping: Damaging an enemy applies a Bio Tracker ping.
- Projectile
  - Improved performance for piercing projectiles

## v2.4.1

**Bug Fixes**

- Ammo Cap
  - Fixed incompatibility with GtfXP's ammo level up bonuses
- Misc
  - Removed leftover debug logging

## v2.4.0

**Bug Fixes**

- Data Swap
  - Fixed it not functioning on join-in-progress
- Silence
  - Fixed it not working for clients
- Trigger
  - Fixed networked triggers repeatedly sending resets back to each other
- Misc
  - Fixed properties not applying for clients

## v2.3.4

**Bug Fixes**

- Multi Shot
  - Fixed CancelShot having issues when dealing damage/used with AccuracyShow
  - Fixed CancelShot incompatibility with Projectile

## v2.3.3

**Bug Fixes**

- Projectile, Thick Bullet
  - Fixed them failing to work when not aiming at anything (or always for Projectile)

## v2.3.2

**Features and Adjustments**

- Multi Shot
  - Added new field "CancelShot": Cancels the shot the gun normally fires.

**Bug Fixes**

- Multi Shot
  - Fixed initial shot spread reduction not applying to ApplySpreadPerShot

## v2.3.1

**Bug Fixes**

- Multi Shot
  - Fixed ApplySpreadPerShot not working when PierceBugFix is installed

## v2.3.0

**Features and Adjustments**

- Added new Trait:
  - Multi Shot: Fires additional bullets per shot at given offsets.
- Thick Bullet
  - Now makes impact FX when used with WallPierce.
- Trigger
  - Added field "Threshold": Only allows triggers once accumulated triggers have reached the threshold.
- Misc
  - Force Create Template option in the config now overwrites the file if it exists.

**Bug Fixes**

- Projectile
  - Fixed the wrong projectiles being destroyed occasionally when two players initially fired near the same time
- Misc
  - Fixed search algorithms failing sometimes against flyers and tumors
  - Fixed third person syncs failing to occur

## v2.2.9

**Bug Fixes**

- PartialData support fixed

## v2.2.8

**Bug Fixes**

- Auto Aim, Data Swap
  - Fixed the traits not working at all

## v2.2.7

**Features and Adjustments**

- Thick Bullet
  - Now makes impact FX if the bullet hits the environment

**Bug Fixes**

- Data Swap
  - Fixed the trait breaking on the second drop onwards with the same weapon
- Projectile
  - Improved acceleration/gravity logic to work consistently for any frame rate
  - Fixed desynced acceleration for other players' projectiles
- Explosive/Projectile
  - Fixed their inability to damage teammates

## v2.2.6

**Features and Adjustments**

- Thick Bullet
  - Added compatibility with WallPierce
- Tumor Damage Multi
  - Added field "BypassCap": Allows the weapon to bypass tumor damage caps.
- Misc
  - Search algorithms (projectiles, explosives) now consider weakspots slightly closer to make weakspot hits a little more consistent

**Bug Fixes**

- Projectile
  - Fixed erroneous line of sight logic on large projectiles
  - Now checks for hits before moving, which can fix them going through walls and doors when on low frames
- Misc
  - No longer generates a folder in the base game directory when no datablocks are detected

## v2.2.5

**Bug Fixes**

- Projectile
  - Fly once more

## v2.2.4

**Bug Fixes**

- Explosive
  - Fixed issues hitting nightmare enemies
- Projectile
  - Fixed some nullrefs and other errors in rare circumstances

## v2.2.3

**Bug Fixes**

- Misc
  - Fixed damage falloff not calculating correctly for effects (e.g. DOT, Explosive)
  - Fixed nullref that occurred sometimes from Projectile and Explosive

## v2.2.2

**Bug Fixes**

- Auto Aim
  - Fixed locking enemies regardless of invisiblility or Tag Only field

## v2.2.1

**Bug Fixes**

- Silence
  - Fixed WakeupRadius not working if AlertRadius was not bigger than it

## v2.2.0

**Features and Adjustments**

- Explosive
  - Added field "Glow Fade Duration": Sets the time it takes for the glow to linearly fade at the end of its duration.
- Temp Properties
  - Now immediately triggers added properties with the same trigger as it.

**Bug Fixes**

- Data Swap
  - Fixed errors that occurred when ExtraRecoilData is not installed
- Temp Properties
  - Fixed some properties using Invalid trigger support causing errors
- Misc
  - Fixed networked triggers not specifying which property was triggered

## v2.1.3

- Pushed v2.1.2 without updating .dll :\(

## v2.1.2

**Bug Fixes**

- Auto Aim
  - Fixed inconsistent logic with verifying that the current lock is valid

## v2.1.1

**Bug Fixes**

- Data Swap
  - Fixed compatibility with ExtraRecoilData

## v2.1.0

**Features & Adjustments**

- Added new Trait:
  - Silence: Modifies the stealth properties for firing. [Gun]
    - Like mccad's plugin, but offers a couple new features.
- Audio Swap
  - Renamed to "Data Swap". Now also allows swapping the Archetype of the weapon.
- Auto Aim
  - Added a field to the config file to adjust how frequently it searches for targets.
  - Now checks for line of sight to the lock-on point to avoid locking onto enemies behind walls.
- Temp Properties
  - Now automatically triggers and resets effects/traits with invalid triggers.
    - Can use this to sync multiple triggers instead of pasting the same info over them all.
- Misc
  - Improved enemy search logic for all systems (AutoAim, Explosive, etc.)
    - Now acquires ALL enemies, rather than capping at a certain point.
    - Potentially improved performance.

**Bug Fixes**

- Fire Rate Mod, Temp Properties
  - Fixed networked triggers applying to all effects of the same type
- Projectile
  - Fixed incorrect initial hitbox position
  - Fixed incorrect hit locations
  - Fixed enemies not being hit if they were inside the projectile but didn't have line of sight initially
  - Fixed inability to damage padlocks
  - Fixed inability to deal backstab damage
  - Fixed nullref that occurred when hitting walls sometimes
- Thick Bullet
  - Fixed inability to damage padlocks
- Misc
  - Fixed nullref that occurred when hitting padlocks

## v2.0.0

**Melee Support**

EWC now supports adding properties to melee weapons! Most effects work, but few traits do.

**Temp Properties**

Change the behavior of the weapon during play by adding and removing properties when triggered.

**Features & Adjustments**

- Added Melee Support
  - Specified on CustomWeapon blocks via "MeleeArchetypeID"
  - Disallowed Effects: AmmoMod, RecoilMod
  - Allowed Traits: ArmorPierce, BackMulti, TumorMulti
  - Integrated mostly with existing triggers.
- Added new Traits:
  - Audio Swap: Toggles audio on a trigger.
  - Temp Properties: Temporarily adds another set of properties.
- Added new Triggers:
  - Aim, Aim End: Triggers when entering or exiting aim down sights, respectively.
  - Pre Fire: Triggers prior to a shot firing or at the start of a melee swing.
  - Reload Start: Triggers when a reload is started.
  - Charge: Triggers when damage is dealt, scaling trigger amount by the melee charge scalar.
- Explosive
  - Now accepts Damage and Charge triggers
- Removed support for ResetTrigger & Cooldown fields

**Bug Fixes**

- Damage Trigger
  - Fixed type blacklist not working (e.g. Explosive could trigger on Explosive damage)
- Explosive
  - Fixed Trigger not appearing on the template


## v1.8.4

**Bug Fixes**

- Accelerate
  - Fixed ResetTrigger not functioning

## v1.8.3

**Bug Fixes**

- Thick Bullet
  - Fixed pierce weapons not hitting anything

## v1.8.2

**Bug Fixes**

- Accelerate, Fire Rate Mod
  - Properly modifies burst delay again
- Thick Bullet
  - Checks for line of sight when sufficiently big

## v1.8.1

**Features & Adjustments**

- Added new Trait:
  - Wall Pierce: Bullets can damage enemies through walls.

**Bug Fixes**

- Projectile
  - Can damage padlocks again (uses "Hit Size" hitbox)

## v1.8.0

**Features & Adjustments**

- Accelerate:
  - Field "Accel Exponent" supports the value "e", which causes it to use a continuous growth curve.
- Auto Aim:
  - Added field "Target Mode": Sets the behavior for targeting, to replace "TargetBody". Accepts the values:
    - "Normal": Current default targeting.
    - "Body": Same behavior as "TargetBody".
    - "Weakspot": Prioritizes visible weakspots. Similar to "Normal", but can target tumors.

**Bug Fixes**

- Trigger
  - Fixed invalid triggers on some effects causing errors

## v1.7.3

**Features & Adjustments**

- Added new Trait:
  - Backstab Multi: Applies a multiplier to backstab damage.

**Bug Fixes**

- Explosive
  - Fixed not applying back damage with "BulletLanded" triggers that hit the ground.
- Projectile
  - Fixed projectiles hitting corpses and disappearing.
  - Fixed projectiles scanning for hits farther than intended.
  - Fixed projectiles failing to hit enemies within their hitbox when extremely large.
  - Fixed projectiles hitting through walls when large.
  
## v1.7.2

**Bug Fixes**

- Kill Trigger
  - Fixed non-EWC weapons and melee causing kill triggers for the last EWC weapon that hit the enemy.
  - Fixed a few issues with its logic that ensured triggers only run once.
  - Fixed error message that occurred when non-EWC weapons alone killed an enemy.
  
## v1.7.1

**Features & Adjustments**

- Explosive
  - Added new fields:
    - "DamageFriendly": Enables damage to teammates.
    - "DamageOwner": Enables damage to the user.
    - "SoundID": The sound to use for the explosion.

**Bug Fixes**

- Damage Over Time
  - Fixed a case where applying damage over time from a damage over time hit would break it
  
## v1.7.0

**Features & Adjustments**

- Explosive
  - Now accepts Kill triggers
- Projectile
  - Added new fields:
    - "AccelScale": The scalar multiplied with speed that the projectile accelerates to.
    - "AccelExponent": The exponent used on acceleration progress.
    - "AccelTime": The time for the projectile to fully accelerate.
    - "DamageFriendly": Enables direct hit damage to teammates.
    - "DamageOwner": Enables direct hit damage to the user. (Now defaults to false)
    - "Lifetime": The lifetime of the projectile.
- Trigger
  - Added "Cap" field: Limits the number of stored activations.

**Bug Fixes**

- Projectile
  - Fixed visual bullet tracers/FX appearing.
  - Fixed pierce projectiles being able to hit the same enemy multiple times if another weapon or projectile hit them.
    - Was particularly common on pierce shotguns.
- Triggers
  - Fixed an error that occurred when apply triggers ran without stored activate triggers.

## v1.6.5

**Bug Fixes**

- Projectile
  - Fixed an error that occurred when bottoming out the magazine with a full-auto weapon.

## v1.6.4

**Bug Fixes**

- Projectile
  - Fixed it not being affected by spread.

## v1.6.3

**Bug Fixes**

- Projectile
  - Fixed it not working at all, courtesy of Thick Bullet addition.

## v1.6.2

**Features & Adjustments**

- Thick Bullet
  - Removed friendly fire checks from the bigger hitbox.

## v1.6.1

**Features & Adjustments**

- Added new Trait:
  - Thick Bullet: Gives bullets a bigger entity hitbox.

**Bug Fixes**

- Explosive
  - Fixed it failing to hit padlocks.
- Projectile
  - Fixed piercing weapons firing nothing.

## v1.6.0

**Features & Adjustments**

- Added new Trait:
  - Projectile: Fires a projectile instead of a hitscan bullet.
- Explosive
  - Added field "GlowColor": Sets the color for the explosion FX.
  - Added field "GlowDuration": Sets the duration for the explosion FX.
- Added an option to the config to recreate the template file (in case a developer wants to recreate it without restarting).

**Bug Fixes**

- Accelerate, Fire Rate Mod
  - Fixed the lack of syncing with other players.
  - Fixed incorrect audio fire rate when swapping to the weapon in some cases.
- Auto Aim
  - Fixed bugged behavior on piercing weapons where it would attempt to aim at the locked target with each pierce hit.
- Tumor Damage Multi
  - Fixed multiplier applying exponentially with pierces.
- Fixed unregistered type warnings in console/log output.

## v1.5.2

**Features & Adjustments**

- Added an option to the config to completely disable SFX.

## v1.5.1

**Bug Fixes**

- Damage Over Time
  - Fixed crash on trigger.
  - Fixed Damage triggers not scaling to damage dealt.

## v1.5.0

**Trigger Overhaul**

Expanded the trigger system. Classical trigger definitions are supported, but "Cooldown" and "ResetTriggerType" effect fields are now deprecated as they exist in the trigger system instead. They will be removed in a future version. The system adds the following capabilities:
- Add multiple triggers for one effect.
- Separate the activation and application trigger timings for an effect.
- Add a chance for triggers to occur.

Please see the [Wiki Page](https://github.com/Dinorush/ExtraWeaponCustomization/wiki/Trigger) for more details.

**Features & Adjustments**

- Added new Traits:
  - Armor Pierce: Pierces armor or modifies bullet damage dealt to armor.
  - Pierce Multi: Applies a damage multiplier with each enemy pierced.
  - Tumor Multi: Applies a multiplier to tumor damage.
- Damage Over Time
  - Now causes Hit triggers
- Explosive
  - Added Trigger field. Supports Hit as a valid trigger type.
- Triggers
  - Damage
    - Added field "Cap": Sets the maximum amount of damage a single trigger will accept.

**Bug Fixes**

- Explosive
  - Fixed a rare issue where direct hit explosions could cause piercing bullets to deal no damage.

## v1.4.4

**Features & Adjustments**

- Ammo Mod, Damage Mod, Damage Mod Per Target, Fire Rate Mod, Health Mod, Recoil Mod
  - Added field "Cooldown": Sets a cooldown that prevents the effect from triggering again until it passes.
    - E.g. useful for having an effect trigger on hit but only once per bullet regardless of pierce/explosion
- Enforce Fire Rate
  - Affects recoil

**Bug Fixes**

- Accelerate, Damage Mod, Enforce Fire Rate
  - Damage modifiers no longer apply exponentially to targets beyond the first on piercing bullets

## v1.4.3

**Bug Fixes**

- Ammo Cap
  - Fixed an issue where it would not apply on drop if the weapon was swapped to in loadout selection

## v1.4.2

**Features & Adjustments**

- Auto Aim
  - "Favor Look Point" is now only active if the user is aiming at the locked target, rather than any enemy.
  - Improved visuals when lock is lost; locking reticle moves towards the center of the screen
  - Increased search tick rate from 4/s to 10/s, along with performance improvements to compensate

**Bug Fixes**

- Damage Mod Per Target
  - No longer causes null refs when hitting locks.
- Reserve Clip
  - Fixed an issue where having one weapon with Reserve Clip would reload the other weapon if it was held when receiving ammo
- Trigger Type
  - "On Damage" triggers no longer occur on dead enemies.

## v1.4.1

**Features & Adjustments**

- Ammopack Refill
  - Renamed to "Ammo Cap". Now functions more generically as a property that modifies the reserve capacity used for ammo calculations.
    - **Dev Note:** "AmmopackRefill" still works, but is deprecated and will be removed in the next minor version.
  - Now affects ammo on drop.
  - "AmmoRefillRel" now exactly determines ammopack refill amount, rather than being affected by the Ammo Max / Ammopack Max ratio.
  - Added 2 new fields that have the same effect as "AmmoRefillRel" but can be more intuitive in some cases:
    - "AmmoCapRel": Direct modifier of reserve capacity for ammo calculations.
    - "CostOfBullet": Specifies the CostOfBullet to be used for ammo calculations rather than the weapon's CostOfBullet.

**Bug Fixes**

- Ammopack Refill/Ammo Cap
  - No longer modifies level ups from GTFuckingXP to count as an ammopack
  - No longer modifies "Ammo" command on CConsole to count as an ammopack

## v1.4.0

- New effect: Recoil Mod
  - Applies a recoil modifier when triggered.
- Ammo Mod
  - Added field "Overflow To Reserve": Excess ammo changes in the clip overflow to reserve ammo. On by default.
- Trigger Type
  - Added type "On Wield": Triggers when swapping to the weapon.
- Misc
  - Added compatibility with GTFuckingXP

**Bug Fixes**

- Misc
  - Fixed burst weapons having no burst delay if they had no fire rate modifiers.

## v1.3.0

**Features & Adjustments**

- Accelerate
  - Added field "Damage Stack Layer": Determines how the damage modifier stacks with other damage modifier effects.
- Damage Mod, Damage Mod Per Target, Fire Rate Mod
  - Added field "Stack Layer": Determines how the effect modifier stacks with different effects. Set to "Multiply" by default (matches existing behavior).
  - "Stack Type" now uses "Add" by default rather than "None".
- Damage Mod Per Target
  - Now also supports the new Trigger Type "On Damage" (Previously only allowed "On Hit")
- Damage Over Time, Explosive
  - Now benefit from backstab bonus.
  - Added field "Ignore Backstab": Disables the backstab bonus. Off by default.
- Trigger Type
  - Added type "On Damage": Triggers on any damage dealt (bullet, DOT, explosive) and scales the effect with damage dealt.
  - Added type "On Precision Damage": Same as "On Damage", but only on precision hits.
- Misc
  - Damage multipliers now affect friendly fire damage.
  - Improved LiveEdit support and logging.
    - Prints all found archetype IDs on load/file edit, rather than only replaced IDs.
    - Prints warnings when duplicate archetype IDs are found.
    - Supports file creation and deletion during runtime.
    - Applies custom data objects added to held weapons that did not originally have one.
    - Correctly removes stashed custom data objects when they are removed from their file.

**Bug Fixes**

- Explosive
  - Fixed damage modifiers not applying correctly.
- Health Mod
  - Now exists in the template file.
- Misc
  - Effects now reset on elevator drop.
  - Fixed incompatibility with ExtraObjectiveSetup.

## v1.2.0

**Features & Adjustments**

- New effect: Heal Mod
  - Allows giving or taking health from the user when triggered.
- Accelerate
  - Now compatible with Semi-Automatic and Burst weapons.
- Auto Aim
  - Added field "Favor Look Point": Prioritizes the user's aim if they are looking directly at an enemy.
  - Added field "Lock While Empty": Allows locking while the clip is empty or during reloads. On by default.
  - Now immediately searches for a new target if the current target dies (previously only updated on a tick every 1/4 second).
- Damage Mod, Damage Mod Per Target
  - "OnHit" and "OnHitExplosion" triggers from explosions no longer effect the bullet that hit the enemy on a direct hit.
- Damage Mod, Damage Mod Per Target, Fire Rate Mod
  - Added field "Cap": Sets a maximum or minimum total modifier.
- Damage Over Time, Explosive
  - Added field "IgnoreDamageMods": Ignores damage modifiers when calculating damage dealt.
- Trigger Type
  - Added type "OnPrecisionHit": Triggers on weakspot hit. Has subtypes like "OnHit", e.g. "OnPrecisionHitBullet".
  - Added type "OnPrecisionKill": Triggers when an enemy is killed with a weakspot hit.
- Misc
  - Editing the file now updates weapons in your hands rather than requiring you to change loadout.

**Bug Fixes**

- Accelerate, Fire Rate Mod
  - Fixed weapon audio being incorrect on the first shot after fire rate changed
- Ammo Mod
  - Fixed cases where clip could underfill or overfill by 1
- Auto Aim
  - Fixed issues with Auto Aim reticle not appearing when it should
- Trigger Type 
  - OnKill now triggers on the weapon that got the kill rather than held weapon
- Misc
  - Changed networking logic, should fix some issues and work closer to vanilla networking
  - Fixed some cases where weapon effects or audio would trigger when the weapon shouldn't fire

## v1.1.4

- Fixed semi-automatics and burst weapons having the wrong fire rate (real final fix)

## v1.1.3

- Fixed bricking semi-automatics and burst weapons

## v1.1.2

- Fixed Explosives triggering on other players than the one who fired
- Semi-Automatics and Burst weapons now work better with fire rate modifications

## v1.1.1

- Fixed multiple weapons with the same archetype sharing property behavior/causing issues
- Fixed multiple auto aim weapons causing issues with the others
- Fixed ReserveClip causing errors when using ammo packs
- (Potentially) Fixed errors with favorited weapons

## v1.1.0

- Ammo Mod
    - Now accepts decimal values. Decimals accrue in the background until a whole number is reached.
- Explosive
    - Moved to effects (can have multiple different ones on a gun)
    - Fixed piercing weapons causing extra explosions on the same enemy.
- Fire Rate Accel
    - Renamed to Accelerate
    - Can now change damage
- Damage Mod and Damage Mod Per Target
    - Now affect Damage Over Time and Explosive
    - Added a ResetTriggerType to clear all modifier stacks on a trigger condition
- OnHit Trigger
    - Now also occurs on explosive hits.
    - Added OnHitBullet and OnHitExplosive for specific hit types.
- Misc
    - Fixed sentries using your currently held weapon's effects.

## v1.0.0

- Initial Release