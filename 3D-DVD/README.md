# 3D DVD Screensaver

Classic DVD screensaver with bouncing 3D objects. Built with Three.js and the Chatooly Tool Framework.

## Features

### Core Mechanics
- **Object Source**: Choose from built-in primitives (Cube, Sphere, Torus, Cone, Cylinder) or upload custom GLB models
- **Orthographic Bounce**: Objects bounce off canvas edges in 2D (X/Y)
- **Multiple Objects**: Add multiple bouncing objects

### Bounce Effects
- **Speed Increase**: Objects speed up on each bounce (with configurable max cap)
- **Split/Multiply**: Objects split into two on hit (with configurable max limit)
- **Rotation on Hit**: Objects rotate toward hit direction (snap or smooth lerp)

### Trail System
- **Ghost Copies**: Fading trail copies behind objects
  - Configurable length (1-50 copies)
  - Opacity and scale fade controls
- **Motion Blur**: Directional stretch effect based on velocity
- **Trail Inheritance**: Split children can inherit or start fresh

### Object Behavior
- **Facing Modes**: Camera, Movement direction, Fixed angle, Random
- **Smooth Rotation**: Optional lerp for facing transitions
- **Spin & Tumble**: Independent rotation while moving

### Materials
- Solid color
- Gradient (radial/linear with 3 color stops)
- Shader modes: Flat, Reflective, Toon
- Light and rim controls

## Usage

1. Run a local server:
   ```bash
   npm start
   ```

2. Open http://localhost:8080 in your browser

3. Use the controls panel to customize the screensaver

## Development

- `index.html` - Main HTML with Chatooly controls
- `js/main.js` - Core Three.js logic and classes
- `js/ui.js` - UI control handlers
- `js/matcap-generator.js` - Gradient texture generation
- `js/chatooly-config.js` - Tool metadata
- `js/tool-ipc.js` - Hot-reload support

## License

MIT
