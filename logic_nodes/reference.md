# Reference

## Table of Content
- [Logic](#logic)
- [Event](#event)
- [Activators](#activators)
- [States](#states)
- [Values](#values)
- [Variables](#variables)
- [Actions](#actions)
- [Physics](#physics)
- [Sound](#sound)
- [Canvas](#canvas)

## Logic

### Alternate

Alternates between its activated outputs to pass through its input when it is being re-activated.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Alternate.JPG)


### Array loop

It loops through each item assigned in an array."Value" give item specified by index's value."Done" calls connectors when it is done looping through the array.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array-loop.JPG)


### Branch

When activated, activates its "True" or "False" output, according to the state of the plugged-in boolean.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Branch.JPG)


### Gate

Logic nodes way to do "if" statements. When activated, it compares if its two inputs are being Equal, Greater Equal, Less Equal, or Not Equal, regardless of variable type, and passes through its red input if the set state is the case.

"And" and "Or" are being used for booleans only, and pass through the input when both bools are true \(and\) or at least one \(or\).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Gate.JPG)


### Inverse

Bool will become opposite, True will become False, False will become True.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Inverse.JPG)


### Is True/False

Passes through its activation only if the plugged in boolean is "True"/"False", according to the node.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Is-true_false.JPG)


### Is None

Give bool value of null i.e., If it is null then its output true(Doesn't have value), if it is not null then it outputs false(Have value).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/is-none.JPG)


### Is Not None

Give opposite bool value of null i.e., If it is not null then its output true(Have value), if it is null then it output false(Doesn't have value).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/is-not-none.JPG)


### Loop

It is basically for(i in from...to) loop. "Index" give value specified by the index value."Done" is called when it is done looping.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Loop.JPG)


### Loop Break

Loop Break terminates loop containing it.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/loop-break.JPG)


### Merge

The "New" button creates new inputs, the "X" one deletes the most bottom one. If it receives on activation from any of its inputs, it will activate its output.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Merge.JPG)


### Not

Inverts a plugged in boolean, so if its input is "true" it outputs "false".

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Not.JPG)


### Sequence

Its call output in sequential order.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Sequence.JPG)


### Switch

Check the value on input “in”, When the input value matches Case1, Case 2 or Case 3 value, it will trigger the corresponding output Case 1, Case 2 or Case 3. Click "new" to add more Case Value.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Switch.JPG)


### To Bool

Is false when there is no event on input, true when there is an event on input.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/to-bool.JPG)


### While

Its loop through as long as bool specified in "Condition" is same.(i.e., like  while(jumping == true){do domething}).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/While.JPG)


### Sleep

Activates the node connected with its output after the float value in seconds after it was activated itself.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sleep.JPG)


## Event

### On Event

Activates the node\(s\) being connected to Sent Event or Sent Global Event specified in other node\(s\) tree.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/on-event.JPG)


### On Init

Activates the node\(s\) being connected to it on the first frame of the game.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/On-Init.JPG)


### On Timer

Activates the node\(s\) being connected to after a Timer countdown on from the beginning of the game, repeatedly when box ticked.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/On-Timer.JPG)


### On Update

Activates the node\(s\) being connected to it every frame.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/On-Update.JPG)


### On Volume Trigger

The lower object-input is used as Volume, the upper one as object-input for the object that enters/leaves/overlaps with it.

Enter-mode: Activates the connected nodes on the frame the object enters the volume, on all other frames it doesn't do that.

Leave-mode: Activates the connected nodes on the frame the object leaves the volume, on all other frames it doesn't do that.

Overlap-mode: Activates the connected nodes on the frame the object overlaps with the volume, on all other frames it doesn't do that.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/on-volume-trigger.JPG)


## Activators


### On Mouse

Activates the node\(s\) being connected to it when the set Mouse-button is being started, held down or released, depending on settings.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/On-Mouse.JPG)


### On Keyboard

Activates the node\(s\) being connected to it when the set Keyboard-button is being started, held down or released, depending on settings.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/On-Keyboard.JPG)



## States

### Mouse

Outputs a bool if the set button is being currently started, hold down, released, moved \(true\) or not \(false\).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Mouse.JPG)


### Mouse Cords

Outputs the X, Y location of the mouse of screen and its movement as Vector, and an integer if the scroll wheel es been moved up \(1\) or moved down \(-1\) this frame.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Mouse-Cords.JPG)


