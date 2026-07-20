<div align="center">

# 🪩 THREEVERSE

**A playful interactive 3D toy studio.**
One shape, floating in space, waiting for you to break it.

[**▶ Play with it live**](https://threeverse-eta.vercel.app)

![Three.js](https://img.shields.io/badge/Three.js-r160-a78bff?style=flat-square) ![No build step](https://img.shields.io/badge/build-none-4fe3c1?style=flat-square) ![Static](https://img.shields.io/badge/deploy-static-ffd166?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-ff6b6b?style=flat-square)

</div>

---

Drag it, spin it, sculpt it into something that's never existed before, then blow it apart. No login, no loading spinner longer than a heartbeat, no explanation needed — just a shape in a candy-cosmic void and a dock full of toys.

## Controls

| Action | How |
|---|---|
| Orbit the object | Click + drag |
| Zoom | Scroll |
| Change shape | **Shape** chips — Blob, Knot, Gem, Donut, Capsule, Spikes |
| Sculpt it into your own form | **Sculpt** sliders — Twist, Spikes, Bulge (composes with any shape, persists across switches) |
| Change material | **Finish** chips — Glossy, Metal, Glass, Matte, Neon |
| Change color | **Color** swatches |
| Auto-rotate | **Auto-spin** toggle |
| Burst it apart | **Explode** button, or press `Space` |

Everything is additive and reversible — flip between a chrome torus knot mid-twist and a matte gold blob mid-explosion without ever hitting a wall.

## Under the hood

- **Three.js r160** — `WebGLRenderer`, `OrbitControls`, `RoomEnvironment` for image-based lighting (via PMREM), ACES filmic tone mapping
- **One deformation pipeline, every shape**: each frame, the mesh is rebuilt from its stored base vertices through `twist → spikes → bulge → explode`, so sculpting, material, and the explode burst all compose regardless of which primitive is active
- Ambient floating debris, a starfield, mouse-driven parallax, a gentle idle wobble
- Zero framework, zero bundler — vanilla JS and CSS in a single `index.html`
- Respects `prefers-reduced-motion` and full keyboard focus

## Run it locally

No build, no install — just a static file. Any local server works:

```bash
# Python
python -m http.server 4199
# → http://localhost:4199

# or Node
npx serve .
```

> Open it through a server, not by double-clicking the file. ES modules and the import map both require an `http://` origin.

## Deploy it yourself

Zero-config, static, one file:

```bash
vercel --prod                       # Vercel
netlify deploy --prod --dir .       # Netlify
# GitHub Pages / Cloudflare Pages / any static host: upload index.html
```

Three.js loads at runtime from the unpkg CDN via an import map — the only dependency is a network connection.

## License

MIT — take it apart, remix it, ship your own version.

<div align="center">

Built for fun. 🌈

</div>
