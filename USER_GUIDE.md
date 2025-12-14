# Particle Geometry Explorer - User Guide

Welcome to the **Particle Geometry Explorer**! This comprehensive guide will help you understand every feature and option available in the application, allowing you to create stunning 3D particle visualizations.

## Table of Contents

1.  [Interface Overview](#interface-overview)
2.  [Control Panel](#control-panel)
    *   [Quick Actions](#quick-actions)
    *   [Particle System](#particle-system)
    *   [Motion & Effects](#motion--effects)
    *   [Orbital Rings](#orbital-rings)
    *   [Colors & Appearance](#colors--appearance)
    *   [Mouse Interaction](#mouse-interaction)
3.  [Navigation & Controls](#navigation--controls)
4.  [Diagnostics & Performance](#diagnostics--performance)
5.  [Saving & Sharing](#saving--sharing)

---

## Interface Overview

The application consists of two main areas:
*   **The Viewport**: The main background where the 3D simulation renders.
*   **The Control Panel**: A floating menu on the left side containing all configuration options. You can toggle this panel's visibility by clicking the `☰` button in the top-left corner.

---

## Control Panel

The control panel is divided into several sections, each managing a specific aspect of the simulation.

### ⚡ Quick Actions

These buttons provide immediate control over the simulation state.

*   **Pause (Space)**: Freezes the animation. Useful for inspecting a specific frame.
*   **Random (R)**: Generates a completely random configuration. Great for discovering new visual styles.
*   **Screenshot (S)**: Instantly downloads a `.png` image of the current view.
*   **Record Video (V)**: Starts recording a video of the canvas. Click again to stop and download the `.webm` file.
    *   **Include UI in Video**: Toggle this switch to decide if the control panel should be visible in your recording.
*   **Demo Mode**: Automatically randomizes settings every few seconds.
    *   **Interval**: Set how many seconds each configuration lasts (1-5s).
    *   **Start Demo**: Begins the automatic cycle.

### ⬡ Particle System

Defines the fundamental structure of the particles.

*   **Shape Type**: Determines the geometric arrangement of particles.
    *   *Options*: Sphere, Tetrahedron, Cube, Octahedron, Dodecahedron, Icosahedron, Torus, Happy Face, Rubber Ducky, Skull, DNA Helix, Custom Text.
*   **Sprite Type**: The image texture used for each individual particle.
    *   *Options*: Square, Circle, Star, Triangle, Diamond, Heart, Happy Face, Skull, Rubber Ducky.
*   **Text to Display**: (Visible only when Shape Type is "Custom Text") Enter the text you want to render with particles.
*   **Particle Count**: The total number of particles in the main shape (500 - 10,000). Higher numbers look denser but may affect performance.
*   **System Size**: The overall scale/radius of the main particle shape.

### ✨ Motion & Effects

Controls how the system moves and behaves over time.

*   **Time Speed**: The global speed multiplier for the entire simulation. Set to 0 to freeze time.
*   **Start Delay**: Adds a delay before the initial animation sequence begins.
*   **Effect Delay**: The time interval between repeating effects.
*   **Rotation Speed**: How fast the entire system rotates around its axis.
*   **Effect Type**: Applies a dynamic transformation to the particles.
    *   *None*: No effect.
    *   *Pulse*: Particles expand and contract rhythmically.
    *   *Wave*: A sine wave ripple passes through the particles.
    *   *Spiral*: Particles twist in a spiral pattern.
    *   *Breathe*: A slow, organic expansion and contraction.
    *   *Explode*: Particles scatter outward and return.
*   **Effect Speed**: How fast the selected effect plays.
*   **Effect Scale**: The intensity or magnitude of the effect (e.g., how far particles pulse outward).

### 🌀 Orbital Rings

Adds secondary rings of particles orbiting the main shape.

*   **Presets**: Quick buttons to set up common orbital configurations:
    *   *Atom*: Small, fast-moving rings like electrons.
    *   *Solar*: Flat, wide rings like a solar system.
    *   *Galaxy*: A dense, spiral-like galaxy structure.
*   **Number of Rings**: How many separate orbital rings to create (0-5).
*   **Particles per Ring**: The density of each ring.
*   **Ring Size**: The radius of the orbital rings relative to the center.
*   **Orbital Speed**: How fast the particles travel along their orbit.
*   **Orientation**: The geometric plane of the rings.
    *   *XY / XZ / YZ*: Fixed geometric planes.
    *   *Random*: Each ring gets a random tilt.
    *   *Gyroscope*: Rings are evenly distributed on all axes.
*   **Ring Spacing**: The distance between multiple rings.
*   **Tilt Angle**: Manually tilt the rings (0-90 degrees).
*   **Independent Speeds**: If enabled, each ring will move at a slightly different speed for a more natural look.

### 🎨 Colors & Appearance

Customize the visual style of the environment.

*   **Color Scheme**: Select a gradient palette for the particles (Default, Fire, Ice, Forest, Sunset, Neon, Gold, Monochrome).
*   **Color Shift**: Rotates the hue of the selected palette over time, creating a rainbow effect.
*   **Background**: Changes the environment backdrop.
    *   *Options*: Solid Black, Gradient, Starfield, Cyberpunk Grid, Nebula, Checkerboard, Chess Board.
*   **Particle Glow**: Adds a glowing "bloom" effect to bright particles.
*   **Particle Trails**: Particles leave a fading trail behind them as they move. (High performance cost).
*   **Connection Lines**: Draws thin lines between nearby particles, creating a "constellation" or "plexus" effect.

### 🖱️ Mouse Interaction

How the particles react to your mouse cursor.

*   **Mouse Mode**:
    *   *None*: No interaction.
    *   *Repel*: Particles flee from the cursor.
    *   *Attract*: Particles are pulled towards the cursor.
*   **Require Ctrl Key**: If checked, interaction only happens when you hold the `Ctrl` key. This prevents accidental disruption while rotating the camera.
*   **Force Strength**: How strongly the particles react to the mouse.

---

## Navigation & Controls

### Mouse / Touch
*   **Rotate**: Left Click + Drag (or 1-finger touch move).
*   **Pan**: Right Click + Drag (or 3-finger touch move).
*   **Zoom**: Scroll Wheel (or 2-finger pinch).

### Keyboard Shortcuts
| Key | Action |
| :--- | :--- |
| **Space** | Pause / Play Animation |
| **S** | Take Screenshot |
| **R** | Randomize Settings |
| **C** | Reset Camera Position |
| **M** | Lock / Unlock Camera Movement |
| **D** | Toggle Diagnostics Panel |
| **F** | Toggle Fullscreen |

---

## Diagnostics & Performance

Press **D** to open the Diagnostics Panel in the top-right corner. This provides real-time technical data:

*   **FPS**: Frames Per Second. 60 is ideal. If this drops, try reducing *Particle Count* or turning off *Trails*.
*   **Frame Time**: How long it takes to render one frame (in milliseconds).
*   **Render Calls**: Number of draw calls sent to the GPU.
*   **Geometry**: Stats on the current shape, vertex count, and active particles.
*   **Camera**: Current coordinates and zoom level.

---

## Saving & Sharing

You can save your exact configuration to share with others or load later.

1.  **Export**: Click the "Export" button (if available) or use the internal logic to generate a JSON string of your settings.
2.  **Import**: Paste a settings JSON string to instantly load that configuration.

*(Note: In the current version, use the Screenshot feature to save visual results!)*
