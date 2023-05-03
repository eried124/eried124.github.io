# Folder structure

The `TNM061Project` project folder contains two top level folders.

- The `ContentSource` folder for the invidivual asset source files (source/project files from Maya/Blender and any asset project files)
- The `UnrealProject` folder for the exported assets and Unreal Engine project files.


## UnrealProject folder

```
Content
├── Common              Placeholders, gizmo icons and IES files
├── Core                Core engine files and utilities
├── Editor
│   └── ConsoleVars     Console variable presets
├── Effects             Visual effect presets
├── Import              Temporary folder for content imported from other softwares
├── Levels
│   ├── TestLevels
│   │   ├── AssetLevel  Used to assemble and test imported assets
│   │   └── Sandbox     Used for testing various visuals and map settings
│   └── MainMap         The main environment map
├── Materials           Contains material instances and templates
│   ├── Blockout        Contains materials for level blockout
│   └── Templates       Contains "master" materials/templates which to instances from
├── Placeables
│   ├── Blockout        Contains primitives for level blockout
│   ├── Decals          Texture projectors for decals such as graffiti or dirt
│   ├── Props           Props/objects with materials applied to be used in levels
│   └── Structures      Walls, floors, ceiling, pillar structures
└── Textures            Texture files which are used in materials