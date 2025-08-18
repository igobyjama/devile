# MovementSpeedAPI

Adds an API for plugin developers to modify movement speed to avoid conflicts between mods.

## API

To add a modifier, call the function:

```cs
ISpeedModifier MoveSpeedAPI.AddModifier(float mod, StackLayer layer = StackLayer.Multiply, string groupName = "Default");
```
Where the parameters are:
- `mod`: The value of the modifier to apply.
- `layer`: Which layer the modifier is added to. Determines how it stacks with other modifiers.
  - Options: Multiply, Add, Max, Min, Override
- `groupName`: Which group to put the modifier in. Layers only apply within each group; separate groups are multiplied.

`AddModifier` returns the created `ISpeedModifier` object. The modifier provides methods to update its value or remove itself:

```cs
public interface ISpeedModifier
{
  // The value of the modifier. Updates when modified if active.
  public float Mod { get; set; }

  // The layer the modifier is on.
  public StackLayer Layer { get; }

  // Whether the modifier is active.
  public bool Active { get; }

  // Enables the modifier if it is inactive.
  public void Enable();

  // Sets Mod to the value and enables the modifier if it is inactive.
  public void Enable(float mod);

  // Disables/removes the modifier.
  public void Disable();
}
```

*Note: All modifiers are disabled on level cleanup. If you wish to use the same modifier across drops, make sure to Enable it.*

## Examples

#### Simple Timed Buff

```cs
public void AddSpeedBuff(float mod, float duration) {
  CoroutineManager.StartCoroutine(IEnumerator(mod, duration).WrapToIl2Cpp());
}

private IEnumerator RunSpeedBuff(float mod, float duration) {
  var modifier = MoveSpeedAPI.AddModifier(mod);
  yield new WaitForSeconds(duration);
  modifier.Disable();
}
```

#### Simple Persistent Buff

```cs
ISpeedModifier? _activeModifier = null;

public void SetSpeedBuff(float mod) {
  if (_activeModifier == null)
  {
    _activeModifier = MoveSpeedAPI.AddModifier(mod);
  }
  else
  {
    _activeModifier.Enable(mod);
  }
}
```