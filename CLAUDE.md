# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Particle Geometry Explorer is a single-file web application (`particle-explorer.html`, ~4,400 lines) that creates interactive 3D particle simulations using Three.js. There is no build system, bundler, or package manager — the entire app lives in one HTML file with inline CSS, HTML, and JavaScript.

## Running Locally

Open `particle-explorer.html` directly in a browser. No server or build step required.

Three.js r128 is loaded from CDN (`cdnjs.cloudflare.com`), so an internet connection is needed on first load.

## Architecture

The single HTML file is organized into three major sections:

| Section | Lines | Description |
|---------|-------|-------------|
| CSS | ~7–758 | Glassmorphic UI styling, modals, diagnostics panel |
| HTML | ~759–1,422 | Control panel, modals (export/import/help), diagnostics overlay |
| JavaScript | ~1,424–4,437 | All application logic (~3,000 lines) |

### JavaScript Subsystems

**State management**: A central `params` object (~line 1,460) holds all configurable settings (particle count, shape, colors, effects, camera, etc.). Global variables track UI state (pause, drag, recording). `updateAllControls()` syncs the `params` object to HTML inputs.

**Key subsystems by approximate line range:**

- **Scene setup** (~1,424–1,505): Three.js scene, camera, renderer initialization
- **Color palettes** (~1,507–1,517): 8 predefined HSL-based palettes (fire, ice, forest, neon, etc.)
- **Preset management** (~1,520–1,690): Save/load/export/import via localStorage and Base64 encoding
- **Shape generation** (`generateShapeParticles`, ~1,893–2,528): 25+ shapes including geometric primitives, sacred geometry (seed of life, merkaba, metatron's cube, etc.), and custom shapes (DNA helix, text, skull)
- **Sprite generation** (`generateSprite`, ~2,529–2,687): Canvas-based 2D sprite rendering (circle, star, heart, happyface, etc.)
- **Particle system creation** (`createParticleSystem`, ~2,689–2,799): Builds combined BufferGeometry for main shape + orbital ring particles, applies colors/sizes/materials
- **Orbital system** (~2,802–2,856): Up to 5 independent orbital rings with configurable orientation (XY/XZ/YZ) and tilt
- **Connection lines** (~2,857–2,905): Dynamic lines drawn between nearby particles each frame
- **Effects engine** (`applyEffect`, ~2,907–2,969): Pulse, wave, spiral, breathe, explode — modifies particle positions per frame
- **Mouse forces** (`applyMouseForce`, ~2,972–2,998): Attract/repel with velocity damping
- **Background system** (`updateBackground`, ~3,001–3,189): 6 types — solid, starfield, cyberpunk grid, nebula, checkerboard, chessboard
- **Animation loop** (`animate`, ~3,272–3,374): requestAnimationFrame loop handling rotation, orbital animation, effects, camera interpolation, rendering
- **Input handling** (~3,376–3,570): Mouse (rotate/pan), keyboard shortcuts, touch gestures (1/2/3-finger)
- **Video recording** (~3,683–3,741): MediaRecorder API capturing canvas stream
- **Demo mode** (~4,309–4,371): Interval-based auto-randomization of settings
- **Diagnostics** (~4,047–4,098): Real-time FPS, particle count, camera state, memory usage

### How Changes Flow

Modifying any UI control updates `params` → triggers `createParticleSystem()` to rebuild geometry → the `animate()` loop renders the updated scene each frame. Effects and forces are applied per-frame by modifying BufferGeometry position attributes directly.

### Important Patterns

- All particle positions are stored in a `Float32Array` via `BufferGeometry` — updates require setting `geometry.attributes.position.needsUpdate = true`
- Orbital particles are appended after main shape particles in the same geometry buffer; orbital indices start at `mainParticleCount`
- Sprites are generated as canvas textures, not image files
- The control panel is draggable via custom mouse/touch handlers on `#drag-handle`
