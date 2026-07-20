# 🪩 THREEVERSE

A playful, interactive 3D toy studio built with [Three.js](https://threejs.org). One shape floats in a candy-cosmic void — grab it, spin it, morph it, re-skin it, and blow it apart.

![Three.js](https://img.shields.io/badge/Three.js-r160-a78bff) ![No build step](https://img.shields.io/badge/build-none-4fe3c1) ![Static](https://img.shields.io/badge/deploy-static-ffd166)

## What you can do

- **Drag** the object to fling it around (orbit), **scroll** to zoom
- **Morph** between 6 shapes — Blob, Knot, Gem, Donut, Capsule, Spikes
- **Sculpt** any shape into your own with live sliders — **Twist**, **Spikes**, and **Bulge** (with a reset). Sculpt persists as you switch shapes
- **Re-skin** with 5 finishes — Glossy, Metal, Glass, Matte, Neon
- **Recolor** from a 6-swatch palette
- Toggle **auto-spin**, or hit **Explode** (also the `Space` key) to burst the mesh apart
- Ambient floating debris + starfield, mouse parallax, animated vertex wobble

## Run locally

It's a single self-contained `index.html` — no build, no install. Any static server works:

```bash
# Python
python -m http.server 4199
# then open http://localhost:4199

# or Node
npx serve .
```

> Open it over `http://` (a server), not by double-clicking the file — ES modules and the import map need an HTTP origin.

## Deploy

Zero-config static deploy. From this folder:

```bash
# Vercel
vercel --prod

# Netlify
netlify deploy --prod --dir .

# GitHub Pages / Cloudflare Pages / any static host
# just upload index.html
```

Three.js is loaded from the unpkg CDN via an import map, so the only runtime dependency is a network connection.

## Tech

- **Three.js r160** — WebGLRenderer, `OrbitControls`, `RoomEnvironment` (IBL via PMREM), ACES tone mapping
- Real-time vertex displacement: every frame the mesh is rebuilt from its base vertices through a sculpt pipeline (twist → spikes → bulge → explode), so all deformations compose across any shape
- Vanilla JS + CSS, no framework, no bundler
- Respects `prefers-reduced-motion` and keyboard focus

Built for fun. 🌈
