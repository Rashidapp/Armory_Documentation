# Traits

## Table of Content:
- [Introduction](#introduction)
- [Trait Events](#trait-events)
- [Trait Properties](#trait-properties)
  - [Supported Property Types](#supported-property-types)
  - [Properties Example](#properties-example)
  - [Warnings](#warnings)
- [Folder Organisation](#folder-organisation)

## Introduction
Armory uses a trait(component) system to insert logic into Blender objects and make them interactive. Traits can be attached to scene objects or scenes itself. To inspect traits placed in the scene, switch to `Orphan Data` view in the `Outliner` and see Collections.

![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/traits_groups.png)

There are several trait types:
- `Haxe` - writing script from scratch in Haxe
- `Bundled` - handling common stuff like character controllers, bundled in Armory
- `Nodes` - assembling logic visually
- `UI` - working with canvas & user interface

## Trait Events

Trait exposes events - this makes it possible to get notified about its life-cycle.

- `Trait.notifyOnAdd()` - trait is added to an object
- `Trait.notifyOnInit()` - object which this trait belongs to is added to scene
- `Trait.notifyOnRemove()` - object which this trait belongs to is removed from scene
- `Trait.notifyOnUpdate()` - update game logic here
- `Trait.notifyOnRender()` - update rendering here
- `Trait.notifyOnRender2D()` - update 2D rendering here

As the scene is being built asynchronously, `onInit` event can get called at a time when not all scene objects are present yet. If trait construction depends on other scene objects, use `Scene.active.notifyOnInit()` event which gets called as soon as the scene is fully constructed.

## Trait Properties

For scripts, it is possible to pass parameters or set script properties straight from Blender.

Variables that should be visible in Blender have to be preceded with `@prop` [metadata](https://haxe.org/manual/lf-metadata.html) in a separate line in the source code.

**Please note that only variables declared with the `var` keyword are supported!** Using `final` will not work as the properties are set via [Haxe's Reflection API](https://api.haxe.org/Reflect.html) at the start of the game after trait construction.

### Supported Property Types
The following data types are supported:
- Primitive:
  - `Int`
  - `Float`
  - `Boolean`
- `String`
- Object data types
  - [`iron.object.Object`](https://armory3d.org/api/iron/object/Object.html)
  - [`iron.object.CameraObject`](https://armory3d.org/api/iron/object/CameraObject.html)
  - [`iron.object.LightObject`](https://armory3d.org/api/iron/object/LightObject.html)
  - [`iron.object.MeshObject`](https://armory3d.org/api/iron/object/MeshObject.html)
  - [`iron.object.SpeakerObject`](https://armory3d.org/api/iron/object/SpeakerObject.html)
- Float vectors:
  - [`iron.math.Vec2`](https://armory3d.org/api/iron/math/Vec2.html)
  - [`iron.math.Vec3`](https://armory3d.org/api/iron/math/Vec3.html)
  - [`iron.math.Vec4`](https://armory3d.org/api/iron/math/Vec4.html)

### Properties Example
```haxe
package arm;

// See below ("Object data types")
import iron.object.CameraObject;

import iron.math.Vec2;
import iron.math.Vec3;
import iron.math.Vec4;

class MyTrait extends iron.Trait {
	// Primitive data types
	@prop
	var intValue: Int = 40; // Type annotation possible, but not required
	@prop
	var floatValue = 3.14;
	@prop
	var stringValue = "Hello world!";
	@prop
	var booleanValue = true;

	// Object data types
	@prop
	var objValue: iron.object.Object; // Needs type annotation to be recognized
	@prop
	var camObjValue: CameraObject; // Type can be imported (see above)...
	@prop
	var lightObjValue: iron.object.LightObject; // .. or not, both will work
	@prop
	var meshObjValue: iron.object.MeshObject;
	@prop
	var speakerObjValue: iron.object.SpeakerObject;

	// Vector data types
	@prop
	var vector2DValue: Vec2 = new Vec2(0.2, 0.5); // Initialization possible...
	@prop
	var vector3DValue: Vec3; //... but not required
	@prop
	var vector4DValue = new Vec4(1, 2, 3, 4);

	// Not visible in Blender, `@prop` is missing
	var notVisibleValue = 0.0;

	// ...
}

```

This example results in the following image:

![Trait properties](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/traits_props.png)

### Warnings
If Armory detects invalid `@prop` declarations, warnings will get displayed:

![Trait properties warnings](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/traits_warnings.png)
- Every `@prop` statement must have a following variable declaration
- The property type must be supported (see [Supported property types](#supported-property-types))
- The property must be syntactically correct
- Static properties are allowed but not good style as multiple objects can write to the same static property, resulting in different results depending on the internal initialization order of the traits

## Folder Organisation

By default all traits are created into your project's "Sources/arm" folder when you create them in Blender.

![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/1-Regular_Trait.png)
![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/2-Regular_Trait_Source.png)

In general it's desirable to create a folder structure that matches logically your game division. For example you could decide to split your game in multiple scenes, and ideally keep the code of each Scene in separate subfolders (one per scene) so that it's easy to maintain later on.

In order to create a folder hierarchy tree in armory, you can use the `Haxe package syntax` when assigning a name to your new trait. Therefore if you assign a name such as `general.BoxBehavior`, a new trait will be created under "Sources/arm/general" subfolder, with name "BoxBehavior.hx".

![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/3-Subfolder_Trait.png)
![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/4-Subfolder_Trait_List.png)
![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/5-Subfolder_Trait_Source.png)

You can create infinitely nested subfolders this way by appending more dot-separated names to the trait name, such as "general.terrain.TerrainCollider" which will create a file named "TerrainCollider.hx" under the path "Sources/arm/general/terrain".

If at some point you want to assign a different trait to your object, you simply need to select the trait from the list displayed when you click on the `Class` dropdown, right below the Traits List.

![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/6-Trait_List.png)
![](https://github.com/armory3d/armory_wiki_images/raw/master/essentials/subfolders/7-Subfolder_Trait_Assigned.png)

Note: Please bear in mind that some reserved words won't be allowed to be used as package names, therefore trait names such as "my.new.Trait" won't be valid due to `new` being a reserved word.
