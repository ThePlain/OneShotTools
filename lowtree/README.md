# Lowtree

Procedural tree generator that runs in the browser, in the spirit of SpeedTree.
It is a single `index.html`: WebGL 2, no build step, no dependencies.

## Features

- **Branching:** trunk with root flare, lean, gnarl and forks, plus up to three recursive branch levels (count, angle, length, thickness, gravity, gnarl, whorls, flattening) and 8 crown shapes.
- **Leaves:** procedural oak, maple, birch, willow, cherry blossom and spruce-needle cards, with a season slider (spring to leaf drop).
- **Bark:** six tileable procedural bark textures with normal maps, tint and moss.
- **Rendering:** sun shadows, canopy ambient occlusion, wind with gusts and leaf flutter, wireframe view.
- **Low-poly branch cards:** real 3D branches of the current tree are baked into an alpha-clip atlas (4, 9 or 16 variants, colour + alpha + normal map) and placed as crossed cards.
- **Export:** a .zip with GLB, OBJ/MTL, textures or the baked atlas, and the settings JSON. Units are metres, Y up.

### LOD levels (English oak preset)

| LOD | Foliage | Triangles |
|-----|---------|-----------|
| LOD0 | every leaf | ~101,000 |
| LOD1 | cards replace level 3 twigs | ~6,900 |
| LOD2 | cards replace level 2 branches | ~1,500 |
| LOD3 | cards replace level 1 limbs | ~250 |

The branch skeleton is identical at every LOD.

## Run locally

Open `index.html` in a recent Chrome, Edge, Firefox or Safari, or serve the folder:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Publish with GitHub Pages

1. Push this folder to a GitHub repository (for example `lowtree`).
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/lowtree/`.

`.nojekyll` tells GitHub Pages to serve the files as they are.

## Controls

- Drag to orbit, right-drag or Shift-drag to pan, scroll or pinch to zoom.
- `F` frames the tree, `R` picks a new seed, `L` switches between full leaves and branch cards.