### Keyboard

Outputs a bool if the set button is being currently started, hold down, released, \(true\) or not \(false\).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Keyboard.JPG)


### Get Transform

Outputs the current transform of the set object. An objects Transform consists out of Vectors for its global location, rotation, and scale.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-transform.JPG)


### Get Location

Outputs the current global location of the set object as vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-location.JPG)


### Get Rotation

Outputs the current rotation of the set Object as a Vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-rotation.JPG)


### Get Scale

Outputs the current scale of the set object as vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-scale.JPG)


### Get Object

Searches for an object with the set name in the scene and outputs it.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-object.JPG)


### Get Visible

Outputs a Boolean Value according to the objects current visibility setting in the Outliner. False if invisible, True if visible, even if the Object is not on camera right now.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-visible.JPG)


### Get Child

Searches for object with the set name that is currently a child of the set object and outputs it.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-child.JPG)


### Get Children

Outputs all current children of the set object as array of objects.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-children.JPG)


### Get Parent

Outputs the current closest parent of the set object.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-parent.JPG)


### Get Group

Searches for a group of objects with the set name and outputs it as an array of objects.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-group.JPG)


### Group

Outputs all objects in the set group as array.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/group.JPG)


### Get Distance

Outputs the current distance between the two set objects as float.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-distance.JPG)


### Get Trait

Searches for a Trait with the set name which is applied on the set object and outputs it.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-trait.JPG)


### Active Camera

Outputs the current active Camera in your game as object.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/active-camera.JPG)


### Active Scene

Outputs the currently active scene in your game.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/active-scene.JPG)


### Volume Trigger

The lower object-input is used as Volume, the upper one as object-input for the object that enters/leaves/overlaps with it.

Enter-mode: Outputs true on the frame the object enters the volume, on all other frames it outputs false.

Leave-mode: Outputs true on the frame the object leaves the volume, on all other frames it outputs false.

Overlap-mode: Outputs true on the frames the object overlaps with the volume, on all other frames it outputs false.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Volume-trigger.JPG)


## Values

### Get Property

Can be used to receive Properties of other objects, which were set with the "[Set Property](logic-nodes/set-property.md)" node. The properties name and object have to match the inputs of this node.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Get-property.JPG)


## Variables

### Action

TBD

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Action.JPG)


### Boolean

Stores a Boolean value. A Boolean value has just two states: True and False.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/boolean.JPG)


### Colour

Store colour value in RGB/HSV/HEX format.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Colour.JPG)


### Dynamic

TBD

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Dynamic.JPG)


### Float

Stores a Float value. A Float variable is a number with a limited number of decimals. If your number has more than 3 decimals, the value displayed will be rounded, but when you click on it you can still see the whole number, which will also be used in the game.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/float.JPG)


### Global Object

Gives access to an global Object, which can be used to share information between different Traits.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/global-object.JPG)


### Group

Get value stored in a group (Under Object tab) in Array form.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Group.JPG)


### Integer

Stores an integer value. These are whole numbers.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Integer.JPG)


### Material

Get material of any object specified.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Material.JPG)


### Mesh

Get reference of mesh specified.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Mesh.JPG)


### Object

Get reference any object specified.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Object.JPG)


### Quaternion

Store quaternion value.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Quaternion.JPG)


### Scene

Get reference of scene specified.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Scene.JPG)


### Scene Root

TBD

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene-root.JPG)


### String

Store string value.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/String.JPG)


### Trait

Get reference of trait specified. If the trait was not found or was not exported, an error is thrown [(more information)](https://github.com/armory3d/armory/wiki/troubleshooting#trait-not-exported).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Trait.JPG)


### Transform

Store Location, Rotation, Scale value in vector form.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Transform.JPG)


### Vector

Store X, Y, Z value in vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/Vector.JPG)


## Actions

### Set Variable

When activated, updates the first plugged in Variable to the Value of the second. Automatically converts some variable types.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/set-variable.JPG)


### Translate Object

Moves the set object every frame it is activated by the given Vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/translate-object.JPG)

### Set Property

When activated, sets or updates a Property of the given object named after its string input to the Value of its general Variable input \(the green one\). You do not have to worry about the variable type, you can plug everything it apart from activations.

This node can be used to share Variables between different Traits. If the trait\(s\) you want to access the variable with are on different objects, use the "[Global Object](logic-nodes/global-object.md)" node to store the data. Every trait can access this one.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/set-property.JPG)


