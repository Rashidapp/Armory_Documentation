# Logic Nodes

This page shows how to create custom logic nodes in a node package. The same approach is used to edit or add new nodes to Armory itself. In this case, don't create a library as described on this page and use the `blender/arm/logicnode/` folder for Python node definitions and `Sources/armory/logicnode` for the node's Haxe source code.

**Content**:
- [Create a library](#create-a-library)
- [Python](#python)
  - [Python API](#python-api)
- [Haxe](#haxe)
- [Next steps](#next-steps)

## Create a library

We will make a new library to store the sources of custom logic nodes and keep them portable with no modifications to engine sources.

Locate your blend file and create a new `Libraries` folder alongside it. Navigate to the `Libraries` folder and create a new `mynodes` folder in it to place your new node.

## Python

Next, we will create the logic node definition for Blender. 

To do so, we have to create a file named `blender.py` in `Libraries/mynodes` folder. Armory automatically picks this file up once the library is loaded. 

Define a simple node with single in/out socket like the one in the example below.

```py
from bpy.types import Node

from arm.logicnode.arm_nodes import *
import arm.nodes_logic


# Extend from ArmLogicTreeNode so that the node is recognized as a logic node
class TestNode(ArmLogicTreeNode):
    """Test node"""
    bl_idname = 'LNTestNode'
    bl_label = 'Test'

    # Use this as a tooltip in the add node menu.
    # If `bl_description` does not exist, the docstring of this node is used instead.
    bl_description = 'This is a test node'

    def init(self, context):
        self.add_input('ArmNodeSocketAction', 'In')
        self.add_output('ArmNodeSocketAction', 'Out')


# Register this custom node into the `Action` category
add_node(TestNode, category='Action')
```

Restarting Blender and loading the project again, the new logic node is available for placement.

![](https://github.com/armory3d/armory_wiki_images/raw/master/dev/logicnodes/0.png)

### Python API

Armory provides a small API in [`arm_nodes.py`](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/arm_nodes.py) to ease working with logic nodes.

#### Methods for `ArmLogicTreeNode`

- **Adding input/output sockets**:
  ```python
  def add_input(self, socket_type: str, socket_name: str, default_value: Any = None, is_var: bool = False) -> bpy.types.NodeSocket:
  def add_output(self, socket_type: str, socket_name: str, default_value: Any = None, is_var: bool = False) -> bpy.types.NodeSocket:
  ```
  Small wrapper methods around `self.inputs.new()` and `self.outputs.new()`.

  If a `default_value` is given, the socket will use this value if it has no connection.
  If `is_var` is set to `True`, the socket will have a small dot in the middle to show that this socket can be used for [accessing a variable](https://github.com/armory3d/armory/wiki/reference#variables).

  > Additional available socket types can be found in [arm_sockets.py](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/arm_sockets.py). Libraries can also define their own socket types.

- **Node versioning**
  ```python
  def get_replacement_node(self, node_tree: bpy.types.NodeTree) -> arm.logicnode.arm_nodes.NodeReplacement:
  ```
  Todo.

#### Static methods

There are a bunch of static methods that allow you to register nodes and create node categories. For a in-depth overview, please look at [`arm_nodes.py`](https://github.com/armory3d/armory/blob/master/blender/arm/logicnode/arm_nodes.py). On this page, only some often-used methods are documented.

- <br>

  ```python
  def add_node(node_type: Type[bpy.types.Node], category: str, section: str = 'default', is_obsolete: bool = False) -> None:
  ```
  Registers a logic node so that it is displayed in the add node menu.

  - `node_type`: The class of the node (see example code in the [Python](#python) section)
  - `category`: The category this node belongs in (see example code in the [Python](#python) section). If the category does not exist yet, it is created. If you pass `PKG_AS_CATEGORY` (defined in `arm_nodes.py`), the capitalized name of the Python package the node definition file is in is used as the category name. When you later rename a category, you don't have to change all calls to `add_node` when using this constant.
  - `section` (optional): Add this node into a sub-section of nodes in that given category. Node sections are visually grouped together in the menu. If the section does not exist yet, it is created.
  - `is_obsolete` (optional): Todo

- <br>

  ```python
  def add_category(category: str, section: str = 'default', icon: str = 'BLANK1', description: str = '') -> Optional[ArmNodeCategory]:
  ```
  Adds a category of nodes to the node menu and returns the `ArmNodeCategory` object if the category didn't exist yet.
  
  - `category`: The name of the category
  - `section` (optional): Just like node sections explained above, categories can also be grouped into visually separated sections. If the section does not exist yet, it is created.
  - `icon` (optional): Blender icon constant to give each node in this category a icon. The icon is also displayed in the node menu.
  - `description` (optional): Description of this category. This value is currently unused but might be used in the future to display tooltips.

- <br>

  ```python
  def add_node_section(name: str, category: str) -> None:
  ```
  Adds a section of nodes to the sub menu of the given category to group multiple nodes visually together. The given name only acts as an ID and is not displayed in the user inferface.

- <br>

  ```python
  def add_category_section(name: str) -> None:
  ```
  Adds a section of categories to the node menu to group multiple categories visually together. The given name only acts as an ID and is not displayed in the user inferface.

## Haxe

Before the project can be run, we need to implement the actual node logic in Haxe. 

Start by creating the folder structure `Sources/armory/logicnode/` in the same folder of `blender.py`.

Next, create a `TestNode.hx` file inside the `logicnode` folder just created, and place the code from below in the file.

When the node gets executed, we let it print a 'Hello, World!' string.

```haxe
package armory.logicnode;

class TestNode extends LogicNode {

    public function new(tree:LogicTree) {
        super(tree);
    }

    override function run(from: Int) {
        // Logic for this node
        trace("Hello, World!");

        // Execute next action linked to this node, this activates the output socket at position/index 0
        runOutput(0);
    }
}
```

## Next steps

- Example project:
https://github.com/armory3d/armory_examples/tree/master/dev_logicnode

When implementing new logic nodes, browse the sources of existing nodes as a reference:

- Python definitions of Armory nodes:
https://github.com/armory3d/armory/tree/master/blender/arm/logicnode

- Haxe implementation:
https://github.com/armory3d/armory/tree/master/Sources/armory/logicnode
