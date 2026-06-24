# 🌸 Bloom

An interactive AR web experience that lets you grow a glowing tree and bloom flowers using your hands — no installation needed, runs entirely in the browser.

**[→ Live Demo](https://yourusername.github.io/bloom)**

![bloom preview](preview.gif)

---

## How it works

| Hand | Gesture | Effect |
|------|---------|--------|
| ✋ Left | Pinch open (thumb ↔ index) | Tree grows taller and branches multiply |
| ✋ Left | Pinch closed | Tree shrinks back |
| 🤚 Right | Pinch open | Lily flowers bloom at branch tips |
| 🤚 Right | Pinch closed | Flowers fade |

---

## Built with

- **MediaPipe Hands** — real-time hand landmark detection (21 points per hand)
- **HTML5 Canvas** — two-layer rendering (hand skeleton + tree)
- **Vanilla JavaScript** — recursive branch generation, no frameworks
- **CSS** — mirrored webcam overlay

---

## Technical highlights

- **Recursive tree generation** — one trunk splits into 2 branches per level, up to 6 levels deep (64 tips at full growth)
- **Two-canvas architecture** — hand tracking canvas is CSS-mirrored to match webcam, tree canvas is independent
- **Real-time pinch detection** — Euclidean distance between thumb (landmark 4) and index finger (landmark 8) mapped to growth/bloom values
- **Smooth interpolation** — lerp on all values so growth feels organic, not jumpy
- **Glowing branches** — `shadowBlur` + layered strokes, color shifts from white-gold at trunk to pink-magenta at tips
- **Lily flower rendering** — ellipse petals with linear gradients, radial stamen glow, per-petal vein lines

---

## Run locally

No build step needed — just open the file:

```bash
git clone https://github.com/yourusername/bloom.git
cd bloom
# open index.html in Chrome
```

> ⚠️ Requires Chrome (for MediaPipe camera access). Must be served over HTTPS or localhost.

---

## What I learned

- Hand landmark tracking with MediaPipe in the browser
- Recursive algorithms for procedural tree generation
- Canvas layering and coordinate system management
- Mapping real-world gesture input to visual parameters in real time

---

## Future ideas

- [ ] Add particle effects when flowers bloom
- [ ] Season modes (cherry blossom, autumn, snow)
- [ ] Record and export as a video
- [ ] Mobile touch fallback

---

*Made by [Afreen](https://github.com/afreenanz)*
