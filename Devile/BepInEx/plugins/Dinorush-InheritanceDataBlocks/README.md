# InheritanceDataBlocks

Allows developers to specify an additional field in any vanilla datablock, `parentID`. This causes the block to pull data from the given ID to fill any non-specified fields.

#### Example

```
GameData_ArchetypeDataBlock_bin.json

// Creates a new archetype using values from ID 5
// but with Damage and DefaultClipSize changed
{
    "Damage": 4,
    "DefaultClipSize": 50,
    "parentID": 5,
    "name": "Assault Rifle Upgraded",
    "persistentID": 205
},
// Creates a new archetype using values from ID 205 (which borrows from ID 5)
// but with Damage and DefaultReloadTime changed
{
    "Damage": 5,
    "DefaultReloadTime": 1.0,
    "parentID": 205,
    "name": "Assault Rifle Upgraded Stage 2",
    "persistentID": 305
}
```