# AWOPartialDataFixer
## what it is:
100% replacement for MTFO.Ext.PartialData, supports AWO and Inheritance.

Use the AWO number enums to define events please.

- 10000 CloseSecyrityDoor
- 10001 LockSecurityDoor
- 10002 SetDoorInteraction
- 10003 TriggerSecurityDoorAlarm
- 10004 SolveSecurityDoorAlarm
- 10005 StartReactor
- 10006 ModifyReactorWaveState
- 10007 ForceCompleteReactor
- 10008 ForceCompleteLevel
- 10009 ForceFailLevel
- 10010 Countdown
- 10011 SetLevelFailCheckEnabled
- 10012 SetLevelFailWhenAnyPlayerDowned
- 10013 KillAllPlayers
- 10014 KillPlayersInZone
- 10015 SolveSingleObjectiveItem
- 10016 SetLightDataInZone
- 10017 AlertEnemiesInZone
- 10018 CleanupEnemiesInZone
- 10019 SpawnHibernateInZone
- 10020 SpawnScoutInZone
- 10021 SaveCheckpoint
- 10022 MoveExtractionWorldPosition
- 10023 SetBlackoutEnabled
- 10024 AddTerminalCommand
- 10025 HideTerminalCommand
- 10026 UnhideTerminalCommand

example: 
"Type": "CloseSecurityDoor", 
becomes
"Type": 10000,

source: https://github.com/Dinorush/PartialDataModCompatible


## Changelog

### V1.5.1
- removed hard deps for both injectlib and inheritance. dinorush, thank you kindly for all you've dnoe for this and me.

### V1.5.0
- dinorush compiled this after integrating inheritance support. thank you dino! inheritance is based af, god-tier stuff.

### V0.0.5
- removes dependency to actual partialdata and AWO_Testing. This works as a replacement to partialdata, and people can decide which AWO to use, Flow's original or hirnu's pathetic imitation. " :D "

### V0.0.4
- partialdata converter based fix, tested to work with og captivity c2. presents itself as partialdata v1.4.4
- will do a PR for flow so this can be deprecated once pdata itself updates.
- thank you flowaria very much for the fix and the -teach.

### V0.0.3
- bepinplugin name change, nothing more.

### V0.0.2
- some sanity checks on objects so we don't crash on missing EventsOnXXX

### V0.0.1
- CloseSecurityDoor (10000) works, pushing it out so people can test others.
