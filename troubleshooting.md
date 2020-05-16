# Troubleshooting

## Table of Content:
- [Troubleshooting Guide](#troubleshooting-guide)
  - [General](#general)
  - [Windows](#windows)
  - [Linux](#linux)
  - [macOS](#macos)
- [Common Issues](#common-issues)

## Troubleshooting Guide

### General

- For old graphics cards, create a `Mobile` path in `Properties - Render - Armory Render Path`.
- When naming folders/files for the SDK path and the individual projects files (.blend files), prefer only unaccented alphabetical letters `A-Z`, forbidden characters in folder and file names such as `[]` can cause issues too.
- If you have conflicts with data not updating correctly when launching your build, like textures not showing correctly, wrong normal/normal map, meshes not updating properly, etc., try cleaning the build cache by clicking the `Clean` button (see image below) that is next to the `Play` one in `Properties > Render > Armory Player`. If this doesn't solve the issue try disabling `Cache Build` in the `Armory Project` panel and try again.

  ![Screenshot: "Clean" button](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/troubleshooting/button_clean_build.jpg)
- If you have any trouble setting things up, raise a [new issue](https://github.com/armory3d/armory/issues).  

### Windows

- To see error messages, press `Menu bar - Window - Toggle System Console` in Blender.
- `Type not found : Main` error - save your .blend file in a safe path like `C:\Users\user_name\Documents\test`, otherwise Windows may prevent writing the files. Do not save .blend file to the drive root.
- If you get missing .dll errors, try installing [Visual C++ Redistributable for Visual Studio 2017](https://go.microsoft.com/fwlink/?LinkId=746572).

### Linux

- To see error messages, start Blender from terminal using `./blender`.

### macOS

- To see error messages, start Blender from terminal using `/blender.app/Contents/MacOS/blender`.

## Common Issues

_To search for a particular error/warning message, press `Ctrl` + `F` (`Cmd` + `F` on macOS)._
- ```Armory Warning: Logic node tree and generated trait names differ! Node tree: "[...]", trait: "[...]"``` <a name="warning-trait-names-differ"></a>
  
  This warning means that the specified node tree has a different name during runtime. Logic Nodes are converted to [Haxe classes](https://haxe.org/manual/types-class-instance.html) during project export and classes in Haxe must follow a set syntax. For example, class names must begin with an uppercase letter and must not contain dots. Node tree names in Blender do not have that restriction, so if a node tree name does not follow the Haxe syntax, it will be converted to a different, valid name.

  **Example**: if you have a node tree called `my.nodetree1`, it will be converted to `My_nodetree1` during export.

  In most cases, there is nothing to worry about when seeing this warning. It is important to know this fact when using the [`getTrait()`](https://armory3d.org/api/iron/Scene.html#getTrait) function in Haxe traits (e.g.) or when using a node that has a trait name input field, like [Get Trait](https://github.com/armory3d/armory/wiki/reference#get-trait). These functions/nodes will work with the converted names only.

  (_For more information on this, see [issue 1567](https://github.com/armory3d/armory/issues/1567))_

- ```Armory Warning: skipping export of the object [...] (collection [...]) because it has the same export name as another object in the scene: [...]```<a name="warning-skipping-export-of-object"></a>

  This is a rarely seen warning that is displayed if two objects in the scene have the same name at export time.

  During export, Armory converts the scene data to a file that Iron (Armory's [engine core](https://github.com/armory3d/armory/wiki/architecture#iron)) can read. Currently, Iron does not handle multiple objects with the same name but because Blender does that (for example if those objects are in different collections or linked from different files), some objects have to be renamed to ensure that Iron works correcly. For detailed reference about the renaming process, please take a look at `asset_name(bdata)` in [blender/arm/utils.py](https://github.com/armory3d/armory/blob/master/blender/arm/utils.py).

  Sometimes it can happen that the renamed object has the same name as an already existing object in the scene. If that is the case, that object (the order of exporting objects is not guaranteed!) is not exported to prevent obscure bugs from happening.

  (_For more information on this, see [pull request 1595](https://github.com/armory3d/armory/pull/1595))_

- ```No trait with the name [...] found, make sure that the trait is exported!```<a name="trait-not-exported"></a>

  This error occurs when using the [`Trait`](https://github.com/armory3d/armory/wiki/reference#trait) node with a trait that is not exported. Either the trait does not exist or it does exist but there is no object or scene that is using that trait.

  During export, only traits that are enabled on at least one user (scene or object) are exported and included in the game. If you need to access a trait that should not be activated at the start of the game, there is a [`Fake User`](https://github.com/armory3d/armory/wiki/traits#fake-user) option. When enabled, the trait will be exported even if it has no user object or scene.

  (_For more information on this, see [issue 1529](https://github.com/armory3d/armory/issues/1529))_