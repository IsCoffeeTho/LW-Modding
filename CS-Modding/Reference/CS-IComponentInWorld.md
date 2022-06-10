# IComponentInWorld
Location: `LW/Server/LogicAPI.dll` : `LogicAPI.Data` > `IComponentInWorld`

> ### NOTE
> This section is very much **INCOMPLETE**.

### IComponentInWorld Interface
Field | Type | Access | Description
:-- | :-- | :-- | :--
`Data` | [`ComponentData`](./CS-ComponentData.md) | `{get;}` | No Information.
`Parent` | [`ComponentAddress`](./CS-ComponentAddress.md) | `{get;}` | No Information.
`ChildCount` | `int` | `{get;}` | No Information.
`WorldPosition`| [`Vector3`](https://docs.unity3d.com/ScriptReference/Vector3.html) | `{get;}` | No Information.
`WorldRotation` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | No Information.
`LocalPosition`| [`Vector3`](https://docs.unity3d.com/ScriptReference/Vector3.html) | `{get;}` | No Information.
`LocalRotation` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | Unknown
`up` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | No Information.
`forward` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | No Information.
`localRight` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | No Information.
`localUp` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | No Information.
`localForward` | [`Quaternion`](https://docs.unity3d.com/ScriptReference/Quaternion.html) | `{get;}` | No Information.

### Methods

```cs
IEnumerable<ComponentAddress> EnumerateChildren();
```
No Information.
&nbsp;
```cs
bool ContainsChild(ComponentAddress cAddress);
```
No Information.
&nbsp;
```cs
Vector3 ToLocalSpace(Vector3 worldSpace);
```
No Information.
&nbsp;
```cs
Vector3 ToWorldSpace(Vector3 localSpace);
```
No Information.