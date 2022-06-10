# Component Data
Location: `LW/Server/LogicAPI.dll` : `LogicAPI.Data` > `ComponentData`

> ### NOTE
> This section is very much **INCOMPLETE**.

```cs
private InputInfo[] _InputInfos;
private OutputInfo[] _OutputInfos;
private const int NullMarkSize = 1;
private const int ArrayLengthSize = 4;
public ComponentType Type { get; }
public IReadOnlyList<InputInfo> InputInfos => _InputInfos;
public IReadOnlyList<OutputInfo> OutputInfos => _OutputInfos;
public int InputCount => InputInfos?.Count ?? 0;
public int OutputCount => OutputInfos?.Count ?? 0;
public byte[] CustomData { get; private set; }
public ComponentAddress Parent { get; private set; }
public Vector3 LocalPosition { get; private set; }
public Quaternion LocalRotation { get; private set; } = Quaternion.identity;
InputInfo[] IEditableComponentData.InputInfos { get; set;}
OutputInfo[] IEditableComponentData.OutputInfos { get; set; }
byte[] IEditableComponentData.CustomData { get; set; }
ComponentAddress IEditableComponentData.Parent { get; set; }
Vector3 IEditableComponentData.LocalPosition { get; set; }
Quaternion IEditableComponentData.LocalRotation { get; set; }
public int Size;
public ComponentData(ComponentType type);
```