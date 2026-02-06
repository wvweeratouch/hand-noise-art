# Hand Noise Art

Interactive noise art combining webcam hand tracking, microphone audio analysis, and procedural noise — all in a single HTML file.

## How to Run

1. Open `index.html` in Chrome or Firefox
2. Click **Begin**
3. Allow camera + microphone permissions
4. Move your hand in front of the webcam — particles and geometry react
5. Make noise or play music — visuals pulse with frequency

## Gestures

| Gesture | Effect |
|---------|--------|
| Open palm | Particles spread outward |
| Fist | Particles compress inward |
| Pinch (thumb + index) | Burst of particles |
| Wave (fast hand movement) | Bloom ripple effect |
| Two hands | Mirror/symmetry mode |

## Tech Stack

- **Three.js** — WebGL 3D rendering + bloom post-processing
- **MediaPipe Hands** — 21-point hand landmark tracking from webcam
- **Web Audio API** — Real-time microphone frequency analysis
- **GLSL Simplex Noise** — GPU procedural generation (fBm, simplex)

## Visual Layers

1. **Particle cloud** — 10k particles that swarm around hand position, sized by bass
2. **Deformable mesh** — Icosphere displaced by fractal noise, rotation follows hand
3. **Background shader** — Flowing noise field, colors shift with audio spectrum

## Math (from KlakMath)

- Simplex noise → GLSL `snoise()`
- Fractal Brownian motion → GLSL `fbm()`
- ExpTween (exponential interpolation) → JS `expTween()`
- CdsTween (critically damped spring) → JS `CdsTween`
- XXHash (deterministic seeding) → JS `xxhash()`

## Requirements

- Modern browser with WebGL2 support
- Webcam (for hand tracking)
- Microphone (for audio reactivity)
- Works on mobile with front camera

---

*Created by Bri-yarni (บริ-ญาณิ์) — a Light Oracle*
