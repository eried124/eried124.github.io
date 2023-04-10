# Final checks

Some feature tweaks and settings that should be checked before publishing the final build at the end of the project.

## Textures

- Ensure anisotropic texture filtering
- Virtual Texture settings/Texture Streaming

## Materials

- Ensure usage of Material Instances, no unique non-base materials
- Bump offset (POM) candidates for materials with height/depth
- Flow maps using Distance Fields in a material

## Lighting

- Light overlaps, max 4 stationary light overlaps per geometry piece 
    - Directional light counts as a global layer, thus 3 light overlaps with a directional light
- Test SSGI in combination with conjunction with Lightmaps
- Reduce Lightmass AO contribution (already computes proper indirect lighting)
- Contact shadow and disabling of low-contribution shadow casters
- Light mobilities (static/movable)
    - Stationary cost is based on movable objects within its frustum. Can use cascades and fade to baked lighting at far distances. Also supports variable brightness and color while maintaining indirect lighting
- Reflection Capture spheres (sphere has uniform errors, box has discontinuities in corners)
  - 341 captures is the DX11 hardlimit
  - Adjust resolution
  - Evaluate with Static and Stationary (docs. recommends Stationary as it will blend specular capture with diffuse reflections)
- Capsule Shadowing for highly dynamic objects
- Determine the lowest usable Sky Light Cubemap Resolution
  - Possibly Stationary Mobility with Bent Normals (most un-occluded direction relative to the texel) if indirect color changes are possible 
- Virtual- vs Cascade- vs Distance Field Shadows

## Particles

- Check if Sort Priority needs any changes
- Transclucent/smoke particles shadowing [shadowed with Stationary Light bakes](https://docs.unrealengine.com/5.1/en-US/stationary-light-mobility-in-unreal-engine/)


## Rendering

- Debug view:
  - Lightmap density
  - Texel density
  - Overdraw, light overlap, shader complexity
- Verify that occlusion culling works properly

## Geometry

- Ensure convex collisions
- Ensure Proxy meshes are used for [shadow casting geometry](https://docs.unrealengine.com/5.1/en-US/proxy-geometry-shadows-in-unreal-engine/)
    - [Possibly merge Actor clusters?](https://docs.unrealengine.com/5.1/en-US/improving-normals-with-the-proxy-geometry-tool-in-unreal-engine/)