# `class` LogicComponent\<TData\>
> ###### Location: `LW/Server/LogicAPI.Server.dll` : `LogicWorld.Server.Circuitry` > `LogicComponent<TData>`

A variant on [`class` LogicComponent](CS-LogicComponent.md) that contains automatically handled CustomData, including convenient typing.

> ##### NOTE From MHG:
> ###### This is intended for simple components, those with just a few custom data properties. If your component has a huge crazy amount of custom data, like a RAM block, you should use [ComponentData.CustomData](CS-ComponentData.md#:~:text=CustomData) directly.

```cs
private ICustomDataManager<TData> DataManager;
public TData Data => DataManager.Data;
protected override byte[] SerializeCustomData();
protected override void DeserializeData(byte[] data);
protected abstract void SetDataDefaultValues();
```