# DISCLAIMER: This mod only work if all player in lobby using this mod! You cannot join normal lobbies with this mod!

## Development Console Command Tool for Rundown Devs!

# Main Features
 - Simple CUI Devtool
 - Provide TONS of useful feature for Developing MODs for GTFO (Check `Shortcuts` and `Commands` to see what is available for use!)

# Extra QoL Features
 - Allow Force drop when you are host whatever teammate is ready or not
 - Allow swap weapon in lobby menu while in-game
 - Fast Elevator & Timescale on startup (Configurable)
 - Built-in Screen Skipper Feature (Configurable)
 - Silent Elevator when Timescale is set or Fast Elevator is set

# Shortcuts
 - (~) Open Console (Configurable)
 - (\\) Open Compact Console
 - (Tab) Auto Complete Command
 - (UpArrow) Auto Complete / Browse Command History
 - (DownArrow) Auto Complete / Browse Command History
 - (F1) Freecam (press T to teleport)
 - (F2) Location Info Menu
 - (F3) Resource Menu
 - (F4) FPS Weapon Inspector
 - (F5) \[Only on First Startup\] - Restore to latest expedition you dropped
 - (F6) Fog Editor
 - (Insert) - Weapon Builder Menu

# Commands
# Global
```
 - Cls | Clear the Console Screen
 - Help | Show information about command/hotkeys [Usage: 'Help <cmd/key>']
```
# Enemy
```
 - EnemyDetection | Toggle the enemy detection [Usage: 'EnemyDetection [true/false]']
 - KillEnemies | Kill reachable enemies
 - MarkEnemies | Mark reachable enemies [Usage: 'MarkEnemies [true/false]']
 - ShutUpSpitter | SHUT THE FUCK UP YOU FUCKING WALKSACKS [Usage: 'ShutUpSpitter [true/false]']
 - SpawnEnemy | Spawn Enemy on your crosshair by their EnemyID/Name [Usage: 'SpawnEnemy <Enemy ID/Enemy Name> [rotation] [-scout / -hunter]']
```
# Game
```
 - FastElevator | Toggle Fast Elevator [Usage: 'FastElevator [true/false]']
 - TimeScale | Change the timescale of the game [Usage: 'TimeScale <scale>']
```
# List
```
 - DataBlockList | List the specified datablock [Usage: 'DataBlockList <DataBlock Name> [Name filter]']
 - EnemyList | List out Enemies in game
 - ItemList | List the item ids [Usage: 'ItemList <All/Consumable/Pickup/BigPickup/Resource/Tool>']
```
# Give
```
 - GiveGear | Equip Gear from gear offline id [Usage: 'GiveGear <playeroffline gear id>']
 - GiveItem | Equip Item from item id [Usage: 'GiveItem <Item ID/Name>']
 - Ammo | Give Full Ammo
 - Disinfect | Fully Disinfect
 - Health | Set or Add Health [Usage: 'Health [health%] [-add]']
 - Infection | Set Infection Amount [Usage: 'Infection [amount%] [-add]']
```
# LocalPlayer
```
 - Culling | Toggle the culling system [Usage: 'Culling [true/false]']
 - God | Ignore all damage [Usage: 'God [true/false]']
 - IgnoreInfection | Ignore the Infection System [Usage: 'IgnoreInfection [true/false]']
 - IgnoreKnockback | Toggle Ignoring Knockback (or EEC Grapple) effect? [Usage: 'IgnoreKnockback [true/false]']
 - InfiniteClip | Toggle Weapon Clip to be infinite (pull directly from ammo) [Usage: 'InfiniteClip [true/false]']
 - InstantScan | Toggle Instant Scan
 - OneHitKill | Toggle One Hit Kill [Usage: 'OneHitKill [true/false]']
 - ReviveSelf | Revive Self
 - SpawnTripmine | Spawn Tripmine in crosshair [Usage: 'SpawnTripmine [Explosive/Glue/Consumable]']
 - Stamina | Toggle Stamina System [Usage: 'Stamina [true/false]']
 - Suicide | Suicide
```
# Navigation
```
 - Freecam | sv_cheats 1;freecam
 - FullBright | Toggle FullBright
 - Noclip | sv_cheats 1;noclip
 - RevealMap | Reveal Map [Usage: 'RevealMap [-outline / If set: it will only show outline of the map, not the full items]']
 - TP | Teleport! [Usage: 'TP <[Target Item Terminal Name] / [Player Slot (0-3)]>']
 - Turbine | Toggle Mobile Fog Turbine
```
# MobileTerminal
```
 - List | Show Terminal Items [Usage: 'List <filter1> [filter2] [filter3] ...']
 - Ping | Trigger Ping for Terminal Item [Usage: 'Ping <Terminal Item Name>']
 - Query | Get Detailed Information of Terminal Item [Usage: 'Query <Terminal Item Name>']
```
# Objective
```
 - CompleteObjective | Complete Layer Objective [Usage: 'CompleteObjective <Layer>']
 - ExecuteEvents | Execute WardenObjective Events (Not Network Synced) [Usage: 'ExecuteEvents <Layer Type> <Activate/GotoWin> [Activate EventBreak Index (0~n)]']
```
# Reactor
```
 - Reactor_Select | Select Reactor before using 'reactor_' cheats [Usage: 'Reactor_Select <Reactor Name (ie: REACTOR_111)>']
 - Reactor_Codes | Dump all Reactor codes
 - Reactor_Jumptowave | Jump to specific Reactor wave [Usage: 'Reactor_Jumptowave <Wave>'] [HOST ONLY]
 - Reactor_SetIdle | Set Reactor State to Idle [HOST ONLY]
```
# Search
```
 - Search | Search for objects in level by it's name [Usage: 'Search <Substring>']
 - SearchClear | Clear all marker spawned by Search Command
 - SearchEnemy | Search for Specific Enemy type in level [Usage: 'SearchEnemy <Enemy ID/Enemy Name>']
 - SearchItem | Search for Item in Level by id [Usage: 'SearchItem <Item ID>']
 - SearchObjective | Search for Objective Item in Layer [Usage: 'SearchObjective <Layer Type>']
 - SearchProgression | Search for Progression Objects (Key/Cell/Generator/Turbine/Bulkhead) in level [Usage: 'SearchProgression [-withdoor]']
 - SearchTerminal | Search for Terminals in level
```
# Sound
```
 - PlaySound | Play Sound in Player Position [Usage: 'PlaySound <Sound ID / Name>']
```
# Utility
```
 - Alias | Set Alias for Command(s) [Usage: 'Alias <Alias name> [Alias commands (Split by ';')]']
 - Bind | Bind Keyboard key with command [Usage: 'Bind <KeyCode> <command line>']
 - Loop | Loop specified command line with given delay [Usage: 'Loop <count> <ms delay> <"command line">']
 - Unbind | Unbind Keyboard key with command [Usage: 'Unbind <KeyCode>']
```
# Wave
```
 - ListWave | List Every active Survival Wave [Usage: 'ListWave'] [HOST ONLY]
 - StartWave | Trigger Survival Wave (Related to Players room) [Usage: 'StartWave <wave setting id> <wave population id>'] [HOST ONLY]
 - StopAllWave | Stop all Survival Wave [HOST ONLY]
 - StopWave | Stop Specific Survival Wave [Usage: 'StopWave <Wave ID (can be found using ListWave)>'] [HOST ONLY]
```
# World
```
 - BreakDoor | Break Door (Or even Closing Security Door) in your crosshair
 - BreakLock | Break Lock in your crosshair
 - Checkpoint | Checkpoint Reached! [HOST ONLY]
 - InsertBulkheadKey | Insert Bulkhead Key to DC in crosshair
 - InsertCell | Insert Powercell to Generator in crosshair
 - JumpDimension | Jump to specified Dimension [Usage: 'JumpDimension <Dimension Index>']
 - Open | Open Door/Locker in your crosshair
 - OpenAll | Open All Door/Locker in Level [Usage: 'OpenAll <door/weakdoor/secdoor/locker/all>']
 - SetFog | Set Fog Setting (Locally) [Usage: 'SetFog <FogDataID/Name>']
 - SetLight | Locally change the Light settings in current zone [Usage: 'SetLight [Light Settings ID] [Lights Sub Seed]']
 - SetTerminalState | Change the Terminal State in crosshair [Usage: 'SetTerminalState <TERM_State ID or name>']
 - StartFogTransition | Start Fog Transition (Network Synced) [Usage: 'SetFogTransition <FogDataID/Name> <Duration>']
 - Unlock | Unlock Door/Locker in your crosshair
 - UnlockAll | Unlock All Door/Locker in Level [Usage: 'UnlockAll <door/weakdoor/secdoor/locker/all>']
 - UnlockTerminal | Unlock Password Locked Terminal in crosshair
```
# Gizmo
```
 - EnemyPathingVisualizer | Draw lines for the path enemies are going to take and reveal scout path points [Usage: 'EnemyPathingVisualizer [-world / -overlay]']
 - GoodPositionVisualizer | Shows the point that you get warped to whenever you fall out of bounds
 - InvisibleWalls | Show (most) invisible walls in the level [Usage: 'InvisibleWalls [unlit/bioscan/glass/solid] [-show-ncbg]']
 - NavGizmo | Toggle Visibility of NavMesh and Off-Links
 - TScanHelper | Toggle the T-Scan Creation Helper GUI [Usage: 'TScanHelper [<Action> <Index>]']
 - WorldEventGizmo | Shows world event triggers [Usage: 'WorldEventGizmo [-nogui]']
```
# Misc
```
 - LoadExpedition | Force Load Expedition with Given Key [Usage: 'LoadExpedition <Tier Index (1-5)> <Expedition Index (0~)>']
 - ShaderHelper | Lists all shaders or shows a single shaders properties [Usage: 'ShaderHelper [Shader Name]']
```
