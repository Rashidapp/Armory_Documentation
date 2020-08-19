# Supported Nodes

While the plan is to support all of the nodes, not all of them work yet. Currently Armory implements the following ones.

## Cycles material nodes

- BSDF_PRINCIPLED (Principled BSDF) - not all sockets yet
- MIX_SHADER (Mix Shader)
- ADD_SHADER (Add Shader)
- BSDF_DIFFUSE (Diffuse BSDF)
- BSDF_GLOSSY (Glossy BSDF)
- EMISSION - (Emission) - as bloom only
- BSDF_GLASS (Glass BSDF)
- BSDF_TRANSLUCENT (Translucent BSDF)
- BSDF_TRANSPARENT (Transparent BSDF)
- SUBSURFACE_SCATTERING (Subsurface Scattering)
- AMBIENT_OCCLUSION (Ambient Occlusion)
- OUTPUT_MATERIAL (Material Output)
- ATTRIBUTE (Attribute) - accessing vertex colors, UV maps and 'time'
- RGB (RGB)
- MIX_RGB (Mix)
- COMBRGB (Combine RGB)
- COMBXYZ (Combine XYZ)
- SEPRGB (Separate RGB)
- SEPXYZ (Separate XYZ)
- VALTORGB - (Color Ramp)
- BRIGHTCONTRAST (Bright Contrast)
- TEX_IMAGE (Image Texture)
- GAMMA (Gamma)
- HUE_SAT (Hue/Saturation)
- INVERT (Invert)
- CAMERA (Camera Data)
- NEW_GEOMETRY (Geometry)
- OBJECT_INFO (Object Info)
- TEX_COORD (Texture Coordinate) - UV socket only
- NORMAL (Normal)
- NORMAL_MAP (Normal Map)
- VECT_MATH (Vector Math)
- FRESNEL (Fresnel)
- LAYER_WEIGHT (Layer Weight)
- VALUE (Value)
- MATH (Math)
- RGBTOBW (RGB to BW)
- TEX_CHECKER (Checker Texture)
- TEX_NOISE (Noise Texture)
- TEX_GRADIENT (Gradient Texture)
- TEX_VORONOI (Voronoi Texture)
- MAPPING (Mapping) - 'Normal' mapping type is not supported yet
- PARTICLE_INFO (Particle Info) - GPU particles
- VERTEX_COLOR (Vertex Color)

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
    This mode allows you to access the contents of uniform values that are provided by Iron in [Uniforms.hx](https://github.com/armory3d/iron/blob/master/Sources/iron/object/Uniforms.hx). Armory will automatically add the selected uniforms to the generated shader. You can find a list of available uniforms [here](https://github.com/armory3d/armory/wiki/materials/_edit#available-uniforms). A more detailed explanation of this mode can be found [here](https://github.com/armory3d/armory/wiki/materials/_edit#shader-uniforms).

  The chosen `Variable Type` represents the data type of the value and the `Variable Name` represents either the input name in the shader code or the link name of the uniform.