# ComponentAddress
> ###### Location: `LW/Server/LogicAPI.dll` : `LogicAPI.Data` > `ComponentAddress`

> ### NOTE
> This section is very much **INCOMPLETE**.

### Instanced
``` cs
public uint ID { get; }
public int Size => 4;
public ComponentAddress(uint id);
public override bool Equals(object obj);
public override int GetHashCode();
public override string ToString();
```

### Statics
```cs
ComponentAddress.Parse(string text); // Needs to be understood
ComponentAddress.Null; // returns ComponentAddress of ID (0u)
```

```js
// Valid operations
ComponentAddress == ComponentAddress
ComponentAddress != ComponentAddress
```