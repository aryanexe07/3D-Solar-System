# Solar System Explorer

Interactive 3D solar system running in a single HTML file. Built using Three.js with procedural textures — no external image files, no build tools.

This was an AI-assisted project. I used Claude to generate the code, but the main work was writing detailed, structured prompts to get useful output. Vague prompts gave garbage results. Breaking the problem down precisely — geometry, materials, animation, camera controls, UI — gave something actually worth keeping.

---

## Features

### Visuals
- All 8 planets with unique procedurally generated textures (canvas-based, no images)
- Sun with layered corona glow and pulsing animation
- Saturn's multi-layer ring system with tilt and transparency
- Earth has a separate cloud layer that rotates independently
- Jupiter has animated horizontal band stripes and a Great Red Spot
- Atmospheric glow on Earth, Venus, and Neptune
- Asteroid belt between Mars and Jupiter (1000+ particles)
- Milky Way skybox — procedurally drawn galaxy with nebula clouds, dust lanes, and 15,000+ stars. Follows the camera so it always feels like a real background

### Solar System
- All major moons included and orbiting their parent planets
- Each planet has its own orbital speed based on real relative periods
- Each planet rotates on its own axis at its own speed
- Uranus has its correct extreme axial tilt (~98°)
- Visible orbit path lines for all planets

### Controls

| Input | Action |
|-------|--------|
| `W / ↑` | Zoom in |
| `S / ↓` | Zoom out |
| `A / ←` | Orbit left |
| `D / →` | Orbit right |
| `Q / E` | Rotate up / down |
| `R` | Reset camera |
| `O` | Toggle orbit lines |
| Mouse drag | Rotate view |
| Scroll | Zoom |

### Planet Info
- Click any planet or the sun to focus the camera on it
- Info panel slides in with real scientific facts and key stats (diameter, temperature, moons, atmosphere, etc.)
- Press `Escape` or click ✕ to dismiss

### UI
- Speed slider (0.1× – 5×)
- Planet name labels floating in 3D space, fade with distance
- Toggle buttons for orbits and labels

---

## Stack

- Three.js r128
- Vanilla JS + HTML Canvas for all textures
- Plain CSS for UI
- Single `solarsystem.html` — open it and it works

---

## Prompt Engineering

The code was AI-generated but required a lot of iteration on the prompts to get right. A few things that actually made a difference:

- Using tables in the prompt to define planet data (size, color, orbit speed, moons) gave consistent, accurate output
- Describing effects in rendering terms (`additive blending`, `BackSide material`, `CanvasTexture`) instead of just saying "make it glow" worked much better
- Splitting complex features into separate focused prompts — the Milky Way background was done as its own prompt after the base was working
- Specifying code structure up front (sun factory, planet factory, animation loop, input handler) kept the output organized

---

## Usage

```bash
# Just open the file
open solarsystem.html

# Or serve locally
npx serve .
```
