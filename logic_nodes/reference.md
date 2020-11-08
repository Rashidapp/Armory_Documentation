# Logic Nodes Reference

*This document was generated automatically. Please do not edit this page directly, instead change the docstrings of the nodes in their [Python files](https://github.com/armory3d/armory/tree/master/blender/arm/logicnode) or the [generator script](https://github.com/armory3d/armory_tools/blob/master/make_node_reference.py) and [open a pull request](https://github.com/armory3d/armory/wiki/contribute#creating-a-pull-request). Thank you for contributing to this reference!*

*This reference was built for **Armory 2020.11**.*

---
## Node Categories

- **Basic**
  - [Logic](#logic)
  - [Event](#event)
  - [Input](#input)
  - [Native](#native)
- **Data**
  - [Camera](#camera)
  - [Material](#material)
  - [Light](#light)
  - [Object](#object)
  - [Scene](#scene)
  - [Trait](#trait)
- **Motion**
  - [Animation](#animation)
  - [Navmesh](#navmesh)
  - [Transform](#transform)
  - [Physics](#physics)
- **Values**
  - [Array](#array)
  - [Math](#math)
  - [Random](#random)
  - [String](#string)
  - [Variable](#variable)
- **Graphics**
  - [Canvas](#canvas)
  - [Postprocess](#postprocess)
  - [Renderpath](#renderpath)
- **Sound**
  - [Sound](#sound)
- **Misc**
  - [Miscellaneous](#miscellaneous)
  - [Layout](#layout)

## Logic

Logic nodes are used to control execution flow using branching, loops, gates etc.

### Alternate Output

Activates the outputs "0" and "1" alternating every time it is active.


![Alternate Output node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNAlternateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_alternate_output.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/AlternateNode.hx)

### Branch

Activates its `true` or `false` output, according to the state of the plugged-in boolean.


![Branch node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNBranchNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_branch.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BranchNode.hx)

### Call Function

Calls the given function that was created by the [Function](#function) node.


![Call Function node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNCallFunctionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_call_function.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CallFunctionNode.hx)

### Function

Creates a reusable function that can be called by the [Call Function](#call-function) node.


![Function node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNFunctionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_function.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/FunctionNode.hx)

### Function Output

Sets the return value for the given function.

**See also:**

- *[`Function`](#function)*


![Function Output node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNFunctionOutputNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_function_output.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/FunctionOutputNode.hx)

### Gate

Logic nodes way to do "if" statements. When activated, it compares if its two inputs are being Equal, Greater Equal, Less Equal, or Not Equal, regardless of variable type, and passes through its active input to the output that matches the result of the comparison. "And" and "Or" are being used for booleans only, and pass through the input when both booleans are true (And) or at least one (Or).


![Gate node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNGateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_gate.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GateNode.hx)

### Invert Boolean

Inverts the plugged-in boolean. If its input is `true` it outputs `false`.


![Invert Boolean node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNNotNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_invert_boolean.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/NotNode.hx)

### Invert Output

Activates the output if the input is not active.


![Invert Output node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNInverseNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_invert_output.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/InverseNode.hx)

### Is False

Passes through its activation only if the plugged-in boolean equals `false`.

**See also:**

- *[`Is True`](#is-true)*


![Is False node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNIsFalseNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_is_false.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/IsFalseNode.hx)

### Is Not Null

Passes through its activation only if the plugged-in value is not `null`.

**See also:**

- *[`Is None`](#is-none)*


![Is Not Null node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNIsNotNoneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_is_not_null.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/IsNotNoneNode.hx)

### Is Null

Passes through its activation only if the plugged-in value is `null` (no value).

**See also:**

- *[`Is Not None`](#is-not-none)*


![Is Null node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNIsNoneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_is_null.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/IsNoneNode.hx)

### Is True

Passes through its activation only if the plugged-in boolean equals `true`.

**See also:**

- *[`Is False`](#is-false)*


![Is True node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNIsTrueNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_is_true.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/IsTrueNode.hx)

### Loop

Resembles a for-loop (`for (i in from...to)`) that is executed at once when this node is activated.

**See also:**

- *[`While`](#while)*
- *[`Loop Break`](#loop-break)*


![Loop node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNLoopNode.jpg)

**Inputs:**

- `From`: The value to start the loop from (inclusive)
- `To`: The value to end the loop at (exclusive)

**Outputs:**

- `Loop`: Active at every iteration of the loop
- `Index`: The index for the current iteration
- `Done`: Activated once when the looping is done

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_loop.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LoopNode.hx)

### Loop Break

Terminates the currently executing loop (only one loop is executed at once).

**See also:**

- *[`Loop`](#loop)*
- *[`While`](#while)*


![Loop Break node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNLoopBreakNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_loop_break.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LoopBreakNode.hx)

### Merge

Activates the output when any connected input is activated.


![Merge node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNMergeNode.jpg)

**Options:**

- `New`: Add a new input socket.
- `X Button`: Remove the lowermost input socket.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_merge.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MergeNode.hx)

### Null

A `null` value that can be used in comparisons and conditions.


![Null node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNNoneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_null.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/NoneNode.hx)

### Sequence

Activates the outputs one by one sequentially and repeatedly.


![Sequence node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNSequenceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_sequence.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SequenceNode.hx)

### Switch Output

Activates the outputs depending of the value. If the "value" is equal to "case 1", the output "case 1" will be activated.


![Switch Output node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNSwitchNode.jpg)

**Outputs:**

- `Default`: Activated if the input value does not match any case.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_switch_output.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SwitchNode.hx)

### To Boolean

Converts a signal to a boolean value. If the input signal is active, the boolean is `true`; if not, the boolean is `false`.


![To Boolean node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNToBoolNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_to_boolean.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ToBoolNode.hx)

### While

Loops while the condition is `true`.

**See also:**

- *[`Loop`](#loop)*
- *[`Loop Break`](#loop-break)*


![While node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/logic/LNWhileNode.jpg)

**Inputs:**

- `Condition`: boolean that resembles the result of the condition

**Outputs:**

- `Loop`: Activated on every iteration step
- `Done`: Activated when the loop is done executing

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/logic/LN_while.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/WhileNode.hx)

## Event

### On Application State

Listens to different application state changes.


![On Application State node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNOnApplicationStateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_on_application_state.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnApplicationStateNode.hx)

### On Event

Activates the output when the given event is received.

**See also:**

- *[`Send Event To Object`](#send-event-to-object)*
- *[`Send Event`](#send-event)*


![On Event node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNOnEventNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_on_event.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnEventNode.hx)

### On Init

Activates the output on the first frame of execution of the logic tree.


![On Init node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNOnInitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_on_init.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnInitNode.hx)

### On Timer

Activates the output when a given time elapsed (optionally repeating the timer).


![On Timer node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNOnTimerNode.jpg)

**Inputs:**

- `Duration`: the time in seconds after which to activate the output
- `Repeat`: whether to repeat the timer

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_on_timer.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnTimerNode.hx)

### On Update

Activates the output on every frame.


![On Update node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNOnUpdateNode.jpg)

**Options:**

- `Update`: (default) activates the output every frame.
- `Late Update`: activates the output after all non-late updates are calculated.
- `Physics Pre-Update`: activates the output before calculating the physics. Only available when using a physics engine.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_on_update.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnUpdateNode.hx)

### Send Event To Object

Sends the given event to the given object.

**See also:**

- *[`Send Event`](#send-event)*
- *[`On Event`](#on-event)*


![Send Event To Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNSendEventNode.jpg)

**Inputs:**

- `Event`: the identifier of the event
- `Object`: the receiving object

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_send_event_to_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SendEventNode.hx)

### Send Global Event

Sends the given event to all objects in the scene.

**See also:**

- *[`Send Event To Object`](#send-event-to-object)*
- *[`On Event`](#on-event)*


![Send Global Event node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/event/LNSendGlobalEventNode.jpg)

**Inputs:**

- `Event`: the identifier of the event

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/event/LN_send_global_event.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SendGlobalEventNode.hx)

## Input

### Gamepad

Activates the output when there is a gamepad event.

**See also:**

- *[`Gamepad Coords`](#gamepad-coords)*


![Gamepad node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNMergedGamepadNode.jpg)

**Inputs:**

- `Gamepad`: the ID of the gamepad.

**Options:**

- `State`: the state of the gamepad button to listen to.
- `Button`: the gamepad button that should activate the output.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_gamepad.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MergedGamepadNode.hx)

### Gamepad Coords

Returns the coordinates of the given gamepad.

**See also:**

- *[`Gamepad`](#gamepad)*


![Gamepad Coords node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGamepadCoordsNode.jpg)

**Inputs:**

- `Gamepad`: the ID of the gamepad.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_gamepad_coords.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GamepadCoordsNode.hx)

### Get Cursor Location

Returns the mouse cursor location in screen coordinates (pixels).


![Get Cursor Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetCursorLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_get_cursor_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetCursorLocationNode.hx)

### Get Cursor State

Returns the state of the mouse cursor.

**See also:**

- *[`Set Cursor State`](#set-cursor-state)*


![Get Cursor State node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetCursorStateNode.jpg)

**Outputs:**

- `Is Hidden Locked`: `true` if the mouse cursor is both hidden and locked.
- `Is Hidden`: `true` if the mouse cursor is hidden.
- `Is Locked`: `true` if the mouse cursor is locked.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_get_cursor_state.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetCursorStateNode.hx)

### Get Mouse Lock (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Get Cursor State`](#get-cursor-state). 

Deprecated. It is recommended to use the 'Get Cursor State' node instead.


![Get Mouse Lock (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetMouseLockNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_get_mouse_lock.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetMouseLockNode.hx)

### Get Mouse Movement

Returns the movement coordinates of the mouse.


![Get Mouse Movement node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetMouseMovementNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_get_mouse_movement.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetMouseMovementNode.hx)

### Get Mouse Visible (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Get Cursor State`](#get-cursor-state). 

Deprecated. It is recommended to use the 'Get Cursor State' node instead.


![Get Mouse Visible (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetMouseVisibleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_get_mouse_visible.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetMouseVisibleNode.hx)

### Get Touch Location

Returns the location of the last touch event in screen coordinates (pixels).


![Get Touch Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetTouchLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_get_touch_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetTouchLocationNode.hx)

### Get Touch Movement

Returns the movement values of the current touch event.


![Get Touch Movement node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNGetTouchMovementNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_get_touch_movement.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetTouchMovementNode.hx)

### Keyboard

Activates the output when the given keyboard action is done.


![Keyboard node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNMergedKeyboardNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_keyboard.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MergedKeyboardNode.hx)

### Mouse

Activates the output when the given mouse action is done.


![Mouse node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNMergedMouseNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_mouse.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MergedMouseNode.hx)

### Mouse Coords (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Get Cursor Location`](#get-cursor-location). 

Deprecated. It is recommended to use 'Get Cursor Location' node and the 'Get Mouse Movement' node instead.


![Mouse Coords (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNMouseCoordsNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_mouse_coords.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MouseCoordsNode.hx)

### On Gamepad (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Gamepad`](#gamepad). 

Deprecated. It is recommended to use the 'Gamepad' node instead.


![On Gamepad (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnGamepadNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_on_gamepad.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnGamepadNode.hx)

### On Keyboard (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Keyboard`](#keyboard). 

Deprecated. It is recommended to use the 'Keyboard' node instead.


![On Keyboard (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnKeyboardNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_on_keyboard.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnKeyboardNode.hx)

### On Mouse (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Mouse`](#mouse). 

Deprecated. It is recommended to use the 'Mouse' node instead.


![On Mouse (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnMouseNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_on_mouse.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnMouseNode.hx)

### On Surface (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Surface`](#surface). 

Deprecated. Is recommended to use the 'Surface' node instead.


![On Surface (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnSurfaceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_on_surface.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnSurfaceNode.hx)

### On Swipe

Activates the output when the given swipe action is done.


![On Swipe node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnSwipeNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_on_swipe.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnSwipeNode.hx)

### On Tap Screen

Activates the output when the given tap action is done.


![On Tap Screen node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnTapScreen.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_on_tap_screen.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnTapScreen.hx)

### On Virtual Button (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Virtual Button`](#virtual-button). 

Deprecated. Is recommended to use 'Virtual Button' node instead.


![On Virtual Button (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNOnVirtualButtonNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_on_virtual_button.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnVirtualButtonNode.hx)

### Sensor Coords

TO DO.


![Sensor Coords node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNSensorCoordsNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_sensor_coords.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SensorCoordsNode.hx)

### Set Cursor State

Sets the state of the mouse cursor.

**See also:**

- *[`Get Cursor State`](#get-cursor-state)*


![Set Cursor State node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNSetCursorStateNode.jpg)

**Options:**

- `Hide Locked`: hide and lock or unhide and unlock the mouse cursor.

**Outputs:**

- `Hide`: hide/unhide the mouse cursor.
- `Lock`: lock/unlock the mouse cursor.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_set_cursor_state.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetCursorStateNode.hx)

### Set Mouse Lock (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Cursor State`](#set-cursor-state). 

Deprecated. It is recommended to use the 'Set Cursor State' node instead.


![Set Mouse Lock (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNSetMouseLockNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_set_mouse_lock.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMouseLockNode.hx)

### Set Mouse Visible (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Cursor State`](#set-cursor-state). 

Deprecated. It is recommended to use the 'Set Cursor State' node instead.


![Set Mouse Visible (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNShowMouseNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_set_mouse_visible.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ShowMouseNode.hx)

### Surface

Activates the output when the given action over the screen is done.


![Surface node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNMergedSurfaceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_surface.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MergedSurfaceNode.hx)

### Surface Coords (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Get Touch Movement`](#get-touch-movement), [`Get Touch Location`](#get-touch-location). 

Deprecated. Is recommended to use 'Get Touch Location' and 'Get Touch Movement' node instead.


![Surface Coords (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNSurfaceCoordsNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_surface_coords.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SurfaceCoordsNode.hx)

### Virtual Button

Activates the output when the given action over the virtual button is done.


![Virtual Button node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/input/LNMergedVirtualButtonNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/input/LN_virtual_button.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MergedVirtualButtonNode.hx)

## Native

The Native category contains nodes which interact with the system (Input/Output functionality, etc.) or Haxe.

### Call Haxe Static

Calls the given static Haxe function.


![Call Haxe Static node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNCallHaxeStaticNode.jpg)

**Inputs:**

- `Function`: the full module path to the function.

**Outputs:**

- `Result`: the result of the function.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_call_haxe_static.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CallHaxeStaticNode.hx)

### Detect Mobile Browser

Determines the mobile browser or not (works only for web browsers).


![Detect Mobile Browser node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNDetectMobileBrowserNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_detect_mobile_browser.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/DetectMobileBrowserNode.hx)

### Expression

Evaluates a Haxe expression and returns its output.


![Expression node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNExpressionNode.jpg)

**Outputs:**

- `Result`: the result of the expression.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_expression.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ExpressionNode.hx)

### Get Haxe Property

Returns a property of an Haxe object (via the Reflection API).

**See also:**

- *[`Set Haxe Property`](#set-haxe-property)*


![Get Haxe Property node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNGetHaxePropertyNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_get_haxe_property.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetHaxePropertyNode.hx)

### Get System Language

Returns the language of the current system.


![Get System Language node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNGetSystemLanguage.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_get_system_language.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetSystemLanguage.hx)

### Get System Name

Returns the name of the current system.


![Get System Name node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNGetSystemName.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_get_system_name.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetSystemName.hx)

### Load URL

Load the given URL in a new tab (works only for web browsers).


![Load URL node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNLoadUrlNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_loadUrl.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LoadUrlNode.hx)

### Print

Print the given value to the console.


![Print node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNPrintNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_print.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PrintNode.hx)

### Read File

Returns the content of the given file.

**See also:**

- *[`Write File`](#write-file)*


![Read File node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNReadFileNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_read_file.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ReadFileNode.hx)

### Read JSON

Returns the content of the given JSON file.

**See also:**

- *[`Write JSON`](#write-json)*


![Read JSON node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNReadJsonNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_read_json.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ReadJsonNode.hx)

### Read Storage

Reads a stored content.

**See also:**

- *[`Write Storage`](#write-storage)*


![Read Storage node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNReadStorageNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_read_storage.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ReadStorageNode.hx)

### Script

Executes the given script.


![Script node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNScriptNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_script.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ScriptNode.hx)

### Set Haxe Property

Sets a property of an Haxe object (via the Reflection API).

**See also:**

- *[`Get Haxe Property`](#get-haxe-property)*


![Set Haxe Property node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNSetHaxePropertyNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_set_haxe_property.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetHaxePropertyNode.hx)

### Set Vibrate

Pulses the vibration hardware on the device for time in milliseconds, if such hardware exists.


![Set Vibrate node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNSetVibrateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_set_vibrate.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetVibrateNode.hx)

### Shutdown

Closes the application.


![Shutdown node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNShutdownNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_shutdown.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ShutdownNode.hx)

### Write File

Writes the given content in the given file.

**See also:**

- *[`Read File`](#read-file)*


![Write File node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNWriteFileNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_write_file.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/WriteFileNode.hx)

### Write JSON

Writes the given content in the given JSON file.

**See also:**

- *[`Read JSON`](#read-json)*


![Write JSON node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNWriteJsonNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_write_json.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/WriteJsonNode.hx)

### Write Storage

Writes the given content in the given key.

**See also:**

- *[`Read Storage`](#read-storage)*


![Write Storage node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/native/LNWriteStorageNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/native/LN_write_storage.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/WriteStorageNode.hx)

## Camera

### Get Camera Active

Returns the active camera.

**See also:**

- *[`Set Active Camera`](#set-active-camera)*


![Get Camera Active node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/camera/LNActiveCameraNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/camera/LN_get_camera_active.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ActiveCameraNode.hx)

### Get Camera FOV

Returns the field of view (FOV) of the given camera.

**See also:**

- *[`Set Camera FOV`](#set-camera-fov)*


![Get Camera FOV node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/camera/LNGetCameraFovNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/camera/LN_get_camera_fov.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetCameraFovNode.hx)

### Set Camera Active

Sets the active camera.

**See also:**

- *[`Get Active Camera`](#get-active-camera)*


![Set Camera Active node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/camera/LNSetCameraNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/camera/LN_set_camera_active.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetCameraNode.hx)

### Set Camera FOV

Sets the field of view (FOV) of the given camera.

**See also:**

- *[`Get Camera FOV`](#get-camera-fov)*


![Set Camera FOV node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/camera/LNSetCameraFovNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/camera/LN_set_camera_fov.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetCameraFovNode.hx)

## Material

### Get Object Material

Returns the material of the given object.


![Get Object Material node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNGetMaterialNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/material/LN_get_object_material.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetMaterialNode.hx)

### Material

Stores the given material as a variable.


![Material node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNMaterialNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/material/LN_material.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MaterialNode.hx)

### Set Material Image Param

TO DO.


![Set Material Image Param node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNSetMaterialImageParamNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/material/LN_set_material_image_param.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMaterialImageParamNode.hx)

### Set Material RGB Param

TO DO.


![Set Material RGB Param node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNSetMaterialRgbParamNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/material/LN_set_material_rgb_param.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMaterialRgbParamNode.hx)

### Set Material Value Param

TO DO.


![Set Material Value Param node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNSetMaterialValueParamNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/material/LN_set_material_value_param.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMaterialValueParamNode.hx)

### Set Object Material (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Object Material Slot`](#set-object-material-slot). 

Sets the material of the given object.


![Set Object Material (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNSetMaterialNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_set_object_material.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMaterialNode.hx)

### Set Object Material Slot

TO DO.


![Set Object Material Slot node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/material/LNSetMaterialSlotNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/material/LN_set_object_material_slot.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMaterialSlotNode.hx)

## Light

### Set Light Color

Sets the color of the given light.


![Set Light Color node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/light/LNSetLightColorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/light/LN_set_light_color.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetLightColorNode.hx)

### Set Light Strength

Sets the strenght of the given light.


![Set Light Strength node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/light/LNSetLightStrengthNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/light/LN_set_light_strength.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetLightStrengthNode.hx)

## Object

### Get Distance

Returns the euclidian distance between the two given objects.

**See also:**

- *For distance between two locations, use the `Distance` operator
        in the *[`Vector Math`](#vector-math)* node.*


![Get Distance node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetDistanceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_distance.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetDistanceNode.hx)

### Get Object By Name

Searches for a object that uses the given name and returns it.


![Get Object By Name node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_by_name.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetObjectNode.hx)

### Get Object Child

Returns the child of the given object by the child object's name.


![Get Object Child node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetChildNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_child.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetChildNode.hx)

### Get Object Children

Returns the children of the given object.


![Get Object Children node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetChildrenNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_children.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetChildrenNode.hx)

### Get Object Mesh

Returns the mesh of the given object.


![Get Object Mesh node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetMeshNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_mesh.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetMeshNode.hx)

### Get Object Name

Returns the name of the given object.


![Get Object Name node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetNameNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_name.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetNameNode.hx)

### Get Object Offscreen

Returns if the given object is offscreen. Don't works if culling is disabled.


![Get Object Offscreen node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetObjectOffscreenNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_offscreen.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetObjectOffscreenNode.hx)

### Get Object Parent

Returns the direct parent (nearest in the hierarchy) of the given object.

**See also:**

- *[`Set Object Parent`](#set-object-parent)*


![Get Object Parent node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetParentNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_parent.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetParentNode.hx)

### Get Object Property

Returns the value of the given object property.

**See also:**

- *[`Set Object Property`](#set-object-property)*


![Get Object Property node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetPropertyNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_property.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetPropertyNode.hx)

### Get Object Visible

Returns whether the given object or its visual components are visible.

**See also:**

- *[`Set Object Visible`](#set-object-visible)*


![Get Object Visible node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNGetVisibleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_get_object_visible.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetVisibleNode.hx)

### Mesh

Stores the given mesh as a variable.


![Mesh node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNMeshNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_mesh.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MeshNode.hx)

### Object

Stores the given object as a variable.


![Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ObjectNode.hx)

### Remove Object

Removes the given object from the scene.


![Remove Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNRemoveObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_remove_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RemoveObjectNode.hx)

### Remove Object Parent

Removes the parent of the given object.


![Remove Object Parent node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNClearParentNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_remove_object_parent.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ClearParentNode.hx)

### Self Object

Returns the object that owns the trait.


![Self Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSelfNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_self_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SelfNode.hx)

### Set Object Mesh

Sets the mesh of the given object.


![Set Object Mesh node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSetMeshNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_set_object_mesh.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetMeshNode.hx)

### Set Object Name

Sets the name of the given object.


![Set Object Name node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSetNameNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_set_object_name.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetNameNode.hx)

### Set Object Parent

Sets the direct parent (nearest in the hierarchy) of the given object.

**See also:**

- *[`Get Object Parent`](#get-object-parent)*


![Set Object Parent node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSetParentNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_set_object_parent.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetParentNode.hx)

### Set Object Property

Sets the value of the given object property. This node can be used to share variables between different traits. If the trait(s) you want to access the variable with are on different objects, use the *[`Global Object`](#global-object)* node to store the data. Every trait can access this one.

**See also:**

- *[`Get Object Property`](#get-object-property)*


![Set Object Property node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSetPropertyNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_set_object_property.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetPropertyNode.hx)

### Set Object Visible

Sets whether the given object is visible.

**See also:**

- *[`Get Object Visible`](#get-object-visible)*


![Set Object Visible node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSetVisibleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_set_object_visible.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetVisibleNode.hx)

### Spawn Object

Spawns the given object. The spawned object has the same name of its instance, but they are threated as different objects.


![Spawn Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/object/LNSpawnObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/object/LN_spawn_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SpawnObjectNode.hx)

## Scene

### Collection

Returns the objects of the given collection as an array.

**See also:**

- *[`Get Collection`](#get-collection)*


![Collection node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNGroupNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_collection.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GroupNode.hx)

### Create Collection

Creates a collection.


![Create Collection node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNAddGroupNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_create_collection.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/AddGroupNode.hx)

### Get Collection

Searches for a collection of objects with the given name and outputs the collection's objects as an array, if found.

**See also:**

- *[`Collection`](#collection)*


![Get Collection node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNGetGroupNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_get_collection.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetGroupNode.hx)

### Get Scene Active

Returns the active scene.


![Get Scene Active node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNActiveSceneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_get_scene_active.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ActiveSceneNode.hx)

### Get Scene Root

Returns the root object of the current scene.


![Get Scene Root node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNSceneRootNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_get_scene_root.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SceneRootNode.hx)

### Global Object

Gives access to a global object which can be used to share information between different traits.


![Global Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNGlobalObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_global_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GlobalObjectNode.hx)

### Remove Collection

Removes the given collection from the scene.


![Remove Collection node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNRemoveGroupNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_remove_collection.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RemoveGroupNode.hx)

### Remove Scene Active

Removes the active scene.


![Remove Scene Active node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNRemoveActiveSceneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_remove_scene_active.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RemoveActiveSceneNode.hx)

### Scene

Stores the given scene as a variable.


![Scene node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNSceneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_scene.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SceneNode.hx)

### Set Scene Active

Sets the active scene.


![Set Scene Active node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNSetSceneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_set_scene_active.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetSceneNode.hx)

### Spawn Collection

Spawns a new instance of the selected collection. Each spawned instance has an empty owner object to control the instance as a whole (like Blender uses it for collection instances).


![Spawn Collection node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNSpawnCollectionNode.jpg)

**Inputs:**

- `In`: activates the node.
- `Transform`: the transformation of the instance that should be spawned. Please note that the collection's instance offset is also taken into account.

**Outputs:**

- `Out`: activated when a collection instance was spawned. It is not activated when no collection is selected.
- `Top-Level Objects`: all objects in the last spawned collection that are direct children of the owner object of the collection's instance.
- `All Objects`: all objects in the last spawned collection.
- `Owner Object`: The owning object of the last spawned collection's instance.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_spawn_collection.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SpawnCollectionNode.hx)

### Spawn Scene

Spawns the given scene.


![Spawn Scene node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/scene/LNSpawnSceneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/scene/LN_spawn_scene.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SpawnSceneNode.hx)

## Trait

### Add Trait To Object

Adds trait to the given object.


![Add Trait To Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNAddTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_add_trait_to_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/AddTraitNode.hx)

### Get Object Trait

Searches for a trait with the specified name which is applied to the given object and returns that trait.


![Get Object Trait node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNGetTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_get_object_trait.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetTraitNode.hx)

### Get Object Traits

Returns all traits from the given object.


![Get Object Traits node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNGetObjectTraitsNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_get_object_traits.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetObjectTraitsNode.hx)

### Get Trait Name

Returns the name and the class type of the given trait.


![Get Trait Name node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNGetTraitNameNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_get_trait_name.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetTraitNameNode.hx)

### Pause Trait (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Trait Paused`](#set-trait-paused). 

Pauses the given trait.


![Pause Trait (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNPauseTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_pause_trait.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PauseTraitNode.hx)

### Remove Trait

Removes the given trait.


![Remove Trait node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNRemoveTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_remove_trait.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RemoveTraitNode.hx)

### Resume Trait (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Trait Paused`](#set-trait-paused). 

Resumes the given trait.


![Resume Trait (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNResumeTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_resume_trait.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ResumeTraitNode.hx)

### Self Trait

Returns the trait that owns this node.


![Self Trait node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNSelfTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_self_trait.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SelfTraitNode.hx)

### Set Trait Paused

Sets the paused state of the given trait.


![Set Trait Paused node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNSetTraitPausedNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_set_trait_paused.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetTraitPausedNode.hx)

### Trait

Stores the given trait as a variable. If the trait was not found or was not exported, an error is thrown ([more information](https://github.com/armory3d/armory/wiki/troubleshooting#trait-not-exported)).


![Trait node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/trait/LNTraitNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/trait/LN_trait.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TraitNode.hx)

## Animation

### Action

Stores the given action as a variable.


![Action node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNAnimActionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_action.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/AnimActionNode.hx)

### Blend Action

Interpolates between the two given actions.


![Blend Action node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNBlendActionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_blend_action.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BlendActionNode.hx)

### Bone FK

Applies forward kinematics in the given object bone.


![Bone FK node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNBoneFKNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_bone_fk.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BoneFKNode.hx)

### Bone IK

Applies inverse kinematics in the given object bone.


![Bone IK node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNBoneIKNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_bone_ik.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BoneIKNode.hx)

### Get Action State

Returns the information about the current action of the given object.


![Get Action State node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNAnimationStateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_get_action_state.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/AnimationStateNode.hx)

### Get Tilesheet State

Returns the information about the current tilesheet of the given object.


![Get Tilesheet State node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNGetTilesheetStateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_get_tilesheet_state.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetTilesheetStateNode.hx)

### On Action Marker

Activates the output when the object action reaches the action marker.


![On Action Marker node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNOnActionMarkerNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_on_action_marker.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnActionMarkerNode.hx)

### Pause Action (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Action Paused`](#set-action-paused). 

Pauses the given action.


![Pause Action (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNPauseActionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_pause_action.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PauseActionNode.hx)

### Pause Tilesheet (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Tilesheet Paused`](#set-tilesheet-paused). 

Pauses the given tilesheet action.


![Pause Tilesheet (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNPauseTilesheetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_pause_tilesheet.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PauseTilesheetNode.hx)

### Play Action (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Play Action From`](#play-action-from). 

Plays the given action.


![Play Action (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNPlayActionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_play_action.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PlayActionNode.hx)

### Play Action From

Plays action starting from the given frame.


![Play Action From node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNPlayActionFromNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_play_action_from.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PlayActionFromNode.hx)

### Play Tilesheet

Plays the given tilesheet action.


![Play Tilesheet node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNPlayTilesheetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_play_tilesheet.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PlayTilesheetNode.hx)

### Resume Action (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Action Paused`](#set-action-paused). 

Resumes the given action.


![Resume Action (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNResumeActionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_resume_action.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ResumeActionNode.hx)

### Resume Tilesheet (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Tilesheet Paused`](#set-tilesheet-paused). 

Resumes the given tilesheet action.


![Resume Tilesheet (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNResumeTilesheetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_resume_tilesheet.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ResumeTilesheetNode.hx)

### Set Action Paused

Sets the action paused state of the given object.


![Set Action Paused node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNSetActionPausedNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_set_action_paused.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetActionPausedNode.hx)

### Set Action Speed

Sets the current action playback speed of the given object.


![Set Action Speed node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNSetActionSpeedNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_set_action_speed.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetActionSpeedNode.hx)

### Set Parent Bone

Sets the given object parent to the given bone.


![Set Parent Bone node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNSetParentBoneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_set_parent_bone.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetParentBoneNode.hx)

### Set Particle Speed

Sets the speed of the given particle source.


![Set Particle Speed node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNSetParticleSpeedNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_set_particle_speed.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetParticleSpeedNode.hx)

### Set Tilesheet Paused

Sets the tilesheet paused state of the given object.


![Set Tilesheet Paused node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/animation/LNSetTilesheetPausedNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/animation/LN_set_tilesheet_paused.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetTilesheetPausedNode.hx)

## Navmesh

### Go To Location

Makes a NavMesh agent go to location.


![Go To Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/navmesh/LNGoToLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/navmesh/LN_go_to_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GoToLocationNode.hx)

### Navigable Location

TO DO.


![Navigable Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/navmesh/LNNavigableLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/navmesh/LN_navigable_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/NavigableLocationNode.hx)

### Pick NavMesh Location

Pick a location coordinates in the given NavMesh.


![Pick NavMesh Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/navmesh/LNPickLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/navmesh/LN_pick_navmesh_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PickLocationNode.hx)

### Stop Agent

Stops the given NavMesh agent.


![Stop Agent node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/navmesh/LNStopAgentNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/navmesh/LN_stop_agent.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/StopAgentNode.hx)

## Transform

### Append Transform

Appends transform to the given object.


![Append Transform node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNAppendTransformNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_append_transform.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/AppendTransformNode.hx)

### Get Object Location

Returns the current location of the given object in world coordinates.


![Get Object Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNGetLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_get_object_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetLocationNode.hx)

### Get Object Rotation

Returns the current rotation of the given object.


![Get Object Rotation node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNGetRotationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_get_object_rotation.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetRotationNode.hx)

### Get Object Scale

Returns the scale of the given object.


![Get Object Scale node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNGetScaleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_get_object_scale.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetScaleNode.hx)

### Get Object Transform

Returns the transformation of the given object. An object's transform consists of vectors describing its global location, rotation and scale.


![Get Object Transform node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNGetTransformNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_get_object_transform.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetTransformNode.hx)

### Get World Orientation

Returns the world orientation of the given object.


![Get World Orientation node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNGetWorldNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_get_world_orientation.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetWorldNode.hx)

### Look At

TO DO.


![Look At node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNLookAtNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_look_at.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LookAtNode.hx)

### Quaternion

TO DO.


![Quaternion node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNQuaternionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_quaternion.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/QuaternionNode.hx)

### Rotate Object

Rotates the given object.


![Rotate Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNRotateObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_rotate_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RotateObjectNode.hx)

### Rotate Object Around Axis (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Rotate Object`](#rotate-object). 

Deprecated. It is recommended to use the 'Rotate Object' node instead.


![Rotate Object Around Axis (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNRotateObjectAroundAxisNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_rotate_object_around_axis.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RotateObjectAroundAxisNode.hx)

### Scale Object (Deprecated)

> **DEPRECATED.** This node is deprecated and will be removed in future versions of Armory. Please use the following node(s) instead: [`Set Object Scale`](#set-object-scale). 

Deprecated. 'Use Set Object Scale' instead.


![Scale Object (Deprecated) node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNScaleObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/deprecated/LN_scale_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ScaleObjectNode.hx)

### Separate Quaternion

TO DO.


![Separate Quaternion node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNSeparateQuaternionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_separate_quaternion.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SeparateQuaternionNode.hx)

### Separate Transform

Separates the transform of the given object.


![Separate Transform node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNSeparateTransformNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_separate_transform.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SeparateTransformNode.hx)

### Set Object Location

Sets the location of the given object.


![Set Object Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNSetLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_set_object_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetLocationNode.hx)

### Set Object Rotation

Sets the rotation of the given object.


![Set Object Rotation node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNSetRotationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_set_object_rotation.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetRotationNode.hx)

### Set Object Scale

Sets the scale of the given object.


![Set Object Scale node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNSetScaleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_set_object_scale.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetScaleNode.hx)

### Set Object Transform

Sets the transform of the given object.


![Set Object Transform node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNSetTransformNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_set_object_transform.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetTransformNode.hx)

### Transform

Stores the location, rotation and scale values as a transform.


![Transform node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNTransformNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_transform.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TransformNode.hx)

### Transform Math

Operates the two given transform values.


![Transform Math node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNTransformMathNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_transform_math.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TransformMathNode.hx)

### Translate Object

Translates (moves) the given object using the given vector in world coordinates.


![Translate Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNTranslateObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_translate_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TranslateObjectNode.hx)

### Translate On Local Axis

Translates (moves) the given object using the given vector in the local coordinates.


![Translate On Local Axis node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNTranslateOnLocalAxisNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_translate_on_local_axis.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TranslateOnLocalAxisNode.hx)

### Vector From Transform

Returns vector from the given transform.


![Vector From Transform node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNVectorFromTransformNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_vector_from_transform.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorFromTransformNode.hx)

### Vector To Object Orientation

Converts a world oriented vector to a given object oriented vector. Works similarly to 'On Local Axis' checkboxes.

**See also:**

- *[`Get World Orientation`](#get-world-orientation)*
- *[`Vector From Transform`](#vector-from-transform)*


![Vector To Object Orientation node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/transform/LNVectorToObjectOrientationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/transform/LN_vector_to_object_orientation.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorToObjectOrientationNode.hx)

## Physics

### Apply Force

Applies force in the given rigid body.

**See also:**

- *[`Apply Force At Location`](#apply-force-at-location)*
- *[`Apply Impulse`](#apply-impulse)*
- *[`Apply Impulse At Location`](#apply-impulse-at-location)*


![Apply Force node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNApplyForceNode.jpg)

**Inputs:**

- `Force`: the force vector
- `On Local Axis`: if `true`, interpret the force vector as in object space

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_apply_force.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ApplyForceNode.hx)

### Apply Force At Location

Applies force in the given rigid body at the given position.

**See also:**

- *[`Apply Force`](#apply-force)*
- *[`Apply Impulse`](#apply-impulse)*
- *[`Apply Impulse At Location`](#apply-impulse-at-location)*


![Apply Force At Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNApplyForceAtLocationNode.jpg)

**Inputs:**

- `Force`: the force vector
- `Force On Local Axis`: if `true`, interpret the force vector as in object space
- `Location`: the location where to apply the force
- `Location On Local Axis`: if `true`, use the location relative to the objects location, otherwise use world coordinates

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_apply_force_at_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ApplyForceAtLocationNode.hx)

### Apply Impulse

Applies impulse in the given rigid body.

**See also:**

- *[`Apply Impulse At Location`](#apply-impulse-at-location)*
- *[`Apply Force`](#apply-force)*
- *[`Apply Force At Location`](#apply-force-at-location)*


![Apply Impulse node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNApplyImpulseNode.jpg)

**Inputs:**

- `Impulse`: the impulse vector
- `On Local Axis`: if `true`, interpret the impulse vector as in object space

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_apply_impulse.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ApplyImpulseNode.hx)

### Apply Impulse At Location

Applies impulse in the given rigid body at the given position.

**See also:**

- *[`Apply Impulse`](#apply-impulse)*
- *[`Apply Force`](#apply-force)*
- *[`Apply Force At Location`](#apply-force-at-location)*


![Apply Impulse At Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNApplyImpulseAtLocationNode.jpg)

**Inputs:**

- `Impulse`: the impulse vector
- `Impulse On Local Axis`: if `true`, interpret the impulse vector as in object space
- `Location`: the location where to apply the impulse
- `Location On Local Axis`: if `true`, use the location relative to the objects location, otherwise use world coordinates

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_apply_impulse_at_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ApplyImpulseAtLocationNode.hx)

### Apply Torque

Applies torque to the given rigid body.


![Apply Torque node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNApplyTorqueNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_apply_torque.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ApplyTorqueNode.hx)

### Apply Torque Impulse

Applies torque impulse in the given rigid body.


![Apply Torque Impulse node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNApplyTorqueImpulseNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_apply_torque_impulse.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ApplyTorqueImpulseNode.hx)

### Get RB Contacts

Returns an array with all objects that are colliding with the given object.

**See also:**

- *[`Get First Contact`](#get-first-contact)*


![Get RB Contacts node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNGetContactsNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_get_rb_contacts.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetContactsNode.hx)

### Get RB Data

Returns the data of the given rigid body.


![Get RB Data node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNGetRigidBodyDataNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_get_rb_data.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetRigidBodyDataNode.hx)

### Get RB First Contact

Returns the first object that is colliding with the given object.

**See also:**

- *[`Get Contacts`](#get-contacts)*


![Get RB First Contact node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNGetFirstContactNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_get_rb_first_contact.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetFirstContactNode.hx)

### Get RB Velocity

Returns the world velocity of the given rigid body.


![Get RB Velocity node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNGetVelocityNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_get_rb_velocity.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetVelocityNode.hx)

### Get World Gravity

Returns the world gravity.

**See also:**

- *[`Set Gravity`](#set-gravity)*


![Get World Gravity node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNGetGravityNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_get_world_gravity.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetGravityNode.hx)

### Has Contact

Returns whether the given rigid body has contact with another given rigid body.


![Has Contact node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNHasContactNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_has_contact.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/HasContactNode.hx)

### Has Contact Array

Returns whether the given rigid body has contact with other given rigid bodies.


![Has Contact Array node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNHasContactArrayNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_has_contact_array.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/HasContactArrayNode.hx)

### On Contact

Activates the output when the rigid body make contact with another rigid body.


![On Contact node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNOnContactNode.jpg)

**Options:**

- `Begin`: the output is activated on the first frame when the two objects have contact
- `End`: the output is activated on the frame after the last frame when the two objects had contact
- `Overlap`: the output is activated on each frame the object have contact

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_on_contact.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnContactNode.hx)

### On Contact Array

Activates the output when the given rigid body make contact with other given rigid bodies.


![On Contact Array node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNOnContactArrayNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_on_contact_array.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnContactArrayNode.hx)

### On Volume Trigger

Activates the output when the given rigid body enter, overlap or leave the given trigger.


![On Volume Trigger node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNOnVolumeTriggerNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_on_volume_trigger.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnVolumeTriggerNode.hx)

### Pick RB

Pickes the rigid body in the given location using the screen coordinates (2D).


![Pick RB node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNPickObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_pick_rb.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PickObjectNode.hx)

### Ray Cast

Casts a physics ray and returns the first object that is hit by this ray.

**See also:**

- *[`Mask`](#mask)*


![Ray Cast node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNCastPhysicsRayNode.jpg)

**Inputs:**

- `From`: the location from where to start the ray, in world coordinates
- `To`: the target location of the ray, in world coordinates
- `Collision Group Mask`: A bit mask value to specify which objects are considered

**Outputs:**

- `Rigid Body`: the object that was hit
- `Hit`: the hit position in world coordinates
- `Normal`: the surface normal of the hit position relative to the world

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_ray_cast.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CastPhysicsRayNode.hx)

### Remove RB

Removes the rigid body from the given object.


![Remove RB node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNRemovePhysicsNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_remove_rb.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RemovePhysicsNode.hx)

### Set RB Activation State

Sets the activation state of the given rigid body.


![Set RB Activation State node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNSetActivationStateNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_set_rb_activation_state.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetActivationStateNode.hx)

### Set RB Friction

Sets the friction of the given rigid body.


![Set RB Friction node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNSetFrictionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_set_rb_friction.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetFrictionNode.hx)

### Set RB Gravity Enabled

Sets whether the gravity is enabled for the given rigid body.


![Set RB Gravity Enabled node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNSetGravityEnabledNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_set_rb_gravity_enabled.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetGravityEnabledNode.hx)

### Set RB Velocity

Sets the velocity of the given rigid body.


![Set RB Velocity node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNSetVelocityNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_set_rb_velocity.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetVelocityNode.hx)

### Set World Gravity

Sets the world gravity.

**See also:**

- *[`Get World Gravity`](#get-world-gravity)*


![Set World Gravity node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNSetGravityNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_set_world_gravity.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetGravityNode.hx)

### Volume Trigger

Returns `true` if the given rigid body enters, overlaps or leaves the given volume trigger.


![Volume Trigger node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/physics/LNVolumeTriggerNode.jpg)

**Inputs:**

- `Object`: this object is taken as the entering object
- `Volume`: this object is used as the volume

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/physics/LN_volume_trigger.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VolumeTriggerNode.hx)

## Array

### Array Add

Adds the given value to the given array.


![Array Add node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayAddNode.jpg)

**Inputs:**

- `Array`: the array to manipulate.
- `Modify Original`: if `false`, the input array is copied before adding the value.
- `Unique Values`: if `true`, values may occur only once in that array (only primitive data types are supported).

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_add.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayAddNode.hx)

### Array Boolean

Stores an array of boolean elements as a variable.


![Array Boolean node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayBooleanNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_boolean.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayBooleanNode.hx)

### Array Color

Stores an array of color elements as a variable.


![Array Color node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayColorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_color.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayColorNode.hx)

### Array Contains

Returns whether the given array contains the given value.


![Array Contains node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayInArrayNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_contains.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayInArrayNode.hx)

### Array Dynamic

Stores the given array as a variable.


![Array Dynamic node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayNode.hx)

### Array Float

Stores an array of float elements as a variable.


![Array Float node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayFloatNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_float.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayFloatNode.hx)

### Array Get

Returns the value of the given array at the given index.


![Array Get node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_get.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayGetNode.hx)

### Array Integer

Stores an array of integer elements as a variable.


![Array Integer node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayIntegerNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_integer.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayIntegerNode.hx)

### Array Length

Returns the length of the given array.


![Array Length node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayLengthNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_length.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayLengthNode.hx)

### Array Loop

Loops through each item of the given array.


![Array Loop node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayLoopNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_loop_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayLoopNode.hx)

### Array Object

Stores an array of object elements as a variable.


![Array Object node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayObjectNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_object.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayObjectNode.hx)

### Array Pop

Removes the last element of the given array.

**See also:**

- *[Haxe API](https://api.haxe.org/Array.html#pop)*


![Array Pop node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayPopNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_pop.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayPopNode.hx)

### Array Remove By Index

Removes the element from the given array by its index.

**See also:**

- *[`Array Remove By Value`](#array-remove-by-value)*


![Array Remove By Index node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayRemoveNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_remove_index.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayRemoveNode.hx)

### Array Remove By Value

Removes the element from the given array by its value.

**See also:**

- *[`Array Remove By Index`](#array-remove-by-index)*


![Array Remove By Value node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayRemoveValueNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_remove_value.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayRemoveValueNode.hx)

### Array Set

Sets the value of the given array at the given index.


![Array Set node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArraySetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_set.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArraySetNode.hx)

### Array Shift

Removes the first element of the given array.

**See also:**

- *[Haxe API](https://api.haxe.org/Array.html#shift)*


![Array Shift node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayShiftNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_shift.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayShiftNode.hx)

### Array Slice

Creates a shallow copy of the given array in the specified range.

**See also:**

- *[Haxe API](https://api.haxe.org/Array.html#slice)*


![Array Slice node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArraySliceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_slice.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArraySliceNode.hx)

### Array Splice

Removes the given amount of elements from the given array.

**See also:**

- *[Haxe API](https://api.haxe.org/Array.html#splice)*


![Array Splice node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArraySpliceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_splice.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArraySpliceNode.hx)

### Array String

Stores an array of string elements as a variable.


![Array String node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_string.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayStringNode.hx)

### Array Vector

Stores an array of vector elements as a variable.


![Array Vector node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/array/LNArrayVectorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/array/LN_array_vector.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ArrayVectorNode.hx)

## Math

### Compare

Compares values.


![Compare node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNCompareNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_compare.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CompareNode.hx)

### Deg to Rad

Converts degrees to radians.


![Deg to Rad node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNDegToRadNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_deg_to_rad.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/DegToRadNode.hx)

### Math

Mathematical operations on values.


![Math node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNMathNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_math.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MathNode.hx)

### Matrix Math

Multiplies matrices.


![Matrix Math node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNMatrixMathNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_matrix_math.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MatrixMathNode.hx)

### Mix

Interpolates between the two given values.


![Mix node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNMixNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_mix.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MixNode.hx)

### Mix Vector

Interpolates between the two given vectors.


![Mix Vector node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNVectorMixNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_mix_vector.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorMixNode.hx)

### Rad to Deg

Converts radians to degrees.


![Rad to Deg node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNRadToDegNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_rad_to_deg.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RadToDegNode.hx)

### Screen To World Space

Transforms the given screen coordinates into world coordinates.


![Screen To World Space node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNScreenToWorldSpaceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_screen_to_world_space.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ScreenToWorldSpaceNode.hx)

### Separate RGB

Splits the given color into RGB values.


![Separate RGB node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNSeparateColorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_separate_rgb.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SeparateColorNode.hx)

### Separate XYZ

Splits the given vector into XYZ values.


![Separate XYZ node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNSeparateVectorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_separate_xyz.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SeparateVectorNode.hx)

### Vector Clamp To Size

Keeps the vector value inside the given range.


![Vector Clamp To Size node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNVectorClampToSizeNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_vector_clamp_to_size.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorClampToSizeNode.hx)

### Vector Math

Operates vectors. Some operations uses only the first input.


![Vector Math node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNVectorMathNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_vector_math.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorMathNode.hx)

### World To Screen Space

Transforms the given world coordinates into screen coordinates.


![World To Screen Space node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/math/LNWorldToScreenSpaceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/math/LN_world_to_screen_space.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/WorldToScreenSpaceNode.hx)

## Random

### Random Boolean

Generates a random boolean.


![Random Boolean node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomBooleanNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_boolean.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomBooleanNode.hx)

### Random Choice

Choose a random value from a given array.


![Random Choice node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomChoiceNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_choice.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomChoiceNode.hx)

### Random Color

Generates a random color.


![Random Color node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomColorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_color.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomColorNode.hx)

### Random Float

Generates a random float.


![Random Float node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomFloatNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_float.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomFloatNode.hx)

### Random Integer

Generates a random integer.


![Random Integer node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomIntegerNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_integer.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomIntegerNode.hx)

### Random Output

Activate a random output when the input is activated.


![Random Output node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomOutputNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_output.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomOutputNode.hx)

### Random Vector

Generates a random vector.


![Random Vector node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/random/LNRandomVectorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/random/LN_random_vector.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RandomVectorNode.hx)

## String

### Concatenate String

Concatenates the given string.


![Concatenate String node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNConcatenateStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_concatenate_string.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ConcatenateStringNode.hx)

### Parse Float

Returns the floats that are in the given string.


![Parse Float node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNParseFloatNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_parse_float.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ParseFloatNode.hx)

### Split String

Splits the given string.


![Split String node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNSplitStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_split_string.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SplitStringNode.hx)

### String

Stores the given string as a variable.


![String node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_string.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/StringNode.hx)

### String Case

Changes the given string case.


![String Case node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNCaseStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_string_case.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CaseStringNode.hx)

### String Contains

Returns whether the given string contains a given part.


![String Contains node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNContainsStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_string_contains.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ContainsStringNode.hx)

### String Length

Returns the length of the given string.


![String Length node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNLengthStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_string_length.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LengthStringNode.hx)

### Sub String

Returns a part of the given string.


![Sub String node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/string/LNSubStringNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/string/LN_sub_string.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SubStringNode.hx)

## Variable

### Boolean

Stores the given boolean as a variable. A boolean value has just two states: `True` and `False`.


![Boolean node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNBooleanNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_boolean.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BooleanNode.hx)

### Color

Stores the given color as a variable.


![Color node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNColorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_color.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorNode.hx)

### Dynamic

Stores the given dynamic value (a value with an arbitrary type) as a variable.


![Dynamic node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNDynamicNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_dynamic.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/DynamicNode.hx)

### Float

Stores the given float as a variable. If the set float value has more than 3 decimal places, the displayed value in the node will be rounded, but when you click on it you can still edit the exact value which will be used in the game as well.


![Float node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNFloatNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_float.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/FloatNode.hx)

### Integer

Stores the given integer (a whole number) as a variable.


![Integer node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNIntegerNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_integer.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/IntegerNode.hx)

### Mask

TO DO.


![Mask node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNMaskNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_mask.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/MaskNode.hx)

### Set Variable

Sets the value of the given variable.


![Set Variable node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNSetVariableNode.jpg)

**Inputs:**

- `Variable`: this socket must be connected to a variable node (recognized by the little dot inside the socket). The value that is stored inside the connected node is changed upon activation.
- `Value`: the value that should be written into the variable.

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_set_variable.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetVariableNode.hx)

### Vector

Stores the given 3D vector as a variable.


![Vector node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/variable/LNVectorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/variable/LN_vector.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorNode.hx)

## Canvas

Note: To get the canvas, be sure that the node(s) and the canvas (UI) is attached to the same object.

### Get Canvas Checkbox

Returns whether the given UI checkbox is checked.


![Get Canvas Checkbox node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetCheckboxNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_checkbox.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetCheckboxNode.hx)

### Get Canvas Input Text

Returns the input text of the given UI element.


![Get Canvas Input Text node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetInputTextNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_input_text.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetInputTextNode.hx)

### Get Canvas Location

Returns the location of the given UI element (pixels).


![Get Canvas Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetLocationNode.hx)

### Get Canvas Position

TO DO.


![Get Canvas Position node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetPositionNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_position.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetPositionNode.hx)

### Get Canvas Progress Bar

Returns the value of the given UI progress bar.


![Get Canvas Progress Bar node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetPBNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_progress_bar.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetPBNode.hx)

### Get Canvas Rotation

Returns the rotation of the given UI element.


![Get Canvas Rotation node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetRotationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_rotation.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetRotationNode.hx)

### Get Canvas Scale

Returns the scale of the given UI element.


![Get Canvas Scale node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetScaleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_scale.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetScaleNode.hx)

### Get Canvas Slider

Returns the value of the given UI slider.


![Get Canvas Slider node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetSliderNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_slider.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetSliderNode.hx)

### Get Canvas Visible

Returns whether the given UI element is visible.


![Get Canvas Visible node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasGetVisibleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_get_canvas_visible.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasGetVisibleNode.hx)

### On Canvas Element

Activates the output whether an action over the given UI element is done.


![On Canvas Element node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNOnCanvasElementNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_on_canvas_element.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/OnCanvasElementNode.hx)

### Set Canvas Asset

Sets the asset of the given UI element.


![Set Canvas Asset node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetAssetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_asset.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetAssetNode.hx)

### Set Canvas Checkbox

Sets the state of the given UI checkbox.


![Set Canvas Checkbox node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetCheckBoxNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_checkbox.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetCheckBoxNode.hx)

### Set Canvas Location

Sets the location of the given UI element.


![Set Canvas Location node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetLocationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_location.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetLocationNode.hx)

### Set Canvas Progress Bar

Sets the value of the given UI progress bar.


![Set Canvas Progress Bar node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetPBNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_progress_bar.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetPBNode.hx)

### Set Canvas Rotation

Sets the rotation of the given UI element.


![Set Canvas Rotation node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetRotationNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_rotation.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetRotationNode.hx)

### Set Canvas Scale

Sets the scale of the given UI element.


![Set Canvas Scale node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetScaleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_scale.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetScaleNode.hx)

### Set Canvas Slider

Sets the value of the given UI slider.


![Set Canvas Slider node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetSliderNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_slider.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetSliderNode.hx)

### Set Canvas Text

Sets the text of the given UI element.


![Set Canvas Text node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetTextNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_text.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetTextNode.hx)

### Set Canvas Text Color

Sets the color of the given UI element.


![Set Canvas Text Color node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetTextColorNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_text_color.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetTextColorNode.hx)

### Set Canvas Visible

Sets whether the given UI element is visibile.


![Set Canvas Visible node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/canvas/LNCanvasSetVisibleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/canvas/LN_set_canvas_visible.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CanvasSetVisibleNode.hx)

## Postprocess

### Colorgrading Get Global

TO DO.


![Colorgrading Get Global node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingGetGlobalNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_get_global_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingGetGlobalNode.hx)

### Colorgrading Get Highlight

TO DO.


![Colorgrading Get Highlight node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingGetHighlightNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_get_highlight_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingGetHighlightNode.hx)

### Colorgrading Get Midtone

TO DO.


![Colorgrading Get Midtone node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingGetMidtoneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_get_midtone_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingGetMidtoneNode.hx)

### Colorgrading Get Shadow

TO DO.


![Colorgrading Get Shadow node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingGetShadowNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_get_shadow_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingGetShadowNode.hx)

### Colorgrading Set Global

TO DO.


![Colorgrading Set Global node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingSetGlobalNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_set_global_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingSetGlobalNode.hx)

### Colorgrading Set Highlight

TO DO.


![Colorgrading Set Highlight node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingSetHighlightNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_set_highlight_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingSetHighlightNode.hx)

### Colorgrading Set Midtone

TO DO.


![Colorgrading Set Midtone node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingSetMidtoneNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_set_midtone_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingSetMidtoneNode.hx)

### Colorgrading Set Shadow

TO DO.


![Colorgrading Set Shadow node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNColorgradingSetShadowNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_colorgrading_set_shadow_node.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ColorgradingSetShadowNode.hx)

### Get Bloom Settings

Returns the bloom post-processing settings.


![Get Bloom Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNBloomGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_get_bloom_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BloomGetNode.hx)

### Get CA Settings

Returns the chromatic aberration post-processing settings.


![Get CA Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNChromaticAberrationGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_get_ca_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ChromaticAberrationGetNode.hx)

### Get Camera Post Process

Returns the post-processing effects of a camera.


![Get Camera Post Process node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNCameraGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_get_camera_post_process.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CameraGetNode.hx)

### Get Lenstexture Settings

Returns the lens texture settings.


![Get Lenstexture Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNLenstextureGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_get_lenstexture_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LenstextureGetNode.hx)

### Get SSAO Settings

Returns the SSAO post-processing settings.


![Get SSAO Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNSSAOGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_get_ssao_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SSAOGetNode.hx)

### Get SSR Settings

Returns the SSR post-processing settings.


![Get SSR Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNSSRGetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_get_ssr_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SSRGetNode.hx)

### Set Bloom Settings

Set the bloom post-processing settings.


![Set Bloom Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNBloomSetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_set_bloom_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/BloomSetNode.hx)

### Set CA Settings

Set the chromatic aberration post-processing settings.


![Set CA Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNChromaticAberrationSetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_set_ca_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/ChromaticAberrationSetNode.hx)

### Set Camera Post Process

Set the post-processing effects of a camera.


![Set Camera Post Process node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNCameraSetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_set_camera_post_process.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CameraSetNode.hx)

### Set Lenstexture

Set the lens texture settings.


![Set Lenstexture node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNLenstextureSetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_lenstexture_set.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/LenstextureSetNode.hx)

### Set SSAO Settings

Set the SSAO post-processing settings.


![Set SSAO Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNSSAOSetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_set_ssao_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SSAOSetNode.hx)

### Set SSR Settings

Set the SSR post-processing settings.


![Set SSR Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/postprocess/LNSSRSetNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/postprocess/LN_set_ssr_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SSRSetNode.hx)

## Renderpath

### Set MSAA Quality

Sets the MSAA quality.


![Set MSAA Quality node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/renderpath/LNRpMSAANode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/renderpath/LN_set_msaa_quality.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RpMSAANode.hx)

### Set Post Process Quality

Sets the post process quality.


![Set Post Process Quality node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/renderpath/LNRpConfigNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/renderpath/LN_set_post_process_quality.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RpConfigNode.hx)

### Set SSAA Quality

Sets the supersampling quality.


![Set SSAA Quality node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/renderpath/LNRpSuperSampleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/renderpath/LN_set_ssaa_quality.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RpSuperSampleNode.hx)

### Set Shadows Quality

Sets the shadows quality.


![Set Shadows Quality node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/renderpath/LNRpShadowQualityNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/renderpath/LN_set_shadows_quality.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/RpShadowQualityNode.hx)

## Sound

### Pause Speaker

Pauses playback of the given speaker object. The playback will be resumed at the paused position.

**See also:**

- *[`Play Speaker`](#play-speaker)*
- *[`Stop Speaker`](#stop-speaker)*


![Pause Speaker node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/LNPauseSoundNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/sound/LN_pause_speaker.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PauseSoundNode.hx)

### Play Sound

Plays the given sound.


![Play Sound node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/LNPlaySoundRawNode.jpg)

**Inputs:**

- `Play`: Plays the sound, or if paused, resumes the playback. The exact behaviour depends on the Retrigger option (see below).
- `Pause`: Pauses the playing sound. If no sound is playing, nothing happens.
- `Stop`: Stops the playing sound. If the playback is paused, this will reset the playback position to the start of the sound.

**Outputs:**

- `Out`: activated once when Play is activated.
- `Running`: activated while the playback is active.
- `Done`: activated when the playback has finished or was stopped manually.

**Options:**

- `Sound`: The sound that will be played.
- `Loop`: Whether to loop the playback.
- `Retrigger`: If true, the playback position will be reset to the beginning on each activation of Play. If false, the playback will continue at the current position.
- `Sample Rate`: Manually override the sample rate of the sound (this controls the pitch and the playback speed).

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/sound/LN_play_sound.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PlaySoundRawNode.hx)

### Play Speaker

Starts the playback of the given speaker object. If the playback was paused, it is resumed from the paused position.

**See also:**

- *[`Pause Speaker`](#pause-speaker)*
- *[`Play Speaker`](#play-speaker)*


![Play Speaker node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/LNPlaySoundNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/sound/LN_play_speaker.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/PlaySoundNode.hx)

### Stop Speaker

Stops playback of the given speaker object. The playback position will be reset to the start.

**See also:**

- *[`Pause Speaker`](#pause-speaker)*
- *[`Play Speaker`](#play-speaker)*


![Stop Speaker node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/sound/LNStopSoundNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/sound/LN_stop_speaker.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/StopSoundNode.hx)

## Miscellaneous

### Call Node Group

Calls the given group of nodes.


![Call Node Group node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNCallGroupNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_call_group.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/CallGroupNode.hx)

### Default If Null

Returns the value in `Value In` if it is not `null`, otherwise the value in `Default` will be returned.


![Default If Null node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNDefaultIfNullNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_default_if_null.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/DefaultIfNullNode.hx)

### Get Application Time

Returns the application execution time and the delta time.


![Get Application Time node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNTimeNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_get_application_time.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TimeNode.hx)

### Get Debug Console Settings

Get Debug Console Settings


![Get Debug Console Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNGetDebugConsoleSettings.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_get_debug_console_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetDebugConsoleSettings.hx)

### Get Display Resolution

Returns the current display resolution.

**See also:**

- *[`Get Window Resolution`](#get-window-resolution)*


![Get Display Resolution node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNDisplayInfoNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_get_display_resolution.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/DisplayInfoNode.hx)

### Get Frames Per Second

Get the frames per second count.


![Get Frames Per Second node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNGetFPSNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_get_fps.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GetFPSNode.hx)

### Get Window Resolution

Returns the current window resolution.

**See also:**

- *[`Get Display Resolution`](#get-display-resolution)*


![Get Window Resolution node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNWindowInfoNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_get_window_resolution.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/WindowInfoNode.hx)

### Group Nodes

Sets the connected chain of nodes as a group of nodes.


![Group Nodes node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNGroupOutputNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_group_nodes.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/GroupOutputNode.hx)

### Set Debug Console Settings

Set Debug Console Settings


![Set Debug Console Settings node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNSetDebugConsoleSettings.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_set_debug_console_settings.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetDebugConsoleSettings.hx)

### Set Time Scale

Sets the global time scale.


![Set Time Scale node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNSetTimeScaleNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_set_time_scale.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SetTimeScaleNode.hx)

### Sleep

Waits a specified amount of seconds until passing through the incoming signal.


![Sleep node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNSleepNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_sleep.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/SleepNode.hx)

### Timer

Creates a timer.


![Timer node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNTimerNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_timer.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/TimerNode.hx)

### Vector From Boolean

Returns a vector depending on the respective boolean state.


![Vector From Boolean node](https://github.com/armory3d/armory_wiki_images/raw/master/logic_nodes/miscellaneous/LNVectorFromBooleanNode.jpg)

**Sources:** [Python](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/miscellaneous/LN_vector_from_boolean.py) | [Haxe](https://github.com/armory3d/armory/blob/master/Sources/armory/logicnode/VectorFromBooleanNode.hx)

## Layout

### Frame

### Reroute