## Physics

### Apply Force

This apply force to the object assigned, where "Force", is direction force is applied in term of Vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/apply-force.JPG)


### Apply Force at Location

This applies force to the object assigned, where "Force", is direction force is applied in term of Vector, and where "Location", is the location of the object where force is applied from in term of Vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/apply-force-at-location.JPG)


### Apply Impulse

This apply impulse to the object assigned, where "Impulse", is direction force is applied in term of Vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/apply-impulse.JPG)


### Apply Impulse at Location

This applies force to the object assigned, where "Impulse", is direction force is applied in term of Vector, and where "Location", is the location of the object where force is applied from in term of Vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/apply-impulse-at-location.JPG)


### Cast Physics Ray

This cast physics ray from vector assigned to "From", to vector assigned to "To". "Hit" give the location of an object(object assigned to "Object") it hit to in term of vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/cast-physics-ray.JPG)


### Get Contacts

This Get contacts of the object with item in the array.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-contacts.JPG)


### Get First Contact

This Get contact of the object with another object that is assigned with the connector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-first-contact.JPG)


### Get Gravity

This Get gravity of an object in term of vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-gravity.JPG)


### Get Velocity

This Get Linear and Angular velocity of an object in term of vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/get-velocity.JPG)


### Has Contact

This gives bool value of contact between two objects that are assigned,i.e., If both objects contact each other than this gives True, and if not it gives False.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/has-contact.JPG)


### On Contact

Contact between two objects that are assigned to:
1) Overlaps - When this two object completely overlap each other, then the "Out" connector is called.
2) End - When this two objects contact ends, then the "Out" connector is called.
3) Begins - When this two objects first contact, then the "Out" connector is called.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/on-contact.JPG)


### Pick Object

When the object that is assigned to is in "Screen Coords" (Screen coord is coordination of screen in (X, Y) in term of vector. Note: "Z" is not used and should be ignored because we don't have 3D screen.) and then "Hit" is called to do something to it.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/pick-object.JPG)

### Set Gravity

On activated, this set gravity in term of vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/set-gravity.JPG)


### Set Velocity

On activated, this set:
1) The linear velocity of the object that is assigned to.
2) Linear Factor velocity of the object that is assigned to.
3) The angular velocity of the object that is assigned to.
4) Angular Factor velocity of the object that is assigned to.
In term of vector.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/set-velocity.JPG)


## Sound

Note: Different between Pause Speaker and Stop Speaker, is that Pause speaker will just pause the speaker and can be resumed by Play Speaker. While Stop Speaker will completely stop it and cannot be resumed by Play Speaker, on doing so the speaker will play sound/music from start.

### Pause Speaker

On activating this pause speaker(Object that is assigned to as speaker) from playing sound.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/pause_speaker.jpg)


### Play Speaker

On activated this start speaker(Object that is assigned to as speaker) to play sound.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/play_speaker.jpg)


### Play Sound

Plays a sound.

![Screenshot: Play Sound node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/play_sound.jpg)

**Inputs**:
- `Play`: Plays the sound, or if paused, resumes the playback. The exact behaviour depends on the `Retrigger` option (see below)
- `Pause`: Pauses the playing sound. If no sound is playing, nothing happens
- `Stop`: Stops the playing sound. If the playback is paused, this will reset the playback position to the start of the sound

**Outputs**:
- `Out`: activated when `Play` is activated
- `Running`: activated while the playback is active
- `Done`: activated when the playback has finished or was stopped manually

**Options**:
- `Sound`: The sound that will be played
- `Loop`: Whether to loop the playback
- `Retrigger`: If `true`, the playback position will be reset to the beginning on each activation of `Play`. If `false`, the playback will continue at the current position
- **Overrides**:
  - `Sample Rate`: Manually override the sample rate of the sound (this controls the pitch and the playback speed)

**Sources**:
- Python: [sound_play_sound.py](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/sound_play_sound.py)
- Haxe: [PlaySoundRawNode.hx](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PlaySoundRawNode.hx)


### Stop Speaker

On activated this stop speaker(Object that is assigned to as speaker) to stop playing sound.

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/stop_speaker.jpg)


## Canvas

Note: To get the canvas, be sure that the node\(s\) and the canvas(UI) is attached to the same object.

### Canvas Set Text

On activated it changes the text of element(button, label, etc.).

![](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas-set-text.JPG)
