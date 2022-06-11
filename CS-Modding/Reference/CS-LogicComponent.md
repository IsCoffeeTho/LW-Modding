# LogicComponent
> ###### Location: `LW/Server/LogicAPI.Server.dll` : `LogicAPI.Server.Components` > `LogicComponent`

### LogicComponent Structure
|         Field         |                       Type                       |    Access     |                                     Description                                      |
| :-------------------- | :----------------------------------------------- | :------------ | :----------------------------------------------------------------------------------- |
| `LogicUpdateQueued`   | `bool`                                           | `{get;}`      | Returns whether there is a LogicUpdate waiting to tick over.                         |
| `Component`           | [`IComponentInWorld`](./CS-IComponentInWorld.md) | `{get;}`      | Returns the `ComponentDataManager` of the component.                                 |
| `Address`             | [`ComponentAddress`](./CS-ComponentAddress.md)   | `{get;}`      | Returns the `Address` of the component.                                              |
| `base.Inputs`         | [`IInputPeg[]`](./CS-IInputPeg.md)               | `{get;}`      | This contains a list of the `InputPegs` of the component.                            |
| `base.Outputs`        | [`IOutputPeg[]`](./CS-IOutputPeg.md)             | `{get;}`      | This contains a list of the `OutputPegs` of the component.                           |
| `ComponentData`       | [`ComponentData`](./CS-ComponentData.md)         | `{get;}`      | Returns the `ComponentDataManager` of the component.                                 |
| `HasPersistantValues` | `bool`                                           | `{get; set;}` | This allows the script to tell the game that it must be serialized in a special way. |
---
## Methods
```cs
protected override void Initialize();
```
Similar to the injection point `int main();` in C, this function is called immediately after component is placed in world.
&nbsp;
```cs
protected override void DoLogicUpdate();
```
This is called once after initialization, and after each update to input pegs that are allowed by the `InputAtIndexShouldTriggerComponentLogicUpdates(int inputIndex);`.
&nbsp;
```cs
public override IReadOnlyList<bool> GetOutputStartStates();
```
Called once when before `Initialize();` to set the outputs on or off before any logic is applied.
&nbsp;
```cs
public override bool InputAtIndexShouldTriggerComponentLogicUpdates(int inputIndex);
```
This function determines whether an input peg will call `DoLogicUpdate();` acting as a Clock pin if only one peg results as true.
&nbsp;
```cs
public override void OnComponentMoved();
```
Called when the component moved in world.
&nbsp;
```cs
public override void OnComponentDestroyed();
```
Called when the component is destroyed.
&nbsp;
```cs
public override void Dispose();
```
Called when the component is disposed.
___
### Custom Serialization
```cs
protected override bool OnCustomDataUpdated();
```
Called when the Custom Data of the component is updated.
&nbsp;
```cs
protected override byte[] SerializeCustomData();
```
Used to serialize the Custom Data of the component for saving.
&nbsp;
```cs
protected override void DeserializeData();
```
Used to deserialize the custom data of the component for loading.

# LogicComponent\<TData\>
This is a special variant of LogicComponent that makes using custom data easier
  
It takes a generic argument which is a class that contains the data of the component
  
And it overrides the serialize and deserialize functions to bytewise write the and read the properties of the data class
