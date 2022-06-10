# Component Address
Location: `LW/Server/LogicAPI.dll` : `LogicAPI.Data` > `ComponentAddress`

> ### NOTE
> This section is very much **INCOMPLETE**.

``` cs
public static readonly ComponentAddress Null = new ComponentAddress(0u);
public uint ID { get; }
public int Size => 4;
public ComponentAddress(uint id);
public override bool Equals(object obj);
public override int GetHashCode();
public override string ToString();
public static ComponentAddress Parse(string text);
public static bool operator ==(ComponentAddress a, ComponentAddress b);
public static bool operator !=(ComponentAddress a, ComponentAddress b);
```