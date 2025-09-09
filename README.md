# Rack Builder

A standalone HTML tool for building IO racks (or any side-by-side layout) by dragging in device images.  
Each image is automatically cropped against its white background, given a margin, and added as a tile.  
No backend required — everything runs in your browser.

👉 **[Use it live on GitHub Pages](https://benhar-dev.github.io/webtool-rack-builder/)**

## Demo

![image](./docs/images/screenshot.gif)

## Features

- **Drag & Drop** images directly from your computer or other webpages
- **Paste** (Ctrl/Cmd + V) images directly from clipboard
- **Automatic white-background cropping** with configurable margin and tolerance
- **Rack layout**: images appear as tiles you can reorder by drag-and-drop
- **Copy** button on each tile to duplicate it instantly
- **Delete** button to remove tiles
- **Reorder** tiles with intuitive drag-and-drop (with insertion markers)
- **Combined output**: build a single stitched image from all tiles
- **Customisation**: spacing, background colour, vertical alignment
- **Copy to clipboard** combined PNG
- **Download** combined PNG
- **Settings persistence** via `localStorage`

## Quick Start

1. Open the [live GitHub Pages version](https://benhar-dev.github.io/webtool-rack-builder/).
2. Drag in an image (or paste one).
3. Adjust **Margin px** or **White tolerance** if needed.
4. Reorder, duplicate, or delete tiles in the rack.
5. Copy or download the combined PNG output.

## Local Usage

1. Clone or download this repo.
2. Open `index.html` in your browser.
3. Use it the same way as the hosted version.

## Notes

- If the source website blocks CORS, dragging a URL directly may not allow pixel access. In that case, **paste the image**, or **save and drop** the file instead.
- The rack view has a fixed max height so it doesn’t crush the combined output — scroll sideways if you add many tiles.
- Works entirely client-side. No uploads or external servers.

## Development

The core logic is in plain JavaScript:

- `AutoCropper.computeBounds()` — finds the bounding box of non-white pixels
- `AutoCropper.cropWithMargin()` — trims with the configured margin
- `Rack` — manages the list of tiles, drag-drop reordering, duplication, and removal
- `App` — wiring between UI, cropper, and rack, plus persistence in `localStorage`

## License

MIT — free to use, modify, and distribute.
