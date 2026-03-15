# Particle Geometry Explorer - User Guide

Welcome to the **Particle Geometry Explorer**. This guide covers every feature and option available in the application.

## Table of Contents

1.  [Interface Overview](#interface-overview)
2.  [Control Panel](#control-panel)
    *   [Quick Actions](#quick-actions)
    *   [Particle System](#particle-system)
    *   [Motion & Effects](#motion--effects)
    *   [Orbital Rings](#orbital-rings)
    *   [Colors & Appearance](#colors--appearance)
    *   [Mouse Interaction](#mouse-interaction)
    *   [Gravity Wells](#gravity-wells)
    *   [Camera Controls](#camera-controls)
    *   [Presets](#presets)
    *   [Import / Export](#import--export)
    *   [Settings & Performance](#settings--performance)
3.  [Navigation & Controls](#navigation--controls)
4.  [Diagnostics & Performance](#diagnostics--performance)
5.  [Saving & Sharing](#saving--sharing)

---

## Interface Overview

The application consists of two main areas:
*   **The Viewport**: The main background where the 3D simulation renders.
*   **The Control Panel**: A floating, draggable menu on the left side containing all configuration options. You can toggle its visibility by clicking the `☰` button in the top-left corner, or by clicking `✕` on the panel header.

### Collapsible Sections

Each section in the control panel can be collapsed or expanded by clicking its title. A chevron indicator shows the current state. By default, only **Quick Actions** and **Particle System** are expanded — all other sections start collapsed to keep the workspace clean.

---

## Control Panel

### Quick Actions

Immediate control over the simulation state.

*   **Pause (Space)**: Freezes the animation. Useful for inspecting a specific frame.
*   **Random (R)**: Generates a completely random configuration. Great for discovering new visual styles.
*   **Screenshot (S)**: Instantly downloads a `.png` image of the current view.
*   **Record Video (V)**: Starts recording a video of the canvas. Click again to stop and download the `.webm` file.
    *   **Include UI in Video**: Toggle this switch to decide if the control panel should be visible in your recording.
*   **Demo Mode**: Automatically randomizes settings every few seconds.
    *   **Interval**: Set how many seconds each configuration lasts (1-5s).
    *   **Start Demo**: Begins the automatic cycle.
*   **Help & Guide**: Opens the built-in help modal with keyboard shortcuts and tips.

### Particle System

Defines the fundamental structure of the particles.

*   **Shape Type**: Determines the geometric arrangement of particles.
    *   *Geometric*: Sphere, Tetrahedron, Cube, Octahedron, Dodecahedron, Icosahedron, Torus
    *   *Sacred Geometry*: Seed of Life, Vector Equilibrium, Lotus of Life, Metatron's Cube, Flower of Life, Merkaba, 64 Star Tetrahedron, Philosopher Stone, Nested Polygons, Golden Spiral, Vesica Piscis Chain, Yin Yang Sacred
    *   *Custom*: Happy Face, Rubber Ducky, Skull & Crossbones, DNA Helix, Mobius Strip, Klein Bottle, Custom Text
*   **Sprite Type**: The image texture used for each individual particle.
    *   *Options*: Square, Circle, Star, Triangle, Diamond, Heart, Happy Face, Skull, Rubber Ducky.
*   **Text to Display**: (Visible only when Shape Type is "Custom Text") Enter the text you want to render with particles.
*   **Particle Count**: The total number of particles in the main shape (500 - 10,000). Higher numbers look denser but may affect performance.
*   **System Size**: The overall scale/radius of the main particle shape.

### Motion & Effects

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
    *   **Exclude from Random**: When checked, effect type won't change during randomization.
*   **Effect Speed**: How fast the selected effect plays.
*   **Effect Scale**: The intensity or magnitude of the effect (e.g., how far particles pulse outward).
*   **Size Pulse**: Toggles a pulsing particle size effect on or off.

### Orbital Rings

Adds secondary rings of particles orbiting the main shape.

*   **Exclude from Demo Randomization**: When checked, orbital settings won't change during demo mode.
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

### Colors & Appearance

Customize the visual style of the environment.

*   **Color Scheme**: Select a gradient palette for the particles.
    *   *Options*: Default, Fire, Ice, Forest, Sunset, Neon, Gold, Monochrome.
*   **Color Mode**: How color is mapped onto particles.
    *   *By Index*: Colors assigned by particle order (default).
    *   *By Distance*: Colors mapped by distance from center.
    *   *By Height (Y)*: Colors mapped by vertical position.
    *   *By Velocity*: Colors mapped by particle speed.
*   **Color Shift**: Rotates the hue of the selected palette, creating a rainbow offset effect.
*   **Background**: Changes the environment backdrop.
    *   *Options*: Solid Black, Gradient, Starfield, Cyberpunk Grid, Dynamic Nebula, Checkerboard Void, Chess Board.
    *   **Exclude from Random**: When checked, background won't change during randomization.
*   **Particle Glow**: Adds a glowing bloom effect to bright particles.
*   **Particle Trails**: Particles leave a fading trail behind them as they move. (Higher performance cost.)
*   **Connection Lines**: Draws thin lines between nearby particles, creating a constellation/plexus effect.

### Mouse Interaction

How the particles react to your mouse cursor.

*   **Mouse Mode**:
    *   *None*: No interaction.
    *   *Repel Particles*: Particles flee from the cursor.
    *   *Attract Particles*: Particles are pulled towards the cursor.
*   **Require Ctrl Key**: If checked, interaction only happens when you hold the `Ctrl` key. This prevents accidental disruption while rotating the camera.
*   **Force Strength**: How strongly the particles react to the mouse.

### Gravity Wells

Persistent gravitational attractors that pull particles toward fixed points in space.

*   **Enable Gravity Wells**: Toggle gravity wells on or off.
*   **Number of Wells**: How many gravity well points to create (1-3).
*   **Well Strength**: How strongly the wells pull on nearby particles.

### Camera Controls

Adjust the virtual camera that views the scene.

*   **Field of View**: The camera's field of view angle (30-120 degrees). Lower values zoom in, higher values create a wide-angle look.
*   **Auto-Orbit Camera**: When enabled, the camera automatically orbits around the particle system for a cinematic view.
*   **View Presets**: Quick buttons for Top, Side, and Front orthogonal views.
*   **Reset View (C)**: Returns the camera to its default position and orientation.

### Presets

Save and manage your particle configurations.

*   **Preset Name**: Enter a name for your preset.
*   **Save Preset**: Saves the current configuration to your browser's local storage.
*   **Manage**: Opens the preset list where you can load or delete saved presets.
*   Presets are stored in your browser's `localStorage` and persist across sessions.

### Import / Export

Share configurations with others.

*   **Export Code**: Generates a Base64-encoded string of your current settings. Opens a modal where you can copy the code.
*   **Import Code**: Opens a modal where you can paste a settings code to load someone else's configuration.
*   **Reset All Settings**: Restores all parameters to their defaults.

### Settings & Performance

System-level controls.

*   **Quality Preset**: Adjusts rendering quality.
    *   *Ultra*: Maximum quality (heavy on GPU).
    *   *High*: Recommended default.
    *   *Medium*: Balanced performance.
    *   *Low*: Fastest rendering for lower-end hardware.
*   **Show FPS**: Displays a frames-per-second counter in the top-right corner.
*   **Show Diagnostics**: Opens the full diagnostics panel (same as pressing `D`).
*   **Show Axes**: Renders X (red), Y (green), and Z (blue) axis lines through the origin for spatial reference.

---

## Navigation & Controls

### Mouse / Touch
*   **Rotate**: Left Click + Drag (or 1-finger touch).
*   **Pan**: Right Click + Drag, Shift + Drag (or 3-finger touch).
*   **Zoom**: Scroll Wheel (or 2-finger pinch). Range: 2-30 units.

### Keyboard Shortcuts
| Key | Action |
| :--- | :--- |
| **Space** | Pause / Play Animation |
| **S** | Take Screenshot |
| **R** | Randomize Settings |
| **V** | Start / Stop Video Recording |
| **C** | Reset Camera Position |
| **M** | Lock / Unlock Camera Movement |
| **W** | Trigger Shockwave |
| **D** | Toggle Diagnostics Panel |
| **F** | Toggle Fullscreen |

---

## Diagnostics & Performance

Press **D** to open the Diagnostics Panel in the top-right corner. This provides real-time technical data:

*   **Performance**: FPS, frame time (ms), render calls.
*   **Geometry**: Current shape, sprite type, active palette, particle count, orbital count, vertex count.
*   **Camera**: Position coordinates, look-at target, rotation angles, zoom level, FOV.
*   **Animation**: Play/pause status, time speed, start delay, active effect, effect speed, effect delay.
*   **System**: Background type, canvas resolution, device pixel ratio, quality preset, memory usage.

### Performance Tips

*   Lower the **Quality Preset** if FPS drops below 30.
*   Reduce **Particle Count** for the biggest performance gain.
*   Disable **Particle Trails** — they have the highest performance cost.
*   Disable **Particle Glow** and **Connection Lines** for additional headroom.

---

## Saving & Sharing

There are two ways to save and share your work:

### Presets (Local)
1.  Enter a name in the **Preset Name** field.
2.  Click **Save Preset** to store it in your browser's local storage.
3.  Click **Manage** to view, load, or delete saved presets.

### Export / Import (Shareable)
1.  Click **Export Code** to generate a Base64 string of your current configuration.
2.  Click **Copy to Clipboard** in the export modal.
3.  Share the code with others — they can paste it into the **Import Code** modal to load your exact setup.

### Screenshots & Video
*   Press **S** or click **Screenshot** to download a PNG of the current frame.
*   Press **V** or click **Record Video** to start recording. Press again to stop and download a `.webm` file.
*   Toggle **Include UI in Video** to control whether the control panel appears in recordings.
