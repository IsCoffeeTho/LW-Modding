# LW - C\# Modding
### Introduction
> ### NOTE
> This is still being worked on, if there is any issues or problems with the guide
> please do bring it up in an issue or make a pull request with the changes.
___
### File Structure

There are two folders required. A mod loader, and the mod itself. The full structure looks like this. Individual elements will be explained further later.
```
Logic World/GameData/
└── <mod>/
    ├── components/
    │   └── <component-group>.succ
    ├── src/
    │   └── server/
    │       ├── ServerMod.cs
    │       └── <component script>.cs   #optional
    ├── manifest.succ
    └── ignore #optional
```
```cs
// ServerMod.cs
using LogicAPI.Server;
using LogicLog;

public class Loader : ServerMod
{
    protected override void Initialize()
	{
        Logger.Info("Mod loaded");
    }
}
```
```js
# manifest.succ

ID: exampleID
Name: exampleName
Author: exampleAuthor
Version: 1.0
Priority: 1
```

![Loaded Mods Menu](https://user-images.githubusercontent.com/7610940/138955141-7165ec2f-a975-42ad-919c-c91c15ebc615.png)

> ### **NOTE**
> The SUCC format requires that the tabulature of property is four spaces (`U+0020`).
> Tabs (`U+0009`) will not work

___
### Components

Components are the structures players are given to create circuits in their creative ways.
See the examples in:
`LW/GameData/MHG/Components/`

Components will appear in the item menu as `<modID>.<componentId>` with both elements being substituted out for their represented data.

Here is an example compone
```succ
# <mod>/components/<component>.succ

exampleComponent:
    column: "Logic"
	category
    prefab:
        blocks:
            - Standard
        inputs:
            -
                position: (0, 0.5, -0.5)
                rotation: (-90, 0, 0)
        outputs:
            -
                position: (0, 0.5, 0.5)
                rotation: (90, 0, 0)
    logicCode: exampleID.exampleComponent
    placingRules:
        gridPlacingDimensions: (2, 1)
...
```

The item from the `.succ` above would appear in-game as:
![exampleID.exampleComponent](https://user-images.githubusercontent.com/7610940/138955557-42657956-80c9-4778-9743-2ffcd2a55edf.png)
___
### Scripting
Scripts are stored in the folders inside `<mod>/src/...` such as `client/`, `server/`, &  `shared/` folders.

Here is an example for the example component above:
```cs
// <mod>/src/server/exampleMod-exampleComponent.cs

using LogicAPI.Server.Components;
/* Required for LogicComponent Class */

namespace exampleID
{
	public class exampleComponent : LogicComponent
	{
		protected override void DoLogicUpdate()
		{
			base.Outputs[0].On = base.Inputs[0].On;
		}
	}
}
```

This example simply sets the single output to the single input each time the component is updated by 
More info on [LogicComponent](Reference/CS-LogicComponent.md).

> ### **NOTE**
> Anything used in code referenced using logicCode in your succ file **MUST** be in here, the rest will not be loaded by the time the component types are compiled. You'll have to use reflection for anything external (so probably just accept the big file). You should prefix the filename with the same name as the mod folder so it's easier to find and delete when removing the mod
___
#### `<mod>/ignore`
If this file is present, the mod will not be loaded. This is useful if you want to keep a mod downloaded, but not installed.

When adding or removing the `ignore` file, you just have to reload the world or restart the server.