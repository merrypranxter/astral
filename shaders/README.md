# shaders/

GLSL, HLSL, and other shader source files used by visual art and generative apps.

## Sub-directories

| Directory  | Contents |
|------------|----------|
| `vertex/`  | Vertex shaders (`.vert`, `.vs`, `.glsl`) |
| `fragment/`| Fragment / pixel shaders (`.frag`, `.fs`, `.glsl`) |
| `compute/` | Compute shaders (`.comp`, `.glsl`) |
| `examples/`| Self-contained example shader programs with comments |

## Naming conventions

```
<effect-name>_<version>.<ext>
```

Examples:
- `nebula_v1.frag`
- `starfield_v2.vert`
- `voronoi_noise_v1.comp`

## How apps should consume these files

Apps can enumerate shaders by reading `../manifest.json`, which lists every
shader file with its type, uniforms, and a short description.
