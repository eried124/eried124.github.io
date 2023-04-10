# Workflow

## Asset Creation Workflow

1. **Create a new folder for the asset in the `ContentSource` folder**
1. **Gather reference**
    - Search for and find images of the object you are going to model that showcase it from multiple angles. [PureRef](https://www.pureref.com/) is a very handy tool for collecting references
2. **Create a base mesh/model**
    - A base mesh captures the overall shape and silhouette of the object but does not have a lot of details. A model "sketch"
3. **Export the base mesh and import it in Unreal Engine**
    - It's important to check that the model have realistic dimensions compared to the other objects within the engine
4. **Make any scale/proportion corrections**
5. **Finialize the model**
    - Add in any remaining details and start optimizing the model by reducing unecessary geometry
6. **UV-unwrapping**
    - Every model requires UV-maps to work properly with materials
7. (Optional) **Triangulate the mesh**
8. **Export the mesh and import it in Unreal Engine**
9.  **Assign materials**
10. **Test it in your test map**
    - Each team member should have their own test map where they can test assets without breaking the main map
11. **Add the asset the `Placeable` folder**
    - Find and put it a suitable subfolder in `Placeables` (or create one if no suitable subfolder exists) 

Suggested folder structure for working on an asset:

```
AssetName
    Export          (exported files for Unreal Engine)
    Reference       (reference images)
    Models          (model files)
    Textures        (texture files if applicable)
```

## Project Workflow

1. **Prototyping**
    - Layout concepting
    - Block-out environment
2. **Asset creation**
    - Inventory of required assets, division of labor
    - Asset creation (modeling, unwrapping, export/import)
3. **Environment assembly**
    - Replace block-out meshes with created assets
    - Lighting the level
    - Particles, interactive elements
    - Character/camera controller
4. **Content lock & review**
    - Evaluate environment, detail pass
    - Remove any prototype/block-out meshes
5. **Final preparations**
    - Lightmap preparation and baking [^lightmap_uvs]
    - Reflection Capture placement and baking
    - LoD generation [^lod_gen]
    - Proxy mesh generation [^proxy_gen]
    - Post-processing volumes [^post]
        - Color grading, Vignette
        - Exposure, Bloom, Light Shafts
        - SSGI, SSAO, SSR
6. **Render HQ frames with "Movie Render Queue"** [^render]

---

[^lightmap_uvs]: [Lightmapping in UE](https://docs.unrealengine.com/5.1/en-US/understanding-lightmapping-in-unreal-engine/)
- LightmassImportanceVolume placement
- Per mesh Static Mesh resolution (not overrides)
- Lighmass Portal placement

[^lod_gen]: [LOD generation](https://docs.unrealengine.com/5.1/en-US/static-mesh-automatic-lod-generation-in-unreal-engine/)

[^proxy_gen]: [Proxy mesh generation](https://docs.unrealengine.com/5.1/en-US/building-hierarchical-level-of-detail-meshes-in-unreal-engine/)

[^post]: [Post Processing](https://docs.unrealengine.com/5.1/en-US/post-process-effects-in-unreal-engine/)

[^render]: [Rendering HQ Frames](https://docs.unrealengine.com/5.1/en-US/rendering-high-quality-frames-with-movie-render-queue-in-unreal-engine/)