# Rain Simulator

A miniature 3D rain scene with a pen-and-wash look.

![style](https://img.shields.io/badge/style-pen%20%26%20wash-8c7b6b) ![deps](https://img.shields.io/badge/dependencies-none-6b8e6b) ![offline](https://img.shields.io/badge/offline-single%20file-6b8e6b)

- **Real 3D, drawn with a pen-and-wash palette** — perspective projection and painter's algorithm run on a small hand-rolled Canvas 2D engine. Wobbly ink lines, translucent watercolour washes and paper grain give it the hand-painted feel, and they hold up from every angle. No WebGL, no 3D library, no image assets.
- **One self-contained file** — `index.html` is the whole app. Works offline, no CDN, no build step.
- **Interactive** — drag to orbit, scroll or pinch to zoom, click the water to drop a ripple.
- **Four themes** — transparent white, rain blue, Morandi green, Morandi pink. Switching bleeds the new colour out from the centre like a watercolour wash; the view never moves.
- **Sound** — a seamless rain loop is synthesised straight into the file (no audio files), started on first interaction as browsers require.

## Run it

Open `index.html` in any browser. That is the whole procedure.

## How it works

A hand-rolled mini 3D engine on Canvas 2D — painter's algorithm plus perspective projection. Pen strokes carry their wobble in **pre-generated local coordinates**, so lines never shimmer while you rotate the model. Rain drops choose their landing spot first and then solve backwards for their spawn point, so wind never pushes them off the square base. Theme transitions snapshot the current blend and keep painting from that state, so interrupting one mid-wash never jumps.

## Deploy

```bash
bash deploy.sh
```

Needs a GitHub token with the `repo` scope — either copy one to the clipboard first, or pass it explicitly: `GH_TOKEN=ghp_xxx bash deploy.sh`. Creates (or updates) the public repository, syncs the files and switches GitHub Pages on. Live at
`https://<your-github-username>.github.io/rain-simulator/`.
