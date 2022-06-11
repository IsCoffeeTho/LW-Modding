# Output Peg
> ###### Location: `LW/Server/LogicAPI.Server.dll` : `LogicAPI.Server.Components` > `IOutputPeg`

This is the type of the members of the list [`LogicComponent.Outputs[]`](CS-LogicComponent.md#logiccomponent-structure)

### OutputPeg Structure
|   Field   |               Type               |     Access      |                  Description                  |
| :-------- | :------------------------------- | :-------------- | :-------------------------------------------- |
| `Address` | [`PegAddress`](CS-PegAddress.md) | `{ get; }`      | Inherited from [`interface IPeg`](CS-IPeg.md) |
| `On`      | `bool`                           | `{ get; set; }` | Returns the signal state of the peg.          |