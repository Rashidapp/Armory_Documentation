# Navmesh

Armory is designed to work with any navigation engine. Internally, a glue code is written which binds the engine. By default, Armory is configured to use [Recast navigation](https://github.com/armory3d/haxerecast).

If no navmesh is detected in the scene, Armory skips including the navmesh module to save space and performance. To force including the module, set `Armory Project - Modules - Navigation` from `Auto` to `Enabled`.

Adding a navmesh is as simple as: selecting an object, going the Object tab, and then in Armory Traits click + to add a new trait, select Bundled, and then in class pick the "Navmesh".

![](https://i.imgur.com/I4xyqWL.png)

To generate a navmesh representation, you can click Generate Navmesh. 

You can modify the settings to affect the navmesh generation for the visualization and the in-game version.

Be aware that if your object is too small, the recast library might not be able to process it for the simulation.

Examples:
- https://github.com/armory3d/armory_examples/tree/master/navmesh
