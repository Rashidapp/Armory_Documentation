## Troubleshooting

- For old graphics cards, create a `Mobile` path in `Properties - Render - Armory Render Path`.
- When naming folders/files for the SDK path and the individual projects files (.blend files), prefer only unaccented alphabetical letters `A-Z`, forbidden characters in folder and file names such as `[]` can cause issues too.
- If you have conflicts with data not updating correctly when launching your build, like textures not showing correctly, wrong normal/normal map, meshes not updating properly, etc., try cleaning the build cache by clicking the `Clean` button that is next to the `Play` one in the `Armory Player` panel in the `Render` Properties. If this doesn't solve the issue try disabling `Cache Build` in the `Armory Project` panel and try again.
- If you have any trouble setting things up, raise a [new issue](https://github.com/armory3d/armory/issues).  

### Windows

- To see error messages, press `Menu bar - Window - Toggle System Console` in Blender.
- `Type not found : Main` error - save your .blend file in a safe path like `C:\Users\user_name\Documents\test`, otherwise Windows may prevent writing the files. Do not save .blend file to the drive root.
- If you get missing .dll errors, try installing [Visual C++ Redistributable for Visual Studio 2017](https://go.microsoft.com/fwlink/?LinkId=746572).

### Linux

- To see error messages, start Blender from terminal using `./blender`.

### macOS

- To see error messages, start Blender from terminal using `/blender.app/Contents/MacOS/blender`.