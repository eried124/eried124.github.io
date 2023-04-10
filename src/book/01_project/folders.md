# Folder structure

The project contains two top level folders. 

- The `ContentSource` folder for the source asset files (source/project files from Maya/Blender and any asset project files)
- The `UnrealProject` folder for the exported assets and Unreal Engine project files.

## ContentSource folder

```
Common                  (Common assets, such as generic textures)
Assets
    Structures          (Core structures such as walls/floors)
        Walls
        Pillars
        Trims
        Floors
        Panels
        ...
    Props               (Prop objects used to populate the environment)
        Furniture
        Pipe
        Plants
        ...
```

## UnrealProject folder

```
Audio
    Ambient
    Effects
Core                    (Core resources required to run the project)
    Debug
    GameMode
    PlayerController
    Scripts
Effects                 (Visual effect presets)
    Lights
    Particles
    PostProcessing
Imports                 (Content imported from other softwares)
    Assets              (Imported assets, not to be used directly)
    Common              (Common assets, such as generic textures)
Maps                    (Levels/scenes)
    AssetMap            (Map used to assemble and test imported assets)
    MainMap             (The main environment map)
    <member>sMap        (Each project-members own test map)
Materials               (Reusable materials not tied to any specific asset)
    Templates           (Master materials which new materials are instanced from)
        PBRMaterial     (The main material template)
        DecalMaterial   (Material used for decal projections)
    Metal
    Paint
    Glass
Placeables              (Placeable props assembled from imported assets)
    Blockout            (Primitives used to block-out/prototype the environment)
    Decals              (Decal projections such as dirt or graffiti)
    Structures          (Core structures such as walls/floors)
        Walls
        Pillars
        Trims
        Floors
        Panels
        ...
    Props               (Prop objects used to populate the environment)
        Furniture
        Pipe
        Plants
        ...
    Utilities           (Utilities such as size references)
UI                      (User interface resources)
```