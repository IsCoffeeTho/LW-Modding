# `class` PegAddress
> ###### Location: `LW/Logic_World_Data/Managed/LogicAPI.dll` : `LogicAPI.Data` > `PegAddress`

```cs
// Fields
public ComponentAddress ComponentAddress { get; }
public int PegNumber { get; }
public abstract bool IsInput { get; }
public int Size => 5 + ComponentAddress.Size + 1;
```

```cs
// Methods
public override string ToString();
public override int GetHashCode();
public override bool Equals(object obj);
```

```cs
// Static Methods
PegAddress PegAddress.Parse(string text);
PegAddress PegAddress.Create(bool isInput, ComponentAddress componentAddress, int pegNumber);
```

```js
// Comparison
PegAddress == PegAddress
PegAddress != PegAddress
```