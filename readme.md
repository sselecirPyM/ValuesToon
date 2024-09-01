# ValuesToon
PBR-like toon shader for Godot 4. Support multiple light sources.

![ValuesToon](https://github.com/user-attachments/assets/d746a34a-314a-4d27-9563-e71a0a0a9a44)

## Explain

This shader is inspired by physical lighting calculations, calculating diffuse, specular, and rim lights.

Diffuse uses the Lambert model, but does not perform the clamp01 step and then remaps the output with a gradient map.

Specular reflections use the Blinn-Phong model, specify an exponent of 5, and then remap the output with a gradient map.

This shader uses 1 - N dot V to compute the rim light and then remap the output with a gradient map. Modify the RimEnergyLightSpecular to make the Rim light look like a highlight.

Environment lighting still uses physical lighting, a shader that allows you to adjust the intensity, and doesn't use albedo maps.

When a pixel is illuminated by multiple light sources, the end result is a separate maximum for RGB, which I think is pretty good.

The scattered light is calculated as L dot V and then remapped with a gradient map, multiplied by rim light. For opaque objects, ignore it.

It's easy to create gradient maps in Godot, so this shader comes in.


## Credit
The 3D model of the README is made by SANMUYYB.