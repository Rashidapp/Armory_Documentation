Armory engine is distributed as a Blender add-on:
- [Download](https://www.blender.org/download/) Blender 2.82.
- [Download](https://armory3d.org/download.html) and unpack Armory SDK.
- In Blender, Select `Edit - Preferences...` and navigate to the `Add-ons` tab.
- Click `Install...` button.
- Select `armory.py` file located in the extracted `ArmorySDK` folder.
- Enable Armory add-on in Blender: Simply click the checkbox next to `Render: Armory` from within `Preferences: Add-ons`.
- Pick SDK Directory : (Optional, only in case the `SDK Path` is blank) still in the Armory add-on settings in Blender Preferences: fill the `SDK Path` field by clicking on the folder icon, then navigate to the location you have stored the Armory SDK folder (the SDK folder is the one that contains all the sub-folders: `armory`, `iron`, `Kha`, `Krom`, etc), and then click "Accept".

---
---


- Restart Blender if your add-on doesn't load right away.
- To verify everything is working correctly, save your .blend file and hit `Play` (F5) button, located in the `Properties - Render - Armory Player` panel.
- Continue to the [Playground tutorial](playground) to learn more.
- Armory comes with a version of haxe and kha.

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
