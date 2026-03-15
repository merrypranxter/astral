# assets/

Static visual art assets — textures, reference images, colour palettes, and
other media files consumed by shaders and AI art apps.

## Sub-directories

| Directory    | Contents |
|--------------|----------|
| `textures/`  | Tileable / repeating texture images (PNG, EXR, HDR) |
| `images/`    | General artwork, concept art, and finished pieces |
| `references/`| Reference photos and mood-board images |
| `palettes/`  | Colour palette files (ASE, GPL, JSON) |

## Supported formats

- **Raster**: PNG, JPEG, TIFF, EXR, HDR
- **Palettes**: `.ase` (Adobe Swatch Exchange), `.gpl` (GIMP palette), `.json`
- **Vector**: SVG

## Naming conventions

```
<subject>_<variant>_<resolution>.<ext>
```

Examples:
- `nebula_dark_2048.png`
- `starfield_blue_4k.exr`
- `victorian_pattern_tile_512.png`

## How apps should consume these files

See `../manifest.json` for a full catalogue with metadata (dimensions,
colour-space, tags, licence).
