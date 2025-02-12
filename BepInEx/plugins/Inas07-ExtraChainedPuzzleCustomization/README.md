This plugin allows you to further customize your security scan, including:

- Custom static bioscan point position.
- Custom T-scan:
  - Custom movement speed 
  - Custom T-scan travel path
- Cluster T-scan (i.e. multiple T-scan at the same time).
- Add 'required items to scan' to your puzzle.
  - This is also possible: add different required items to different children scan of a cluster scan.
- Setup concurrent cluster scan (which means: for a cluster scan, all child scans must progress simultaneously).
- Execute warden events when the bioscan / cluster scan is solved.
- Execute warden events when reached certain progress.

Documentation of this plugin: 
https://github.com/Inas-07/ExtraChainedPuzzleCustomization/wiki

# How to use:
1. Toss this plugin into your `BepInEx/plugins` folder.
2. Start your game.
3. There should me files generated in your `BepInEx/plugins/YOUR_RUNDOWN/Custom/ScanPositionOverrides`
4. Supports Partial Data.
5. Supports `AWO`.
