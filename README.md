# 3D Face Mesh Viewer

An interactive browser-based tool for separating and repositioning facial features on a 3D human head model. No server required — open `head_separator.html` directly in any modern browser.

## Features

### Facial Feature Separation
Individual control over four facial regions, each defined by a weighted sphere that smoothly selects nearby vertices:

- **Eyes** — combined left/right region with a symmetric **Spread** slider that moves both eyes symmetrically away from or toward the midline. Y and Z sliders move both eyes together.
- **Nose** — Y and Z sliders only (locked to midline).
- **Mouth** — Y and Z sliders only (locked to midline).

Each feature card also exposes **Region center & radius** inputs so you can fine-tune exactly which vertices belong to each region, then hit **Apply** to recompute live.

### Viewport Controls
- **Orbit** — left-click drag
- **Pan** — right-click drag
- **Zoom** — scroll wheel
- **Move head** — double-click the mesh to enter Move Mode, then drag to reposition the head on the camera plane. Press **Escape** or double-click again to exit.

### Camera
- **Reset Camera** — snaps back to the default view
- **Orthographic / Perspective** toggle — switches projection while preserving the current view angle

### Display
- **Show region highlights** — toggles vertex color coding (red = eyes, green = nose, yellow = mouth). Vertices are always visible as a point cloud regardless of this setting.
- **Show mesh** — toggles the solid mesh surface
- **Opacity** — controls mesh transparency from 0 (fully transparent, showing only the point cloud) to 1 (fully opaque)

### Info Panel
Live readout of world-space positions for the head and each facial feature, updated every frame.

### Origin Marker
A white sphere at (0, 0, 0) with R/G/B axis lines (X = red, Y = green, Z = blue) rendered on top of the scene for spatial reference.

## Usage

1. Open `head_separator.html` in a modern browser (Chrome or Edge recommended).
2. Wait for the model to finish loading (~1 second).
3. Use the **Display** section to adjust mesh opacity so the point cloud is visible underneath.
4. Drag the Y/Z sliders on each feature card to separate facial features.
5. Use the **Spread** slider on the Eyes card to widen or narrow eye spacing.
6. Double-click the head to reposition it in space.

## Files

| File | Description |
|------|-------------|
| `head_separator.html` | Self-contained viewer — GLB model is embedded as base64, no server needed |
| `human_head.glb` | Source GLB model |

## Dependencies

Loaded from CDN at runtime (internet connection required):
- [Three.js r158](https://threejs.org/) — 3D rendering
- GLTFLoader, OrbitControls (Three.js addons)

## Model Attribution

"Human head" by [ADAMA](https://sketchfab.com/tnshwsh) is licensed under [Creative Commons Attribution 4.0 (CC-BY-4.0)](http://creativecommons.org/licenses/by/4.0/).  
Source: https://sketchfab.com/3d-models/human-head-41319c63c3d34f7ea6b04bf2b8c092f1
