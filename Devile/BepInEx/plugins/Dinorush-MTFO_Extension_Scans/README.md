Adds additional fields for MTFO scans. These can be used in `Custom/PuzzleTypes.json` within the `Scans` blocks.

### Fields
- `"FullTeamScanMulti": float` - The multiplier on scan progress used when the entire team is in the scan, regardless of how large or small the team is.
- `"PerTeamSizeScanMultis": list[list[float]]` - Similar to PlayersInScanMulti, except that each list only takes effect when the corresponding number of players are in the game. The first list corresponds to solo, the second to duo, and so on.
  - If the list for the current player count doesn't exist or is empty, the next populated list is used. If that does not exist, PlayersInScanMulti applies instead.
  - Lists autofill upwards. For instance, `[0.5, 1]` is equivalent to `[0.5, 1, 1, 1]`.

### Example
These flash scans do not scale with the number of players in the scan. However, they instantly complete if the entire team enters them.
These null scans do not scale with the number of players in the scan either, but are faster if there are fewer players in the lobby.

```json
// PuzzleTypes.json
{
  "Scans": [
    {
      "Name": "Big Orange Flash Scan ; instant with team",
      "BaseScan": 2,
      "PersistentID": 106,
      "PlayerRequirement": 0,
      "ScanRadius": 3.25,
      "FullTeamScanMulti": 9999.0, // <-- A new field!
      "PlayersInScanMulti": [0.125, 0.125, 0.125, 0.125],
      "ReduceSpeed": 0.0,
      "ReduceWhenNoPlayer": false,
      "RevealMode": "ScaleByDistance",
      "BioScanGraphics": {
      "ScanText": "Flash Scan\nInstant With Team",
        "Radius": 3.25,
        "colorModeColor": [
          { "mode": 1, "r": 1.0, "g": 0.6, "b": 0.0, "a": 1.0 },
          { "mode": 2, "r": 1.0, "g": 0.35, "b": 0.0, "a": 1.0 },
          { "mode": 4, "r": 1.0, "g": 0.6, "b": 0.0, "a": 1.0 },
          { "mode": 5, "r": 1.0, "g": 0.35, "b": 0.0, "a": 1.0 }
        ]
      }
    },
    {
      "Name": "Big Blue Null Scan ; no team scaling",
      "BaseScan": 2,
      "PersistentID": 108,
      "PlayerRequirement": 0,
      "ScanRadius": 2.25,
      "PerTeamSizeScanMultis": [ // <-- A new field!
        [0.3], // Solo
        [0.24],// Duo
        [0.2]  // Trio
        // Four is omitted here, so PlayersInScanMulti is used instead.
      ],
      "PlayersInScanMulti": [0.18, 0.18, 0.18, 0.18],
      "ReduceSpeed": 0.0,
      "ReduceWhenNoPlayer": false,
      "RevealMode": "ScaleByDistance",
      "BioScanGraphics": {
      "ScanText": "Null Scan\nNo Scaling",
        "Radius": 2.25,
        "colorModeColor": [
          { "mode": 1, "r": 0.0, "g": 0.0, "b": 1.0, "a": 1.0 },
          { "mode": 2, "r": 0.25, "g": 0.25, "b": 0.75, "a": 1.0 },
          { "mode": 4, "r": 0.0, "g": 0.0, "b": 1.0, "a": 1.0 },
          { "mode": 5, "r": 0.25, "g": 0.25, "b": 0.75, "a": 1.0 }
        ]
      }
    },
    // ...
  ]
  "Clusters": [
    // ...
  ]
}
```