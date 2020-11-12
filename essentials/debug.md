# Debug

## Table of Content:
- [Debug Console](#debug-console)
  - [Scene](#scene)
    - [Trait Debug View](#trait-debug-view)
  - [Performance and Graphics](#-ms-the-performance-and-graphics-tab)
  - [Console](#console)
- [IDE Debugging](#ide-debugging)
- [RenderDoc](#renderdoc)

## Debug Console
Armory has an integrated debug console that displays some basic information about the scene, its objects, the performance and graphics information in realtime. It also enables you to temporarily change some settings directly from inside the running game.

To enable it, activate `Armory Project > Flags > Debug Console`. You must enable Zui at `Armory Project > Modules > Zui > [Auto or Enabled]` in order for this option to be available. If the debug console is enabled, it will show up in the upper right corner when the game starts. You can drag the debug console around by clicking on its top border.

There are 3 tabs, you can click on them to open the corresponding view:
- ### Scene
  The `Scene` tab displays information about the scene and its objects. You can select objects and scenes by clicking on them in the outliner. If an object is selected, the `Properties` panel will show some basic information about the object like its transform values, its traits and depending on the object type even more values. Some of them are editable.

  ![Scene view screenshot](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/debug/debug_console_scene.jpg)

  #### Trait Debug View
  Every trait has its own debug view that is freely draggable like the debug view itself. You can enable it by clicking on `Details` on the right side of the trait in the trait list. When opened, it remains pinned until closed again, so you can open multiple trait views at once. To close the debug view, click on `Close Trait View`.

  ![Trait debug view screenshot](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/debug/debug_console_trait_details.jpg)

  The trait debug view shows some basic information about the trait (its class name + path, its superclass and the object/scene name) and under `Attributes`, it displays the full list of trait attributes in realtime. This can replace some annoying `trace()` calls in your code.

- ### [...] ms (the Performance and Graphics tab)

  ![Trait debug view screenshot](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/debug/debug_console_performance.jpg)
  
  #### Performance
  This panel displays information about the performance of your game. You can see the overall frame time and the time required by individual parts of the engine.

  #### Draw
  This panel shows some statistics related to the scene drawing.

  #### Render Targets
  Here you can see all current render targets in realtime.

  #### Cached Materials
  The list of cached materials.

  #### Cached Shaders
  The list of cached shaders.

- ### Console
  ![Trait debug view screenshot](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/debug/debug_console_console.jpg)

  #### Script
  This panel allows you to run basic Haxe expressions from inside the game.

  #### Log
  This panel shows the console output. Especially handy on macOS and Linux operating systems because you don't have to run Blender from the console to see its output. On Windows, you can toggle the Blender console by using `Window > Toggle System Console`.

  To clear the log view, press `Clear`.

**To close the debug view again, you can click on the fourth "hidden" tab left to the `Scene` tab.**

## IDE Debugging
Click `Armory Project - Kode Studio` to open the bundled integrated development environment. Kode Studio is based on Visual Studio Code and comes preconfigured for Kha-based projects.

Armory project can be launched directly from Kode Studio by pressing `F5`. Kode Studio contains debug support for Krom and lets you place breakpoints.

![Kode Studio screenshot](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/kode.png)

When compiling to one of the C targets, native project files are generated. This makes it easy to debug and profile Armory projects in Visual Studio or XCode IDE.

## RenderDoc

For graphics debugging, check out RenderDoc.

- Install from https://renderdoc.org/
- Export to `Windows (Krom)`, `Linux (Krom)` or `macOS (Krom)`
- Press `Publish`
- Click on the down arrow in the sidebar of the export target list and choose `Open in RenderDoc`:  
  ![How to open RenderDoc](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/debug/open_renderdoc.jpg)
- Hit `Launch` in RenderDoc to start debugging!