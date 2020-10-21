# Materials

![](https://github.com/armory3d/armory_wiki_images/raw/master/graphics/materials/materials.jpg)

Materials are built with [Cycles nodes](https://docs.blender.org/manual/en/dev/render/cycles/nodes/index.html).

## Table of Content
- [Displacement](#displacement)
- [Blending](#blending)
- [Transparency](#transparency)
- [Material parameters](#material-parameters)
- [Shader uniforms](#shader-uniforms)
  - [Available uniforms](#available-uniforms)

## Displacement

Locate the `Armory Render Path - Renderer - Displacement` property:
- `Off` - No displacement performed
- `Vertex` - Mesh vertices are displaced
- `Tessellation` - Mesh is first tessellated for more detail and then displaced

With `Tessellation` selected, the level of tessellation can be set using the `Mesh` and `Shadow` property.

Note: Vertices are displaced in normals direction. Use smooth shading (`Space - Shade Smooth`) for meshes with displacement to prevent gabs.

Examples:
- https://github.com/armory3d/armory_examples/tree/master/material_examples

## Blending

To enable additive blending for specific material, set `Armory Render Path - Blending` to `On` and check the `Blending` property in `Material - Armory Props`.

Examples:
- https://github.com/armory3d/armory_examples/tree/master/material_translucent
- https://github.com/armory3d/armory_examples/tree/master/particle_examples

## Transparency

- Connect an alpha map to the Principled BSDF input of a material.
- Material properties: Armory Props: Uncheck Alpha Test.

## Material parameters

`RGB`, `Value` and `Image Texture` material nodes can be controlled at run-time using script or logic nodes. To expose material node, enable `Parameter` property in `Node Editor - Properties - Armory Material Node`.

Examples:
- https://github.com/armory3d/armory_examples/tree/master/material_params

## Shader uniforms

It is possible to retrieve additional light and scene data via [uniforms](https://www.khronos.org/opengl/wiki/Uniform_(GLSL)). There are two different ways of using them:

- **Using material nodes**:

  It is possible to access uniform values with the [Shader Data node](https://github.com/armory3d/armory/wiki/supported_nodes#armory-material-nodes). To do this, set the input type to `Uniform` and select the variable type (only uniforms of those data types are currently supported in node shaders). Then, look at [Available uniforms](#available-uniforms) and write the name of the link (e.g. `_pointPosition`) for the uniform into the `Variable Name` field.

  Please note that there is no viewport preview for the Shader Data node!

  **Example**:  
  ![Example of the Attribute node with a shader uniform](https://github.com/armory3d/armory_wiki_images/raw/master/graphics/materials/shaderdata_node_uniforms.jpg)

- **Custom materials**:

  To pass a uniform to the fragment shader, add an entry in the material definition ([example](https://github.com/armory3d/armory_examples/blob/master/material_shaders/Bundled/MyMaterial/MyMaterial.json)) under `"shader_datas" > "contexts" > "constants"`:

  ```json
  {
      "link": "<linkName>",
      "name": "<uniformName>",
      "type": "<uniformType>"
  }
  ```
  Replace `<linkName>` with the name of the link (e.g. `"_pointPosition"`) that can be found in [Available uniforms](#available-uniforms) and replace `<uniformName>` and `<uniformType>` according to your fragment shader.


### Available uniforms

*(The following tables are not yet complete, please look into [Uniforms.hx](https://github.com/armory3d/iron/blob/master/Sources/iron/object/Uniforms.hx) for all available uniforms).*

**Camera**:
| Link name | Type | Description |
| --- | --- | --- |
| `_cameraPlane` | `vec2` | x: camera near plane, y: camera far plane |
| `_cameraPosition` | `vec3` | World position of the active camera |
| `_cameraLook` | `vec3` | Normalized look vector of the active camera in world coordinates |
| `_cameraUp` | `vec3` | Normalized up vector of the active camera in world coordinates |
| `_cameraRight` | `vec3` | Normalized right vector of the active camera in world coordinates |
| `_fieldOfView` | `vec3` | Field of view of the active camera |
| `_viewMatrix` | `mat4` | View matrix of the active camera |
| `_transposeViewMatrix` | `mat4` | View matrix of the active camera with rows and columns 0-2 (3x3) transposed |
| `_projectionMatrix` | `mat4` | Projection matrix of the active camera |
| `_inverseProjectionMatrix` | `mat4` | Inverse of the projection matrix of the active camera |
| `_viewProjectionMatrix` | `mat4` | View matrix multiplied with the projection matrix of the active camera |
| `_inverseViewProjectionMatrix` | `mat4` | View matrix multiplied with the projection matrix of the active camera and inversed |
| `_prevViewProjectionMatrix` | `mat4` | `_viewProjectionMatrix` from the previous frame |

**Lights**:
| Link name | Type | Description |
| --- | --- | --- |
| `_lightDirection` | `vec3` |  |
| `_lightPosition` | `vec3` |  |
| `_pointPosition` | `vec3` |  |
| `_pointColor` | `vec3` |  |
| `_sunColor` | `vec3` |  |
| `_sunDirection` | `vec3` |  |
| `_spotDirection` | `vec3` |  |
| `_lightArea0` - `_lightArea3` | `vec3` |  |

**Objects**:
| Link name | Type | Description |
| --- | --- | --- |
| `_uid` | `int` | The UID of the object |
| `_objectInfoIndex` | `float` | The UID of the object |
| `_objectInfoMaterialIndex` | `float` | The UID of the object's current material |
| `_objectInfoRandom` | `float` | Random value that was assigned to the object during it's creation |
| `_skinBones` | `float[]` | Dual Quaternion skinning buffer. Only available when `arm_skin` is defined. |

**World**:
| Link name | Type | Description |
| --- | --- | --- |
| `_backgroundCol` | `vec3` | The background color of the current world. `(0, 0, 0)` if not set |
| `_envmapStrength` | `float` | The strength of the world background. `0` if the scene has no world |
| `_hosekSunDirection` | `vec3` | The direction of the sun. The z value is clamped below (and including) 0 for the night cycle. `(0, 0, 0)` if the scene has no world |

**Other**:
| Link name | Type | Description |
| --- | --- | --- |
| `_time` | `float` | The elapsed time since the beginning of the game |
| `_vec2x` | `vec2` | Base vector for the x axis (`(1.0, 0.0)`) |
| `_vec2xInv` | `vec2` | Base vector for the x axis divided by the current render target width |
| `_vec2x2` | `vec2` | Base vector for the x axis multiplied by 2 (`(2.0, 0.0)`) |
| `_vec2x2Inv` | `vec2` | Base vector for the x axis multiplied by 2 and divided by the current render target width |
| `_vec2y` | `vec2` | Base vector for the y axis (`(0.0, 1.0)`) |
| `_vec2yInv` | `vec2` | Base vector for the y axis divided by the current render target height |
| `_vec2y2` | `vec2` | Base vector for the y axis multiplied by 2 (`(0.0, 2.0)`) |
| `_vec2y2Inv` | `vec2` | Base vector for the y axis multiplied by 2 and divided by the current render target height |
| `_vec2y3` | `vec2` | Base vector for the y axis multiplied by 3 (`(0.0, 3.0)`) |
| `_vec2y3Inv` | `vec2` | Base vector for the y axis multiplied by 3 and divided by the current render target height |
| `_windowSize` | `vec2` | Window size (x, y) in pixels |
| `_screenSize` | `vec2` | Screen size (size of the renderpath's current render target) in pixels |
| `_screenSizeInv` | `vec2` | Inverse of `_screenSize` (`1.0 / _screenSize`) |
| `_aspectRatioF` | `float` | Aspect ratio of the current render target (width / height) |
| `_aspectRatioWindowF` | `float` | Aspect ratio of the game window (width / height) |