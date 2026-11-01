# Illuminate3D

A browser-based designer for 3D-printable lampshades and their fittings. Shape the shade, layer surface patterns, pick how it connects to the light, and export watertight STL files ready for the slicer.

**Live app:** https://mahroofgit.github.io/Illuminate3D/

## Features

- **Freeform shape** – drag a silhouette profile, set height, width, oval, wall thickness, polygon sides with corner rounding, and twist (linear / ease / wave). Profile smoothing for soft curves.
- **Surface patterns** (stackable) – vertical ribs, spiral ribs, horizontal rings, wavy rings, diamonds, bubbles, organic noise, each with depth and sharpness, fading out near the connector.
- **Connectors**
  - *Socket ring* – clamps straight onto an E27, E14, B22, M10 nipple or custom holder (spokes or solid disc).
  - *Twist-lock* – bayonet collar on the shade with 45° chamfered lugs and an optional click detent; locks into a separate part:
    - **Table base** with an LED puck pocket, a **slot-in puck** seat (push a small puck up edgewise through a slot, turn it flat; straight slot for a low base or a finger funnel), or a bulb-socket mount with a holder cavity.
    - **Socket adapter** for pendants.
- **Print checks** – overhangs above your limit shown in red, printer bed fit, puck/collar fit, bulb clearance, weight estimate.
- **Projects** – New / Open / Save / Save as (⌘S, ⌘O) with thumbnails, stored in the browser; export and import `.json` files to back up or move designs.
- Viewer with solid-section cutaway, exploded view, lamp-on preview, and toggles to show or hide the shade, base and hardware.

## Printing tips

Print the shade connector-end down, supports off, 0.2 mm layers, 3 walls, 0% infill. Bases print upright. Start the twist-lock at 0.3 mm clearance (0.4 mm for PETG). Measure your holder and puck with calipers — the built-in sizes are typical values. Use LED bulbs only.

## Install as an app

Illuminate3D is a Progressive Web App: install it once and it gets its own icon and window, and works offline.

- **Mac – Safari** (macOS Sonoma or later): open the live app, then **File → Add to Dock**.
- **Mac – Chrome / Edge**: click the install icon at the right end of the address bar (or **⋮ → Cast, save and share → Install page as app**).
- **iPhone / iPad**: Safari → Share → **Add to Home Screen**.

The installed app checks for updates whenever you are online and opens from its offline cache otherwise.

## Running locally

The app is a single `index.html` with its libraries in `vendor/`, so it works offline. Browsers won't load modules from `file://`, so serve the folder:

```bash
python3 -m http.server 8000
```

then open http://localhost:8000.

## Built with

- [three.js](https://threejs.org) r180 – 3D preview (MIT)
- [Manifold](https://github.com/elalish/manifold) 3.5.1 – watertight CSG for the connectors and export (Apache-2.0)

Licenses for both are included in `vendor/`.
