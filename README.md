# NozzleLab – 2D CD Nozzle Test Section

Real-time 2D converging-diverging (de Laval) nozzle CFD in the browser (no dependencies). A compressible Euler solver on a body-fitted grid shows the throat, normal shock, oblique shocks and Mach diamonds, with live comparison against 1-D isentropic theory.

**Live demo:** https://bhargavd1501.github.io/Nozzle-test/  *(change to your repo name)*

- Nozzle types: conical, bell (parabolic), contoured S-curve, dual-bell, convergent-only
- Area ratio 1–5 (slider, presets, or drag the exit lip), throat width 10–300 mm
- Gases: air, steam, CO₂, rocket exhaust, helium; p₀ 100–3000 kPa, T₀ 250–3500 K
- Pressure ratio NPR 1.003–150 with presets: subsonic, shock in nozzle, over-expanded, design, under-expanded
- Overlays: Mach, pressure, temperature, density, velocity, Schlieren; sonic line, streamlines, vectors, smoke lines, pathlines
- Live HUD: M throat/exit, exit velocity, mass flow, thrust, C_F (sim vs theory), flow regime and critical NPRs
- Centre-line plot of simulated Mach / pressure against the 1-D curve
- Auto quality mode holds about 60 FPS on phones
- Installable as a Progressive Web App (works offline after the first visit)

## Controls
Drag the exit lip to change area ratio · ↑ / ↓ change NPR · ← / → change area ratio · Space pauses · ↺ restarts the flow · ⛶ fullscreen

## Files
`index.html` (the app) · `manifest.json` · `sw.js` · `icon-192.png` · `icon-512.png`

## Install
Open the GitHub Pages link in Chrome → ⋮ menu → **Install app** (or **Add to Home screen**).

## Note
Educational and visual tool, not a validated CFD solver. Inviscid (no boundary layer or flow separation), ambient gas at T₀. Choked and supersonic cases agree with 1-D theory within a few percent on mass flow and thrust; the subsonic regime is the least accurate. Shock positions are approximate.

## Shock diamonds / extended outlet (v2)

The ambient chamber after the nozzle exit is now ~3× longer (46 length units, throat half-height = 1), so the
under- and over-expanded jet cells ("shock diamonds") have room to form.

- **View** menu: *Exit + plume* (default), *Whole nozzle + near plume*, *Far plume*, *Whole chamber*.
- **Pan** by dragging, **zoom** by pinch / mouse wheel, double-tap to reset the view.
- Best diamonds: a **Convergent** nozzle at NPR ≈ 3–6, or a CD nozzle at *Under-expanded* / a small area ratio.
- Use the **Schlieren** overlay to see the shock cells; centre-line plot follows the visible window.
- 2nd-order (MUSCL) is now on by default, because it is needed to keep the diamonds sharp.
