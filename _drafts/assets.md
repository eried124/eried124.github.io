# Models

- All meshes must have UV:s
  - UV channel 1 for textures
  - UV channel 2 for lightmaps. No overlapping for lightmap UV:s

- Apply transforms/scales before exportings
- Name meshes/objects in Maya/Blender
- Add collisions
- Triangulate before exporting
- Auto generate LoD:s

# Textures

- Textures must be multiples of two, but not necessarily square. No bigger than 8192
- Texture/texel density should be uniform
- Axis and scale

# Notes

- Blueprint <-> prefab
- Z-fighting
- Asset testing map
- Texel density