# astral

> A visual art resource repository — AI-generated art, shaders, and assets for
> generative and theosophy-inspired creative projects.

---

## Repository structure

```
astral/
├── manifest.json          ← machine-readable catalogue (used by apps)
├── .gitignore
│
├── shaders/               ← GLSL / HLSL shader source files
│   ├── vertex/            vertex shaders (.vert, .vs, .glsl)
│   ├── fragment/          fragment / pixel shaders (.frag, .fs, .glsl)
│   ├── compute/           compute shaders (.comp, .glsl)
│   └── examples/          annotated example programs
│
├── assets/                ← static visual art assets
│   ├── textures/          tileable textures (PNG, EXR, HDR)
│   ├── images/            finished artwork and concept pieces
│   ├── references/        reference photos and mood-board images
│   └── palettes/          colour palettes (ASE, GPL, JSON)
│
├── ai-art/                ← AI-assisted generative art
│   ├── prompts/           text prompts for image-generation models
│   ├── outputs/           AI-generated images and videos
│   ├── styles/            style reference images and LoRA weights
│   └── models/            model configs and metadata
│
├── scripts/               ← utility scripts
│   ├── processing/        asset transformation (resize, colour-grade, …)
│   └── conversion/        format-conversion helpers
│
└── docs/                  ← project documentation
```

Each directory contains its own `README.md` with naming conventions, supported
formats, and usage notes.

---

## How apps discover files

Every file added to the repo should be registered in **`manifest.json`** at the
root. Apps load this single JSON file to discover available shaders, assets, and
prompts without needing to walk the directory tree.

```json
{
  "version": "1.0.0",
  "files": [
    {
      "path": "shaders/fragment/nebula_v1.frag",
      "type": "shader/fragment",
      "description": "Procedural nebula with colour cycling",
      "uniforms": ["iTime", "iResolution", "uColour"],
      "tags": ["nebula", "procedural", "space"]
    },
    {
      "path": "assets/textures/victorian_pattern_tile_512.png",
      "type": "asset/texture",
      "resolution": [512, 512],
      "format": "PNG",
      "tags": ["victorian", "pattern", "tile"]
    }
  ]
}
```

Add a new entry to `files[]` whenever you upload a new file.

---

## Naming conventions

| Category | Pattern | Example |
|----------|---------|---------|
| Shaders  | `<effect>_v<N>.<ext>` | `starfield_v2.frag` |
| Textures | `<subject>_<variant>_<res>.<ext>` | `nebula_dark_2048.png` |
| AI outputs | `<prompt-slug>_<seed>_<date>.<ext>` | `victorian_seance_42_20260315.png` |
| Prompts  | `<subject>_<style>.json` | `seance_engraving.json` |

---

## Large files

Do **not** commit large binary model weights (`.ckpt`, `.safetensors`, `.pt`
etc.) directly. Use Git LFS, or store them externally and reference them via a
URL in `manifest.json`.
