# Conventions

Sensible and explicit names will help us finding things quickly. 

Although we will use fairly standardized conventions (based on Epic's recommendations), I have omitted certain parts and adapted it to our smaller scale project.

## General Naming Convention

- In general, use [Pascal-case/upper camel case](https://en.wikipedia.org/wiki/Camel_case) (joined phrases where the first letter of each word is capitalized)
    - _(This is a common convention in Unreal Engine and Unity projects)_
- Avoid spaces and non-unicode characters as they can cause reference and build issues
    - Stick to using lowercase letters `a-z`, uppercase letters `A-Z`, numbers `0-9` and special characters hyphens `-` and underscores `_`

## Asset Naming

Asset names are divided into multiple name components. Name components are written using Pascal case and are separated by underscores `_` (**NOT spaces**).

The **basic asset naming format**:

<span class="convention">
<span style="color: #d77c79;">[TypePrefix]</span><!--
-->_<!--
--><span style="color: #e6a472;">[AssetName]</span><!--
-->
</span>

The format can be extended for **assets that have variations**:

<span class="convention">
<span style="color: #d77c79;">[TypePrefix]</span><!--
-->_<!--
--><span style="color: #e6a472;">[AssetName]</span><!--
-->_<!--
--><span style="color: #c2c77b;">[OptionalVariant]</span><!--
-->_<!--
--><span style="color: #92b2ca;">[OptionalNumber]</span>
</span>

Wall and floor pieces may have their dimensions appended as part of their name.

<span class="convention">
<span style="color: #d77c79;">[TypePrefix]</span><!--
-->_<!--
--><span style="color: #e6a472;">[AssetName]</span><!--
-->_<!--
--><span style="color: #c2c77b;">[OptionalVariant]</span><!--
-->_<!--
--><span style="color: #92b2ca;">[OptionalNumber]</span><!--
-->_<!--
--><span style="color: #6fb2ba;">[OptionalDimensions]</span>
</span>

**Texture maps** should also include a type suffix which describes what type of content the texture contains.

<span class="convention">
<span style="color: #d77c79;">[TypePrefix]</span><!--
-->_<!--
--><span style="color: #e6a472;">[AssetName]</span><!--
-->_<!--
--><span style="color: #c0a7c7;">[TextureTypeSuffix]</span>
</span>

And finally the combined texture format for asset variations:

<span class="convention">
<span style="color: #d77c79;">[TypePrefix]</span><!--
-->_<!--
--><span style="color: #e6a472;">[AssetName]</span><!--
-->_<!--
--><span style="color: #c2c77b;">[OptionalVariant]</span><!--
-->_<!--
--><span style="color: #92b2ca;">[OptionalNumber]</span><!--
-->_<!--
--><span style="color: #c0a7c7;">[TextureTypeSuffix]</span>
</span>

Naming components:

- <span class="naming" style="color: #d77c79;">TypePrefix</span> Identifier for the asset type
    - Refer to the table below for types of assets and their prefixes
- <span class="naming" style="color: #e6a472;">AssetName</span> Descriptive name for the asset
- <span class="naming" style="color: #c2c77b;">OptionalVariant</span> Optional string that describes a variation of the base asset
- <span class="naming" style="color: #92b2ca;">OptionalNumber</span> Optional variation number for an asset variant, starting at `01`
    - Can be used in addition to the variant string if there's multiple versions of an asset variant
    - If it's a single digit number, it should be zero padded to two characters e.g. `01`, `09`, `15`
- <span class="naming" style="color: #6fb2ba;">[OptionalDimensions]</span> Optional wall or floor size/dimensions in centimeters
    - Formatted as `WIDTHxHEIGHT`. e.g. `200x200`, `400x200`
- <span class="naming" style="color: #c0a7c7;">[TextureTypeSuffix]</span> Identifier for the texture type
    - Refer to the table below for texture map types and their suffixes

### Asset Types

Valid asset type prefixes:

| Prefix | Asset type               |
|--------|--------------------------|
| `M`    | Material                 |
| `SM`   | Static mesh              |
| `SK`   | Skeletal mesh            |
| `T`    | Texture                  |
| `BP`   | Blueprint                |
| `PS`   | Particle system          |
| `PP`   | Post processing material |

### Texture Types

Valid texture type suffixes:

| Suffix | Texture map type                        |
|--------|-----------------------------------------|
| `Color`  | Color (also known as albedo or diffuse) |
| `Normal` | Normal map                              |
| `Rough`  | Roughness                               |
| `Metal`  | Metallic                                |
| `Emit`   | Emissive                                |
| `AO`     | Ambient occlusion                       |

### Examples

Basic props:

```
Rock_Small_01                   (asset folder)
    SM_Rock_Small_01            (static mesh model)
    M_Rock_Small_01             (material)
    T_Rock_Small_01_Color       (color texture)
    T_Rock_Small_01_Rough       (roughness texture)
    T_Rock_Small_01_Metal       (metallic texture)

Rock_Small_02                   (asset folder)
    SM_Rock_Small_02(model)     (static mesh model)
    M_Rock_Small_02             (material)
    T_Rock_Small_02_Color       (color texture)
    T_Rock_Small_02_Rough       (roughness texture)
    T_Rock_Small_02_Metal       (metallic texture)

RockStack_Large                 (asset folder)
    SM_RockStack_Large          (static mesh model)
    M_SM_RockStack_Large        (material)
    T_SM_RockStack_Large_Color  (color texture)
    T_SM_RockStack_Large_Rough  (roughness texture)
    T_SM_RockStack_Large_Metal  (metallic texture)
```

Wall/floor pieces:
```
SM_Wall_400x200
SM_Wall_Corner_200x200
SM_Floor_Tiles_100x100
```

Common shared assets:

```
M_RockSurface           (general purpose material)
PP_BloomFilter          (post-processing material)
BP_PlayerController     (blueprint)
PS_DenseSmoke           (particle system)
```
