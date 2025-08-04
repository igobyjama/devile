# Update (0.13.4)
 - Thanks for `Auri` for contributing to Update!
 - Added: `ListBinds` Command
 - Fixed: `KillEnemies` can now kill Pablo (tank_boss) as clients
 - Fixed: `MobileTurbine` breaking `FullBright`
 - Change: `WEVisualizer` can now display generic `WorldEventObjects` in the level
 - Change: `DebugDraw` Utility methods are now exposed under Namespace `CConsole.Utils.DebugDraw`
 - Change: `LatestExpeditionGUI` can now be disabled by setting Key to `None`

# Update (0.13.3)
 - Toggling Some GUI now does not show up `ExFreecam` Legend overlay
 - Replaced `OnIncomingDamage` Detour to Harmony Patch (It should now compatible with EWC)

# Update (0.13.2)
 - Added Missing Dependency for `BepInEx-BepInExPack_GTFO`
 - Fixed: NRE issue while using `ExFreecam`

# Update (0.13.1)
 - Fixed: `SpawnEnemy` rotation parameter is feed wrong

# Update (0.13.0)
 - Thanks for `Auri` and `tru0067` for contributing to Update!
 - Add: `StartFogTransition` Command. This one is network synced unlike `SetFog` does
 - Add: `Infection` Command. This could precisely controls current players Infection amount
 - Add: `LoadExpedition` Command. Useful for Accessing Locked Expedition without Editing RundownDB
 - Update: `WorldEventGizmo` Now supports capsule collider to debug Security Sensor
 - Update: `SpawnEnemy` Command. Now accepts rotation parameter
 - Update: `Health` Command. Now it could precisely control your Health
 - Update: `GiveItem` Command. Now accepts ItemDataBlock name
 - Update: `ExFreecam`
   - Now have a Inspector window to debug items in crosshair
   - Now have a Legend window to guide what key binds are available
   - Added Keybind `I` to inspect item in crosshair with `UnityExplorer`
 - Fixed: `SpawnEnemy` and `SearchEnemy` now works with PartialData'ed Enemy Names
 - Fixed: Exception when `UnityExplorer` is not installed
 - Fixed: Disable Game Input when `UnityExplorer` UI is active
 - Fixed: Potential Fix for `MarkEnemies` where info stops updating when enemy is too far away
 - Fixed: Potential Fix for `KillEnemies` throw NRE when `KillIndicatorFix` mod is installed

# Update (0.12.1)
 - Thanks for Auri for contributing this change!
 - Fixed Issue: Console now don't goes to softlock state while using terminal

# Update (0.12.0)
 - Huge Shoutout to Auri for making all of these changes!
 - Add: `EnemyPathingVisualizer` Command
 - Add: `GoodPositionVisualizer` Command
 - Add: `InvisibleWalls` Command
 - Add: `TScanHelper` Command
 - Add: `WorldEventGizmo` Command
 - Add: `Culling` Command
 - Add: `ShaderHelper` Command
 - Update: `SetLight` Command. Now accepts subseed
 - Update: Alias System, now it accepts parameters like: `{args} {0} {1}` and such
 - Config Added: `EscapeKeyClosesConsole`
 - Config Added: `DisableKeyBindsWhileTypingInChat`
 - Config Added: `DisableKeyBindsWhileOnMap`
 - Config Added: `ExtendedFreeFlightCamera`

# Update (0.11.7)
 - Target Revision Bump and Backend Reflection bug fix (Nothing really changed)

# Update (0.11.6)
 - Add: Absorbtion Parameter to Fog Editor (FogColor Alpha)

# Update (0.11.5)
 - Add: `StopWave` Command
 - Add: `DataBlockList` Command
 - Update: `ListWave` now show list of possible enemy that can be spawn in wave
 - Further extends verbose log suppression
 - Changelogs are now in different file ;)
 - Now Support Blocking Input while using UnityExplorer
 - 📻

# Update (0.11.4)
 - Add: `TP` Command, For teleport to terminal item or other player
 - Add: `NavGizmo` Command, For revaling NavMesh or Off-Links (aka ladders)
 - Add: Config to Shorten the Annoying Logs (For now, EnvironmentStateManager logs are)
 - Add: Config to Hide Inaccessible NavMesh while using NavGizmo
 - Moved `Noclip` and `Freecam` command under `Navigation` Category

# Update (0.11.3)
 - Fixed Issue: `SetLight` is not working

# Update (0.11.2)
 - Target Revision Bump
 - Add `SetTerminalState` command
 - Add `SetLight` command

# Update (0.11.1)
 - Target Revision Bump
 - Console now doesn't accept input on terminal screen

# Update (0.11.0)
 - Add: `Alias` command, Command to set "alias" for command-sets
 - Update: `EnemyDetection`, `MarkEnemies`, `ShutUpSpitter`, `FastElevator`, `God`, `IgnoreInfection`, `IgnoreKnockback`, `InfiniteClip`, `OneHitKill` and `Stamina` now accept `false/true` for argument
 - Update: `SearchObjective` command now show both corr uplink terminal (master/slave)
 - Update: Console now show `Unable to find command...` tooltip when it can't find any command from input
 - Fixed Issue: Cursor now properly hide when you toggle Console on Freecam
 - Fixed Issue: Picking up items now clear search marker
 - Fixed Issue: Compact console no longer eat your input on certain situation
 - Fixed Issue: `name` now be saved properly on Fog Editor

# Update (0.10.1)
 - Fixed Copy to Clipboard on Fog Editor

# Update (0.10.0)
 - Added Fog Editor (Default: F6)

# Update (0.9.12)
 - Update build revision number (32823 -> 32998)
 - Add-Command `ListWave` - List all active waves
 - Add-Command `SearchEnemy` - Search for spawned enemies in level
 - Update: `SearchProgression` command
   - Now accept `-withdoor` parameter to also mark locked security doors
   - Added Icons for better visibility
   - Added Bulkhead DC to search list

# Update (0.9.11)
 - Add: Various Console Appearance config
   - Edit Console BG/Text/Highlight Color
   - Edit Console Font/Font Size
 - QOL: Listen Unity Log Setting now can be toggled in Console Window