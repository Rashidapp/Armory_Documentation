## Installation

The Armory engine is distributed as a Blender add-on:
- [Download](https://www.blender.org/download/) Blender 2.83 LTS (using Armory with Blender 2.9 is not officially supported yet and might be unstable).
- [Download](https://armory3d.org/download.html) and unpack the Armory SDK.
- In Blender, select `Edit > Preferences...` and navigate to the `Add-ons` tab.
- Click the `Install...` button.
- Select the `armory.py` file located in the extracted `ArmorySDK` folder.
- Enable the Armory add-on in Blender: Simply click the checkbox next to `Render: Armory` from within `Preferences: Add-ons`.
- To verify that Armory was installed correctly:
  - Click on the small arrow that's on the left next to the now enabled checkbox in order to open the Armory settings page.
  - Check whether the `SDK Path` field contains the path to the Armory SDK folder (the SDK folder is the one that contains all the sub-folders: `armory`, `iron`, `Kha`, `Krom`, etc).
  - In case the `SDK Path` is blank: fill in the `SDK Path` field by clicking on the folder icon, then navigate to the location you have stored the Armory SDK folder and click on `Accept`.
  - Save your .blend file and hit the `Play` (F5) button, located in the `Properties > Render > Armory Player` panel to test whether the installation was successful.
  - If you don't see any user interface for Armory in Blender, check the console for error messages.

> **If you experience issues installing or using Armory, please look at [Wiki: Troubleshooting](https://github.com/armory3d/armory/wiki/troubleshooting) first. You can also open an issue in the [issue tracker](https://github.com/armory3d/armory/issues) on GitHub.**

> Armory comes with a version of [Haxe](https://haxe.org/) and [Kha](https://kha.tech/), so you don't need to install those components separately.

## Learn more
Continue to the [Playground tutorial](playground) to learn more.

## Code Editor

You can choose with which code editor Armory should open scripts.

- In Blender, select `Edit - Preferences...` and navigate to the `Add-ons` tab.
- Locate the Armory add-on.
- Activate `Show Advanced`
- Under `Code Editor` you can select the editor you want to use.

### System default
Armory tries to automatically select the correct editor. This works as follows:  
If an environment variable `VISUAL` is set, the editor is selected from the path specified there. If `VISUAL` does not exist, the environment variable `EDITOR`, which is actually intended for console-based editors, is used instead.
If both variables do not exist, the operating system tries to choose the correct editor itself.

### VS Code | Kode Studio (recommended)
- Download [Visual Studio Code](https://code.visualstudio.com/) + [Kha Extension pack](https://marketplace.visualstudio.com/items?itemName=kodetech.kha-extension-pack) or [Kode Studio](https://github.com/Kode/KodeStudio/releases).
- Point `Code Editor Executable` to the executable file of your installed copy.
- Inside VS code, make sure your paths are setup properly for the extensions:
  ```
  "haxe.executable": "ArmorySDK/Kha/Tools/haxe/haxe-linux64",
  "kha.khaPath": "ArmorySDK/Kha",
  "krom.kromPath": "ArmorySDK/Krom"
  ``` 

### Sublime Text
- Download [Sublime Text](https://www.sublimetext.com/) + (optional) [Haxe Bundle](https://packagecontrol.io/packages/Haxe) from Sublime's [PackageControl](https://packagecontrol.io/installation)
- Point `Code Editor Executable` to the executable file of your installed copy.
- Then, a basic _[project_name].sublime-project_ file gets created if it doesn't exist yet.

### Custom
- Point `Code Editor Executable` to the executable file of your custom editor.
