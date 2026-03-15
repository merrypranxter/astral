# scripts/

Utility scripts for processing, converting, and managing art assets.

## Sub-directories

| Directory     | Contents |
|---------------|----------|
| `processing/` | Scripts that transform or enhance existing assets (resize, colour-grade, batch rename) |
| `conversion/` | Format-conversion helpers (EXR → PNG, palette extraction, etc.) |

## Style guide

- Scripts should be self-contained and runnable from the repo root.
- Each script must begin with a brief docstring / comment block explaining
  its purpose, inputs, outputs, and any dependencies.
- Prefer Python 3.10+ for portability.

## Running a script

```bash
python scripts/processing/my_script.py --input assets/images/ --output assets/images/processed/
```
