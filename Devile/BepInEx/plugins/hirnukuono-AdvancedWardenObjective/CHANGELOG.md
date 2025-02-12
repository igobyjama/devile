# Changelog
### V2.0.3
  - Fixed ``MoveExtractionWorldPosition`` not working.
  - Fixed TSL not consistently fetching terminals in static dimensions in the same order as AWO terminal events.
  - Internally changed EventLoops to be more thread-safe.

### V2.0.2
  - Fixed EventsOnProgress only executing the first progress event. (Make sure progress events are ordered from first to last.) 

### V2.0.1
  - Removed the arbitrary behavior in `HideTerminalCommand` and `UnhideTerminalCommand` of getting UniqueCommand 1-5 when "CommandNumber" is 1-5. 
  - Fixed "DeleteCommand" not always working in `HideTerminalCommand`. It is now mutually exclusive with hiding a command and will only work if the command is visible.
  - Added an error check for `SetTerminalLog` if "FileContent" is empty when adding a new log.
  - Fixed `TeleportPlayer` not retaining the last look direction before flash teleporting.
  - Reverted accidental change in `ForceCompleteChainPuzzle`. It should now clear scan splines again and not vomit when doing so.

### V2.0.0
This is intended to be one of the last major updates for AWO. Thanks everyone! --Amorously

<b>New Events:</b>
  - `ForcePlayPlayerDialogue`
  - `SetTerminalLog`
  - `SetPocketItem`
  - `DoInteractWeakDoorsInZone`
  - `ToggleInteractWeakDoorsInZone`

<b>Vanilla Event Overrides (VEO):</b>
  - In `PlaySound` (Type 5) you can now also use "Position" instead of "WorldEventObjectFilter" to play non-global sounds from.
  - In `SpawnEnemyOnPoint` (Type 16) you can now also use "Position" instead of "WorldEventObjectFilter" to spawn enemies from, and "Count" to spawn that number of enemies.

<b>Terminal Serial Lookup (TSL)</b>
  - For most formatted text in the game, you can now get the zone alias or serial number for <i>any</i> terminal item! See wiki for how to use.
  - Ex. `"[TERMINAL_0_0_0_0]"` would get the serial number for (Reality, Main, Zone_0)'s 0th terminal.
  - Ex. `"[ZONE_3_2_1]"` would get the zone alias for the zone in (Dimension_3, Overload, Zone_1).

<b>Updated:</b>
  - Events the execute other events in AWO can now execute custom warden events, such as ones from Inas's plugins (EOS, ESVS).
  - Replaced Hirnu's WeakDoorMechanism in `AlertEnemiesInZone` with NoiseEventMechanism (i.e. scream doors, EventsOnEnter). This is now mutually exclusive with the original behavior and enabled by default. For the original behavior, enemies will now aggro onto the closest alive player instead of the host.
  - Added field "NavMarker" to `SpawnNavMarker`; you can now change the nav marker color, style, add text, and add a fade out time.
  - Added fields "IsLayerIndependent" and "Priority" to `MultiProgression`, which will hide/unhide MPs on the hud depending on which layer the player is in.
  - `Teleport/Infect/Damage/Revive Player` should now instead use the Xth player in the lobby from left to right, rather than their lobby slot index.
  - Improved performance for EventsOnProgress.
  - Transitioned to primarily using `GTFO.API` for LevelEvents.
  - Improved randomness.
  - Added "fallbacks" for duplicate and nested fields. See wiki.
  - Added new field "WorldEventObjectFilter", which proxies "SpecialText". 
  - You can now specify a WorldEventObjectFilter for `SpawnHibernateInZone` and `SpawnScoutInZone`.
  - Attempted fix on custom success screens not always updating.
  - Refactored/rebuilt most code in AWO. 
  - Add more.

