# Find objects in the scene

## Using built-in functions

You can find any object in the active scene by their name:

```haxe
var myObj = iron.Scene.active.getChild("object name");
```

You can also find an existing Group (Collection in Blender) by its name too:

```haxe
var foes = iron.Scene.active.getGroup("foes");
```

---

## by custom search of _direct_ children

If we want to do a manual search in a list of objects with a custom condition, we can do the following:

We can obtain a root to all objects in the with the following line:

```haxe
var sceneParent = iron.Scene.active.sceneParent;
```

then we know that with the .children variable of the [Object Class](https://armory3d.org/manual/api/iron/object/Object.html) we can access an array of the full list of objects that are related to the root:   
```
root
│   Camera
│
└───Player
│   │   Collider
│   │
│   └───Skeleton
│       │   
│       │   Mesh
│       │   ...
│   
└───Props
│   │   Barrel
│   │   Box
│   ...
```
so we obtain an array with all objects in the active scene:
```haxe
var sceneObjs = sceneParent.children;
```
and after that you can loop the array to find any object using custom parameters:
```haxe
// initialize empty array
var array = [];
// loop to find any direct child object that is not visible
for(obj in sceneObjs){
    if(!obj.visible){
        array.push(obj);
    }
}
```
> This will only look for direct children, so if any child has children of their own, they will be ignored.

to make a full search of the "family" we have to do some [recursion](https://en.wikipedia.org/wiki/Recursion_(computer_science)).

## Custom recursive search of all children

We will write a function that will search all objects in a family tree.   

To do so, we will outline the behaviour of this recursive function first:  

> The functions receives an object and an array of objects.

> Determine if the object we passed as a parameter to the function must be added to the array given a custom condition.

> Then we look for the children of this object, and check for each child if they have any children of their own.   

>If they do, we repeat the process from the start for that child to check for their children, and pass the array with the collected objects so far as a parameter too.   

> If they don't have any children, we check if that child can be added to the array before proceeding with the next one. 

> The process repeats until no children to inspect is found, then the array is returned.

With that description let's try to code a generic function that finds all objects that meet certain conditions:

```haxe
function findObjs(obj:Object, group:Array<Object>):Array<Object>{
    if (condition){
        group.push(obj);
    }
    for (ch in obj.children) {
        if (ch.children.length > 0) {
            findObjs(ch,group);
        }
        else if (condition) {
            group.push(ch);
        }	
    }
    return group;
}
```

So we can simply replace condition for any simple or complex condition to get a list of objects in particular, like for example the invisible (render disabled) objects in the scene:

```haxe
function findObjs(obj:Object, group:Array<Object>):Array<Object>{
    if (!obj.visible){
        group.push(obj);
    }
    for (ch in obj.children) {
        if (ch.children.length > 0) {
            findObjs(ch,group);
        }
        else if (!ch.visible) {
            group.push(ch);
        }	
    }
    return group;
}
```

and to call this function:

```haxe
var array = [];
var foundObjs = findObjs(sceneParent,array);
```

Take into consideration that because of the recursive nature of the function the root you pass as the initial parameter may be eligible to be added to the array of objects.

to fix that we can do the following:

We start with the function from before, but this time we want to add some flag that will check if the root can enter the array of objects.

```haxe
function findObjs(obj:Object, group:Array<Object>, ignoreRoot=true):Array<Object>{
    if (condition && !ignoreRoot){
        group.push(obj);
    } 
    for (ch in obj.children) {
        if (ch.children.length > 0) {
            findObjs(ch, group, false);
        }
        else if (condition) {
            group.push(ch);
        }
    }
    return group;
}
```

so ignoreRoot has a chance of being false at the initial case if we set it manually when calling the function:

```haxe
var array = [];
// allow root to be considered
var notVisible = objsNotVisible(sceneParent,array,false);

array = [];
// ignore root
var notVisible = objsNotVisible(sceneParent,array,true);
// or simply
var notVisible = objsNotVisible(sceneParent,array);
```

With that general structure for the function we can write many other functions that could find objects invisible to camera, objects that have a trait in particular, objects whose name have a substring in particular in their name, objects that are in a certain position or rotation, etc.   
Some of those functions are already available in the example found below:

Example:
- link
