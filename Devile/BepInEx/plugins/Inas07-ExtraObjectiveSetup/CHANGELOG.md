# 1.6.10
  - Fixed a bug with Objective Counter where clients would sometimes become one step ahead of host on elevator land.
    - Many thanks to Cris for reporting the issue, ThyUnsuspicious for testing, and Jarhead for compiling.

# 1.6.9:
Minor bug fix:
- Fixed an indexing code which is susceptiable to index error exception
- Added a small patch that: For vanilla reactor terminal, override its null `SpawnNode` to `ConnectedReactor.SpawnNode`

# 1.6.8:
 - Fixed: the issue mentioned here
   - https://discord.com/channels/782438773690597389/783918553626836992/1380229542580457672

# 1.6.5~1.6.7:
 - Fixed: EOS Generator Cluster End Sequence not getting reset on checkpoint
   - https://github.com/Inas-07/ExtraObjectiveSetup/pull/1
 - `PartialData` Compatibility check 

# 1.6.4:
 - No feature updates.
 - Fixed: `LocalizedTextConverter` in `PartialData` cannot perform write operation properly.
 - Added: API to copy-instantiate `TMPPro` component from vanilla chained puzzle prefab.

# 1.6.3
 - Fixed: `EventsOnBossDeath` does not work if it's applied to scout.

# 1.6.2
 - Added: Warden Event `EOSToggleTerminalState`. You can toggle terminal to be normal / unusable.
 - Updated documentation accordingly. (https://github.com/Inas-07/ExtraObjectiveSetup/wiki/Extra-Warden-Objective-Event) 

# 1.6.1
  - Fixed: Custom Generator Cluster does not function properly.

# 1.6.0
 - Checkpoint restore bug fixes:
   - Fixed: Logical Generator Group: Restoring from checkpoint re-execute events unexpectedly.
   - Fixed: Custom Generator Cluster: Restoring from checkpoint re-execute events unexpectedly.
   - Fixed: Individual Generator: Restoring from checkpoint re-execute `EventsOnInsertCell`.
   - Fixed: HSUActivator: Restoring from checkpoint re-activate `ChainedPuzzleOnActivation` (if any), re-execute `EventsOnHSUActivation`, `EventsOnActivationScanSolved`.
 - Added vanilla extension:
   - Added: For terminal `UniqueCommand` of command rule `Normal`, if it's attached any `ChainedPuzzle`, the puzzles will be reset to its initial state upon finishing the puzzle.
   - Added: Warden Event `EOSSetTerminalCommand`. You can show / hide certain command on certain terminal.
   - Added documentation accordingly (https://github.com/Inas-07/ExtraObjectiveSetup/wiki/Extra-Warden-Objective-Event) 

# 1.5.0
 - Fixed: `EOSExt_Reactor` cannot build reactor terminal unique commands.
 - Added: `ObjectiveCounter`. It's a custom counter that you could increment, decrement. If the counter reached a certain number, warden events could be executed.
 - Updated documentation accordingly.

# 1.4.6 [Bug fix]
 - Fixed: `EventsOnBossDeath` with limited execution times is not state-synced.

# 1.4.5 [Bug fix]
 - Fixed: `Position` property of `WardenObjectiveEventData` is not handled properly
 - Fixed: `EventsOnBossDeath` is executed in an undesired scenario.
 - Fixed (vanilla bug): powercells inserted to generators could be teleported if, in `ItemDatablock`, `DimensionWarpType` of `Power Cell` (persistent id 131) is configured to be warpable.
 - FloLib: removed a specific Debug message.

# 1.4.4
 - Bug fix: fixed an issue that impedes state-sync.

# 1.4.3
 - [EMP]: removed, and made as a standalone plugin.
 - [Uplink]: fixing (need test) - completed uplink is not reset properly after restoring from checkpoint if it is not completed before reaching checkpoint

# 1.4.2 [Bug fix]
  - [EMP]: Fixed - EMP-ed behaviours of Biotracker, PlayerFlashLight and PlayerHud is not working properly.
  - [ActivateSmallHSU]: Fixed - `EventsOnActivationScanSolved` is not executed on client side.
 
# 1.4.0
  - Added [EMP] events (decoupled from EEC) 
  - Added feature [Persistent_EMP] to `ExtraExpeditionSettings` 
  - Updated documentation accordingly.
  - Added documentation for implemented-but-undocumented features in `ExtraExpeditionSettings`. 

# 1.3.3
  - EOSExt.Reactor compatibility check.

# 1.3.2
  - Miscellaneous bug fix.

# 1.2.2
  - AWO compatibility check.

# 1.2.1
- Improved feature `EventsOnZoneBossDeath`:
  - Now boss death events could be applied to wave bosses as well.
  - More configurable options.
  - Updated documentation accordingly.

# 1.2.0 
- Added features `EventsOnZoneScoutScream`, `EventsOnZoneBossDeath`.
- Updated wiki for `Uplink Terminal`, and the new features.
- Compatibility Issue Note `AWO`: 
  - When `AWO` is installed, events specified in the config file of this plugin would _probably_ be 'skipped' (technically speak, event type will be turned to `None`, for some reasons...). 
  - Make sure to test if your warden events defined in the configs are executed as expected.

# 1.1.0 & 1.1.1
Now supports AWO Events (Don't forget to install AWO)! 

# 1.0.0
Initial release