# Tesla Roadster Cold-Gas Hover Sim

A browser physics sim: a 1700 kg Roadster hovers on choked nitrogen cold-gas
thrusters (10,000 psi / 600 L tank bank, 12 nozzles), with a 50 Hz flight
computer, bang-bang valves, spring-damper landing, and 360° flip maneuvers.

Open `index.html` directly in a browser — no server needed. Three.js loads
from a CDN.

## 3D model

The real car model is **not included** for licensing reasons. Without it the
sim builds a simple procedural placeholder car and everything works.

To use a real model, provide `roadster_model.js` next to `index.html`:

```js
window.ROADSTER_B64 = "<base64 of a .glb>";
```

Requirements for the GLB (what the loader expects):

- meters, car facing +X, wheels on the y=0 contact plane
- wheel meshes grouped near `x=±1.38/1.463, z=±0.78` (they are re-grouped by
  proximity; see the loader in `index.html`)
- tire meshes named `Material_96` get a thin-tire scale tweak (optional)

Note: the Roadster body design is Tesla's, and any third-party 3D model of it
is a derivative work. Only ship a model you have permission to redistribute.
