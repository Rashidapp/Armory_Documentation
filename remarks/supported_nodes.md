# Supported Nodes

While the plan is to support all of the nodes, not all of them work yet. Currently Armory implements the following ones.

> *The following tables are not yet complete, please look at [blender/arm/material/cycles_nodes](https://github.com/armory3d/armory/tree/master/blender/arm/material/cycles_nodes) for detailed information.*

**Legend**:
✔ Full support 🔵 Not fully implemented ❌ Not supported/Will not be supported

### Shader
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Principled BSDF | `BSDF_PRINCIPLED` | 🔵 | Not all sockets yet |
| Mix Shader | `MIX_SHADER` | ✔ | |
| Add Shader | `ADD_SHADER` | ✔ | |
| Diffuse BSDF | `BSDF_DIFFUSE` | ✔ | |
| Glossy BSDF | `BSDF_GLOSSY` | ✔ | |
| Emission | `EMISSION` | ✔ | |
| Glass BSDF | `BSDF_GLASS` | 🔵 | |
| Holdout | `HOLDOUT` | ✔ | |
| Translucent BSDF | `BSDF_TRANSLUCENT` | 🔵 | |
| Transparent BSDF | `BSDF_TRANSPARENT` | ✔ | |
| Velvet BSDF | `BSDF_VELVET` | 🔵 | |
| Subsurface Scattering | `SUBSURFACE_SCATTERING` | 🔵 | |

### Input
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Attribute | `ATTRIBUTE` | 🔵 | Doesn't support all of Blender's attributes. You can access vertex colors (using the color output), UV maps and `time`) |
| Camera Data | `CAMERA` | ✔ | |
| Fresnel | `FRESNEL` | ✔ | |
| Geometry | `NEW_GEOMETRY` | 🔵 | All outputs supported except for `Pointiness` and `Random Per Island` |
| Layer Weight | `LAYER_WEIGHT` | ✔ | |
| Light Path | `LIGHT_PATH` | ❌ | Using preconfigured values (no raytracing) |
| Object Info | `OBJECT_INFO` | 🔵 | All outputs supported except for `Color` |
| Particle Info | `PARTICLE_INFO` | 🔵 | GPU Particles. All outputs supported except for `Random`, `Size` and `Angular Velocity` |
| RGB | `RGB` | ✔ | |
| Tangent | `TANGENT` | 🔵 | |
| Texture Coordinate | `TEX_COORD` | 🔵 | All outputs supported except for `Camera`, `Reflection`. Also it is not possible to access other object's coordinates |
| UV Map | `UVMAP` | ✔ | |
| Value | `VALUE` | ✔ | |
| Vertex Color | `VERTEX_COLOR` | ✔ | |

### Output
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Material Output | `OUTPUT_MATERIAL` | 🔵 | `Volume` input not supported |
| World Output | `OUTPUT_WORLD` | 🔵 | Currently only `Background` and `Emission` nodes can be directly connected to this node |

### Converter
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Blackbody | `BLACKBODY` | ✔ | |
| Clamp | `CLAMP` | ✔ | |
| Color Ramp | `VALTORGB` | 🔵 | Only color output with constant or linear RGB interpolation |
| Combine HSV | `COMBHSV` | ✔ | |
| Combine RGB | `COMBRGB` | ✔ | |
| Combine XYZ | `COMBXYZ` | ✔ | |
| Math | `MATH` | 🔵 | Most operators are supported but some are still missing |
| RGB to BW | `RGBTOBW` | ✔ | |
| Separate RGB | `SEPBRGB` | ✔ | |
| Separate XYZ | `SEPBXYZ` | ✔ | |
| Vector Math | `VECT_MATH` | ✔ | Modulo operator behaves differently in Blender/Armory with negative numbers |
| Wavelength | `WAVELENGTH` | ✔ | |

### Color
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Bright Contrast | `BRIGHTCONTRAST` | ✔ | |
| Gamma | `GAMMA` | ✔ | |
| Hue/Saturation | `HUE_SAT ` | ✔ | |
| Invert | `INVERT` | ✔ | |
| MixRGB | `MIX_RGB` | 🔵 | Some blend types default to `Mix` |
| RGB Curves | `CURVE_RGB` | 🔵 | |

### Texture
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Brick Texture | `TEX_BRICK` | 🔵 | |
| Checker Texture | `TEX_CHECKER` | ✔ | |
| Environment Texture | `TEX_ENVIRONMENT` | ✔ | World shader only |
| Gradient Texture | `TEX_GRADIENT` | 🔵 | |
| Image Texture | `TEX_IMAGE` | ✔ | |
| Magic Texture | `TEX_MAGIC` | 🔵 | |
| Musgrave Texture | `TEX_MUSGRAVE` | 🔵 | |
| Noise Texture | `TEX_NOISE` | ✔ | |
| Sky Texture | `TEX_VORONOI` | 🔵 | World shader only |
| Voronoi Texture | `TEX_VORONOI` | 🔵 | |
| Wave Texture | `TEX_WAVE` | 🔵 | |

### Vector
| Node name | Blender Identifier | Supported | Additional information |
| --- | --- | --- | --- |
| Bump| `BUMP` | ✔ | |
| Displacement | `DISPLACEMENT` | 🔵 | |
| Normal | `NORMAL` | ✔ | |
| Normal Map| `NORMAL_MAP` | ✔ | |
| Mapping | `MAPPING` | 🔵 | 'Normal' mapping type is not supported yet |
| Vector Curves| `CURVE_VEC` | ✔ | |

## Armory material nodes

Armory provides additional nodes in the `Armory` node category to ease shader creation:

- **Shader Data**

  ![Shader Data node](https://github.com/armory3d/armory_wiki_images/raw/master/remarks/supported_nodes/shaderdata_node.jpg)  
  *Example: Retrieving the position of object instances (`ipos`) from the vertex shader.*
  
  **Usage**:
  This node lets you access shader data from [uniforms](https://www.khronos.org/opengl/wiki/Uniform_(GLSL)) and shader inputs. You can switch
  between both types via the `Input Type` toggle.

  - **`Input` mode**  
    This mode allows you to use the contents of values passed as inputs to the vertex or fragment shader stage. You can choose the stage via the `Input Source` dropdown. If `Vertex Shader` is selected, the variable gets passed through to the fragment shader where it is used.

  - **`Uniform` mode**  
    This mode allows you to access the contents of uniform values that are provided by Iron in [Uniforms.hx](https://github.com/armory3d/iron/blob/master/Sources/iron/object/Uniforms.hx). Armory will automatically add the selected uniforms to the generated shader. You can find a list of available uniforms [here](https://github.com/armory3d/armory/wiki/materials#available-uniforms). A more detailed explanation of this mode can be found [here](https://github.com/armory3d/armory/wiki/materials#shader-uniforms).

  The chosen `Variable Type` represents the data type of the value and the `Variable Name` represents either the input name in the shader code or the link name of the uniform.