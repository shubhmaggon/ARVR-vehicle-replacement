# Vehicle AR

WebXR + three.js app that places cars, trucks, buses, vans and motorbikes on any flat surface (floor, table, pavement, road, lawn) through your phone camera. One file, no build step, no assets.

## Run locally
```bash
cd ar-road-vehicles
npx serve .          # desktop preview at http://localhost:3000
```
WebXR AR needs **HTTPS**. To test on your phone, use a tunnel: `npx localtunnel --port 3000` (or `ngrok http 3000`).

## Deploy (pick one)
- **GitHub Pages**: push `index.html` to a repo, Settings > Pages > deploy from branch. HTTPS is automatic.
- **Netlify / Vercel / Cloudflare Pages**: drag-and-drop the folder.

## Device support
- Android + Chrome + ARCore (Google Play Services for AR): full AR.
- iOS Safari does not support WebXR immersive-ar. Use the desktop-style preview, or open in a WebXR-capable iOS browser app.
- Desktop: 3D preview with a sample floor grid (drag to orbit, scroll to zoom, click to place).

## Use
1. Tap **Start AR**, grant camera permission.
2. Scan any flat surface slowly until the yellow ring appears. Only horizontal, upward-facing surfaces are accepted.
3. Pick vehicle, set **Heading** (direction) and **Scale** (life-size, Tabletop 1:10 or Toy 1:50 presets, or the slider), and turn on **Footprint** to see the ground area the vehicle covers.
4. Tap the surface to place. **Undo** / **Clear all** to remove.

## Customise
Edit `SPECS` and `buildVehicle()` in `index.html` to change sizes/colours, or swap in a glTF model with `GLTFLoader` (import from `three/addons/loaders/GLTFLoader.js` by adding it to the import map).