<b>Known Issues:</b>
  - `SetLightDataInZone` is still under investigation with `EOSExt_EMP` and the EMP ability in `EEC`, and will hopefully get fixed in the future.
  - If you lock WeakDoors using `ToggleInteractWeakDoorsInZone` and open or close them with `DoInteractWeakDoorsInZone`, any door buttons with a WeakLock on them will become interactible again. I'm lazy and this is kinda niche.
  - Generator Clusters and Generators added by `ExtraObjectiveSetup` do not currently have a valid TerminalInteface setup, so they can neither be queried nor be used in the serial number lookup.

<details>
  <summary><b>V1.2.0 - 1.2.7</b></summary>
<br>

### V1.2.7
  - Added new event `SpecialHudTimer`.
  - Changed `CustomHudText` since it didn't need to be run in a coroutine.
  - Fixed EventsOnProgress killing the timer.
  - Fixed `NestedEvent` potentially crashing the game when there are more MaxRandomEvents than EventsToActivate. 
  - Fixed an issue where `PlayWaveRoarSound` would play wave roars one size larger than specified.
  - Removed the restriction of having only one active DOT `DamagePlayer` & IOT `InfectPlayer` event at a time.
  - Remembered to do the version bump.

### V1.2.6
  - Added new event `CustomHudText`.
  - Added a random event selection mode to `NestedEvent`.
  - You can now specify a WorldEventObjectFilter to use for `PlayWaveRoarSound`, `SpawnNavMarker`, & `MoveExtractionWorldPosition` via SpecialText.
  - Saved like, 20 bytes of memory for events that use coroutines.

### V1.2.5
  - `CleanupEnemiesInZone` hotfix, sry for the wait.

### V1.2.4
  - Added EventsOnProgress to `Countdown` and `Countup`.
  - You can now specify an area index for `AlertEnemiesInZone` (see wiki)
  - Fixed a potential sync issue with `LockSecurityDoor`.

### V1.2.3
  - You can now specify an area index for `CleanupEnemiesInZone`.

### V1.2.2
  - Fixed a major sync issue with AWO events that activate other events  (Countdown, Countup, NestedEvent, and StartEventLoop).
  - `SpawnHibernatesInZone` now also rerolls for enemies spawning too close to other enemies. After 5 failed attempts, you can choose whether or not to cope and spawn the hibernate anyway via Enabled (default true).

