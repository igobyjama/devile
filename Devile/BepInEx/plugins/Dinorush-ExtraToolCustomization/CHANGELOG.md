## v1.5.3

- Fixed sentry being unable to target enemies when placed in a different room than the user

## v1.5.2

- Improved sentry targeting for non-legacy targeting sentries

## v1.5.1

- Fixed Bot-placed mines not using custom mine data
- Fixed an error that would occur when other players spawned with a Mine Deployer
- (Potentially) Fixed checkpoints causing mines to apply custom data only to the previously placed mine

## v1.5.0

- Added Sentry field:
  - FriendlyDamageMulti: Damage multiplier when hitting friendly players
- Added a bug fix for sentries that ran out of ammo while firing shooting a bullet when given ammo again
- Fixed some cross-plugin issues with customized sentries, especially shotgun sentries

## v1.4.2

- Fixed sentry ammo overflowing if given ammo from GtfXP while sentry is deployed.

## v1.4.1

- Added a fix to prevent tool ammo from resetting to 100% from any change when above 100%.

## v1.4.0

- Added Mine fields:
  - BeamData: Contains "Color", "Length", and "Width" fields.
  - LightData: Contains "Color", "Intensity", and "Range" fields.
- Added Sentry fields:
  - DeployTime: Time it takes for the sentry to deploy.
  - ScanDelay: Time it takes for the sentry to begin scanning after deploying or losing a target.
    - Note: Also affects the minimum time a sentry remains locked when a target is found.
  - PlacementTime: Time it takes to place the sentry.
  - PickupTime: Time it takes to pick up the sentry.
  - ScanColor: The color of the scan beam.
  - TargetColor: The color of the scan beam when a target is locked.
- Added Configuration file with an option to forcibly recreate the template files.
- Fixed Sentry settings not applying
- Fixed mine settings not syncing to clients

## v1.3.2

- Fixed consumable mines not being affected by PlacementTime or PlacementCooldown

## v1.3.1

- Fixed LiveEdit not functioning for the Mine folder

## v1.3.0

- Fixed most custom mine data not applying for clients

## v1.2.0

- Sentry custom files now use "ArchetypeID" instead of "OfflineID".
- Fixed client sentry guns dealing no damage.

## v1.1.4

- Renamed Mine field:
  - PlacementTime -> PlacementCooldown
- Added Mine fields:
  - PlacementTime: Time it takes to place a mine.
  - PickupTime: Time it takes to pick up a mine.

## v1.1.3

- Fixed the error again because I can't read

## v1.1.2

- Fixed an error that occurred when there are two customizations for the same itemID

## v1.1.1

- Added Mine field:
  - PlacementTime: Delay before you can act after placing a mine.

## v1.1.0

- Added sentry customization:
  - Only option currently is "BackDamage" enabled or disabled.
- Fixed sentry loadout text not pulling from Archetype.

## v1.0.0

- Initial Release