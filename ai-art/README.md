# ai-art/

Files related to AI-assisted and generative visual art.

## Sub-directories

| Directory  | Contents |
|------------|----------|
| `prompts/` | Text prompt files (`.txt`, `.json`) used with image-generation models |
| `outputs/` | Generated images and videos produced by AI models |
| `styles/`  | Style reference images and LoRA / embedding weights |
| `models/`  | Model configuration files, checkpoints, and metadata (do **not** commit large binary weights here — use Git LFS or external storage and reference them in `manifest.json`) |

## Prompt file format

Each prompt lives in its own `.txt` or `.json` file:

```json
{
  "prompt": "ethereal Victorian séance, astral light, soft glowing orbs, detailed engraving style",
  "negative_prompt": "blurry, low quality",
  "model": "stable-diffusion-xl",
  "sampler": "DPM++ 2M Karras",
  "steps": 30,
  "cfg_scale": 7.5,
  "seed": 42,
  "tags": ["victorian", "astral", "séance"]
}
```

## Output file naming

```
<prompt-slug>_<seed>_<date>.<ext>
```

Example: `victorian_seance_42_20260315.png`
