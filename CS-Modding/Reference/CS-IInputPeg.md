# `interface` IInputPeg
> ###### Location: `LW/Server/LogicAPI.Server.dll` : `LogicAPI.Server.Components` > `IInputPeg`

This is the type of the members of the list [`LogicComponent.Inputs[]`](CS-LogicComponent.md#logiccomponent-structure)

### InputPeg Structure
|   Field   |               Type               |   Access   |                  Description                  |
| :-------- | :------------------------------- | :--------- | :-------------------------------------------- |
| `Address` | [`PegAddress`](CS-PegAddress.md) | `{ get; }` | Inherited from [`interface IPeg`](CS-IPeg.md) |
| `On`      | `bool`                           | `{ get; }` | Returns the signal state of the peg           |

## Methods
### Secret Links
```cs
void AddSecretLinkWith(IInputPeg otherInput);
```
Will secretly link a peg to another. This will link the value of two pegs together.
&nbsp;
```cs
void RemoveSecretLinkWith(IInputPeg otherInput);
```
Will remove a secret link to the specified peg, and will also set the value of the otherInput to its preferred value that of other logic.
&nbsp;
```cs
void RemoveAllSecretLinks();
```
Will remove **ALL** secret links to and from the specified peg.
&nbsp;
### Phasic Links
Differences between Secret and Phasic links aren't discernable enough in behaviour  to be documented. If you find anything worth documenting, please do make an issue or pull request with new findings.
```cs
void AddPhasicLinkWith(IInputPeg otherInput);
```
Will phasically link a peg to another. This will link the value of two pegs together.
&nbsp;
```cs
void RemovePhasicLinkWith(IInputPeg otherInput);
```
Will remove the phasic link to the specified peg, and will also set the value of the `otherInput` to its preferred value that of other logic.
&nbsp;
### Unsafe Phasics
Differences aren't very discernable between safe and unsafe phasic links. If you find anything worth documenting, please do make an issue or pull request with new findings.
```cs
void AddPhasicLinkWithUnsafe(IInputPeg otherInput);
```
Will phasically link a peg to another unsafely. This will link the value of two pegs together.
&nbsp;
```cs
void RemovePhasicLinkWithUnsafe(IInputPeg otherInput);
```
Will remove the phasic link to the specified peg unsafely, and will also set the value of the `otherInput` to its preferred value that of other logic
&nbsp;
### One Way
Will force a Diode effect
```cs
void AddOneWayPhasicLinkTo(IInputPeg otherInput);
```
Will force a pegs value upon another peg, as to not allow back propagation of signals. This will create a one way travel path for a signal as it only goes in the direction of `A -> B`.
&nbsp;
```cs
void RemoveOneWayPhasicLinkTo(IInputPeg otherInput);
```
Will remove such link to the specified peg, and will also set the value of the `otherInput` to its preferred value that of other logic.