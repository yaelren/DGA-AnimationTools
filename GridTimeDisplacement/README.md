# Grid Time Displacement

A creative animation tool that creates time displacement effects on uploaded videos using customizable grids. Each cell in the grid plays the same video portion but with different frame offsets, creating visually striking temporal effects.

## Features

### Video Processing
- Upload any video file (MP4, WebM supported)
- Automatic letterboxing to preserve aspect ratio
- Frame buffering for smooth playback
- Real-time preview at 1920x1080 resolution

### Grid System
- Configurable horizontal divisions (2-32 columns)
- Configurable vertical divisions (2-24 rows)
- Optional visible grid lines with customizable color and width

### Displacement Modes

#### Random (Noise)
- Procedural noise-based displacement
- Adjustable noise size (scale)
- Adjustable contrast
- Static or animated noise option
- Regenerate button for new patterns

#### Linear Gradient
- Horizontal or vertical direction
- Option to start from center or edge
- Creates wave-like temporal effects

#### Circular Gradient
- Adjustable center point (X/Y)
- Creates ripple-like temporal effects from any point

### Playback Controls
- Play/Pause toggle
- Restart from beginning
- Adjustable maximum frame offset (1-120 frames)

### Background Options
- Solid color background
- Transparent background (for compositing)
- Custom background image with fit options

## How It Works

1. **Upload a Video**: The tool extracts and buffers all frames from your video
2. **Configure the Grid**: Set the number of horizontal and vertical divisions
3. **Choose Displacement Mode**: Select Random, Linear, or Circular pattern
4. **Adjust Parameters**: Fine-tune the displacement effect
5. **Export**: Use Chatooly's built-in export for PNG or video output

The displacement map determines the time offset for each grid cell. A value of 0 plays the current frame, while higher values play frames ahead in time. This creates the illusion of time flowing differently across the video.

## Development

### Prerequisites
- Node.js (for local development server)
- Modern browser with ES6+ support

### Running Locally
```bash
cd GridTimeDisplacement
npm install
npm run dev
```

This starts a local server at `http://localhost:8080` and opens the browser.

### Project Structure
```
GridTimeDisplacement/
├── index.html          # Main HTML structure
├── package.json        # NPM configuration
├── README.md           # This file
├── .gitignore          # Git ignore rules
└── js/
    ├── main.js         # Core video processing & rendering
    ├── ui.js           # UI event handlers
    ├── chatooly-config.js  # Tool metadata
    └── tool-ipc.js     # Hot-reload support
```

## Technical Notes

### Frame Buffering
Videos are fully buffered into memory on load. This enables instant random access to any frame, which is essential for the time displacement effect. Large videos may take time to buffer and use significant memory.

### Displacement Mapping
- Each cell gets a value from 0 to 1 from the displacement map
- This value is multiplied by `maxFrameOffset` to get the frame offset
- Frames wrap around when exceeding total frame count

### Noise Algorithm
Uses a Perlin-style noise function with:
- Permutation table shuffled by random seed
- Gradient vectors for smooth interpolation
- Optional time parameter for animation

## Author

Yael Renous - Studio Video

## License

MIT