### V1.2.1
 - Added new event `PlayWaveRoarSound`.
 - Fixed `Countdown` and `Countup` using the incorrect BlinkIn/BlinkOut values.
 - Increased `SpawnHibernateInZone` player avoid distance >:(
 - Retroactively changed `ModifyPortalMachine` event name to `StartPortalMachine`, sorry

### V1.2.0
<b>New events:</b>
  - ShakeScreen
  - StartPortalMachine
  - SetSuccessScreen
  - PlaySubtitles
  - MultiProgression

<b>Updated:</b>
  - Fixed `LockSecurityDoor` not locking doors and implemented option to add text to locked door.
  <pre>{
    "Type": 10001,
    "Layer": 0,
    "DimensionIndex": 0,
    "LocalIndex": 1,
    "SpecialText": "<color=green>://ERROR! Ultra locked!!</color>"
}</pre>
  - Fixed `TeleportPlayer` not properly syncing between host-clients.
  - Fixed `SpawnScouts` & `SpawnHibernates` throwing errors in the console.
  - You can now use modded custom success screens! Just put the full prefab filepath in either the `SetSuccessScreen` event or RundownDB.
  - Disabled the Objective Extension module (if you were actually using this, DM me and I'll reenable it).

</details>

<details>
  <summary><b>V1.1.1 - 1.0.15</b></summary>
<br>

### V1.1.1
- Fixed `AdjustAWOTimer` bricking `Countdown` duration.
- Fixed `ForceCompleteChainPuzzle` throwing null reference errors if a CP doesn't have a spline.
- A positive TimeModifier for `AdjustAWOTimer` will now increase `Countup` instead of lowering it.
- AMAWO console debug/error messages now include the event name.

### V1.1.0
<b>New events:</b>
  - Countup (like Lockout2's E1 gimmick)
  - ForceCompleteChainPuzzle
  - SpawnNavMarker

<b>Updated:</b>
  - Countdown: you can now also use Duration outside of CountdownData class. Prioritizes backwards compatibility.
<pre>{
  "Type": 10010,
  "Duration": 60.0,
  "Countdown": {
    "TimerText": "Time Until Ends:",
    "TimerColor": "red",
    "EventsOnDone": []
  }
}</pre>
  - AdjustAWOTimer: Same as above. Added features for Countup.
  - SolveSecurityDoorAlarm: Now only changes door interaction state (Clearing CPs was broken, anyways). Use ForceCompleteChainPuzzle for this functionality.
  - AddTerminalCommand: You can now use TextDB for CommandDesc.
  - Refactored code in most AMAWO events.

### V1.0.1650

Fixed Active EventLoop Ids persisting between levels. 

### V1.0.15

Amorously makes and will continue to make cool contributions. First ones merged and compiled here. See the wiki for how to use them.
```
New events:
   - NestedEvent
   - StartEventLoop
   - StopEventLoop
   - TeleportPlayer
   - InfectPlayer
   - DamagePlayer
   - RevivePlayer
   - AdjustAWOTimer
```
</details>

<details>
  <summary><b>V1.0.14 - 1.0.1</b></summary>
<br>

### V1.0.14

thyunsus requests: cleanupenemiesinzone IncludeOnlyID (works same as ExcludeEnemyID but in reverse)

### V1.0.13

hideterminalcommands can now use a remove command entirely -switch, DeleteCommand default false. true it to make the command go poof entirely.

also some other tweaks and fixes here and there.

### V1.0.12

added AddChainPuzzleToSecurityDoor / 10027

Datablock example:

<pre>
              {
                "Type": 10027, // "AddChainPuzzleToSecurityDoor",
                "Layer": 0,
                "DimensionIndex": 0,
                "LocalIndex": 1,
                "WardenIntel": "door is rigged noob",
                "ChainPuzzle": 139
              }
</pre>

only effective on doors that have not been opened yet. on unlocked doors the handle goes back in its hole.

### V1.0.11

AddTerminalCommand does TriggerClient stuff, now it works as it should. ish. zero delay on the command but i can live with it. :)

### V1.0.10

minor tweaks to AddTerminalCommand and COMAMNDS list, noticed u could repeatedly add commands with the same command numbers, not nice. made a simple duplicate check, wont let u do it now.

### V1.0.9

would you like to have over 2 billion UniqueCommands? :) check TERMINALCOMMANDS.md for new commands 10024-10026 AddTerminalCommand, HideTerminalCommand, UnhideTerminalCommand

### V1.0.8

spawnhibernateinzone now avoids players, rerolls position until a position is found that doesnt spawn on a player, instantly aggroing it. also solvesecuritydoor might work better. ish.

### V1.0.7

spawnhibernateinzone now properly randomizes rotation of enemies, they don't all face (roughly) the same way. one enemy spawn goes by the eventdata spawnhibernates position + rotation (rotation.y should only be modified).

### V1.0.6

fixed CleanupEnemiesInZone

### V1.0.5

SolveSecurityDoorAlert now functions even if the door is locked by keycard, cell or lockednokey (type 3) .. it switches any chainpuzzle on the door into type 4.

### V1.0.4

alertenemiesinzone chagned (wakeup mechanism, weakdoor opening). devs: if u don't want weakdoors of zone to open, use "Enabled": false on the event (default true if missing). thanks thyunsus a lot for testing this!

### V1.0.3

v1.0.2 was flawed in one game-breaking way, fixed.

### V1.0.2

thy reported that countdown timers after checkpoints break and play old events again. made provisions to detect cp usage and seppuku accordingly. also, made a small change to how the after-events are executed.

### V1.0.1

initial.
</details>