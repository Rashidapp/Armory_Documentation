Armory engine is distributed as a Blender add-on:
- [Download](https://www.blender.org/download/) Blender 2.80.
- [Download](https://armory3d.org/download.html) and unpack Armory SDK.
- In Blender, Select `Edit - Preferences...` and navigate to the `Add-ons` tab.
- Click `Install...` button.
- Select `armory.py` file located in the extracted `ArmorySDK` folder.
- Enable Armory add-on in Blender.
- Point `SDK Path` property to the extracted `ArmorySDK` folder.
---
- To verify everything is working correctly, save your .blend file and hit `Play` (F5) button, located in the `Properties - Render - Armory Player` panel.
- Continue to the [Playground tutorial](playground) to learn more.
- Armory comes with a version of haxe and kha.

## Troubleshooting

- For old graphics cards, create a `Mobile` path in `Properties - Render - Armory Render Path`.
- When naming folders/files, prefer unaccented alphabetical letters `A-Z`.
- If you have any trouble setting things up, raise a [new issue](https://github.com/armory3d/armory/issues).

### Windows

- To see error messages, press `Menu bar - Window - Toggle System Console` in Blender.
- `Type not found : Main` error - save your .blend file in a safe path like `C:\Users\user_name\Documents\test`, otherwise Windows may prevent writing the files. Do not save .blend file to the drive root.
- If you get missing .dll errors, try installing [Visual C++ Redistributable for Visual Studio 2017](https://go.microsoft.com/fwlink/?LinkId=746572).

### Linux

- To see error messages, start Blender from terminal using `./blender`.

### macOS

- To see error messages, start Blender from terminal using `/blender.app/Contents/MacOS/blender`.

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
