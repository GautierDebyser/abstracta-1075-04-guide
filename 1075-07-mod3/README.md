# 1075-07 Mod 3 — animated assembly instructions

User authorized sharing on the existing public guide website. Public guide: https://gautierdebyser.github.io/abstracta-1075-04-guide/1075-07-mod3/ . Follows `../../ASSEMBLY_GUIDELINES.md` and reuses the Chair Unit's bone/913, upright, leg, and foot components and timing. Frame and shelf geometry are generated specifically for this L-shaped unit; no Chair Unit parts counts are reused.

## Run

From the repository root:

```sh
npm start --prefix Abstracta_Codex_Project/software/1075-07-mod3
```

Open http://localhost:8087/software/1075-07-mod3/ . Python 3 and the project's existing Three.js 0.180.0 installation in `software/1075-04/node_modules/three` are required. If missing, run `npm ci --prefix Abstracta_Codex_Project/software/1075-04` first.

Or open `assembly-guide/1075-07-mod3.html` from the repository root in a browser. That standalone file embeds Three.js, source modules, styling, and the 620 reference image, with no CDN dependency. If your browser restricts local HTML, use the local server above.

## Controls

Drag to orbit; scroll to zoom; right-drag to pan. Use 3D/front/side/plan presets, numbered steps, pause/resume/replay, bone selection, connector colors, and glass visibility. Play sequence advances through the guide; use Next/Previous to move manually. Reduced-motion preference starts individual demonstrations paused. Download model/BOM JSON from Parts list.

## Quantities and corrections

The reconstructed six-bay L uses three nineteen-tube ladders, fourteen 595 uprights, fourteen 265 upper uprights and fourteen 265 short legs. This exactly matches the original 44 × 595, 28 × 265, 27 × 460, and 5 × 3T / 18 × 4T / 17 × 5T / 2 × 6T.

The user explicitly corrected the original drawing: fit fourteen feet and glass in every bay on all three levels. Corrected quantities are **14 × 705, 15 × 1722, 3 × 1717, 72 × 620 and 72 × 012**. The original drawing's 12 feet, 12 rectangular shelves, 60 clips and 60 bumpers remain recorded in the model and shown alongside the corrected quantities in the parts list. No bays are left open.

Catalog glass dimensions: 1717 = 17 9/16″ square; 1722 = 17 9/16″ × 22 3/4″. Feet follow the user-supplied insert appearance and collar stop; equivalence between the pictured 3705 name and the drawing's 705 code is not verified. Rendered casting/clip dimensions, fit, foot extension, structural stability and load limits remain schematic or unverified. The 143 lb drawing weight is not a load rating.

## Source and export

- `model.js`: topology, cut lengths, corrected BOM and original drawing quantities.
- `app.js`: step controller, Three.js scene and installation demonstrations.
- `bracket-620.js`: curved-bridge, perpendicular corner-clip component, distinct from 625.
- `motion.js`: clip sequencing and shared slide timing.
- `export-guide.mjs`: self-contained HTML export; embeds only the reused connector portion of the component library, not unrelated museum geometry.

```sh
npm test --prefix Abstracta_Codex_Project/software/1075-07-mod3
npm run export --prefix Abstracta_Codex_Project/software/1075-07-mod3
```

The completed screenshot is `assembly-guide/1075-07-mod3.png`; JSON is `assembly-guide/1075-07-mod3-model-and-bom.json`. Source drawing was supplied in chat: #1075-07 Mod 3, Barbara McFadyen Jewelry, 10/1/26, Matte Black, Glass. Component references and manufacturer PDFs remain in the project reference directories.

## Clear-glass appearance

Glass uses the reusable `../shared/glass.js` component: highly transparent neutral faces, aqua-green cut edges, polished-edge highlights, a soft studio reflection environment, and faint contact occlusion located at the actual vinyl bumper centers. Works with supplied 620 or 625 support coordinates. Contact shading is hidden while glass is above its supports. Shelf dimensions and bracket transforms are unchanged. The optical material reference is 1/4 inch; the existing 4 mm mesh thickness is deliberately preserved pending a separate geometry correction.
