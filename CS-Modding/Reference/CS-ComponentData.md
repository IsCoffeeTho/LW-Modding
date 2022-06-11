# ComponentData
> ###### Location: `LW/Server/LogicAPI.dll` : `LogicAPI.Data` > `ComponentData`

> ### NOTE
> This section is very much **INCOMPLETE**.

```cs
public ComponentType Type { get; }
public IReadOnlyList<InputInfo> InputInfos { get; }
public IReadOnlyList<OutputInfo> OutputInfos { get; }
public int InputCount { get; set; }
public int OutputCount { get; set; }
public byte[] CustomData { get;}
public ComponentAddress Parent { get;}
public Vector3 LocalPosition { get; }
public Quaternion LocalRotation { get; }
InputInfo[] IEditableComponentData.InputInfos { get; set;}
OutputInfo[] IEditableComponentData.OutputInfos { get; set; }
byte[] IEditableComponentData.CustomData { get; set; }
ComponentAddress IEditableComponentData.Parent { get; set; }
Vector3 IEditableComponentData.LocalPosition { get; set; }
Quaternion IEditableComponentData.LocalRotation { get; set; }
public int Size { get; set; }
public ComponentData(ComponentType type);
```