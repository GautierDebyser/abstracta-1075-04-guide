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

Drag to orbit; scroll to zoom; right-drag to pan. Use 3D/front/side/plan presets, numbered steps, pause/resume/replay, bone selection, connector colors, and glass visibility. Play full sequence explicitly starts automatic advancement; use Next/Previous to move manually. All selected demonstrations start paused, including with reduced-motion preference. Download model/BOM JSON from Parts list.

## Quantities and corrections

The reconstructed six-bay L uses three nineteen-tube ladders, fourteen 595 uprights, fourteen 265 upper uprights and fourteen 265 short legs. This exactly matches the original 44 × 595, 28 × 265, 27 × 460, and 5 × 3T / 18 × 4T / 17 × 5T / 2 × 6T.

The user explicitly corrected the original drawing: fit fourteen feet and glass in every bay on all three levels. Corrected quantities are **14 × 705, 15 × 1722, 3 × 1717, 72 × 620 and 72 × 012**. The original drawing's 12 feet, 12 rectangular shelves, 60 clips and 60 bumpers remain recorded in the model and Drawing notes for comparison. No bays are left open.

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

## Revision 2 — October 29, 2026

The instruction panel sits beside the model on desktop; compact stacked panels and visible transport/navigation serve mobile. Each selected step starts paused. Start this step, Pause/Resume, Replay, ¼×/½×/1×/1½× speeds, and a labeled timeline control deterministic playback; only Play full sequence advances automatically. Seeking stops the sequence. Completion checks remain selected when navigating within the page.

Seven base bones A–G are linked to a clickable plan, connector/end descriptions and an arrow-labeled orientation close-up. The six paired ladder joins move receiving bones or connected sections rigidly, rather than translating tubes between two fixed joints. The first A/B pair is progressively seated with the mallet. Illustrative wood supports touch the lower frame during leg/foot installation and leave the leg insertions accessible.

The 620 step retains the fixed camera and exact hardware positions, fades unrelated frame members, numbers the four target corners, and shows the reference image. Four clips install individually, then all other clips install together. The current parts list leads with Revision 2 quantities; original values and history remain in Drawing notes. Print checklist produces current parts, the A–G plan, and all stage checks; a PDF is included in the review package.

Manufacturer cross-check: the supplied September 2025 assembly instructions, steps 2–8, support bones/ladders, grouped progressive seating, legs last, feet after hammering, and clips/bumpers before glass. The particular six-group L sequence and illustrative support setup are not manufacturer-verified. Confirm actual working orientation, support provisions and insertion tolerances with the supplier. This guide does not establish a load rating or structural approval.

Geometry/BOM regression compares nodes, edges, feet, shelves, bracket records and layout coordinates against the saved pre-upgrade model. Existing clear-glass material and **4 mm mesh thickness** are preserved. This revision changes presentation and motion, not manufacturing dimensions.

## Revision 2 validation

Sixteen Node tests pass, including playback idle/reset, individual versus sequence advancement, pause/speed/seek, rigid receiving-group motion, all pair connections, and saved-model geometry/BOM invariance. Browser review covers all fourteen steps, all seven bones, controls and scrubbing, illustrative supports, fixed camera for four then seventy-two clips, print PDF, persisted checks, 1440×900 desktop and 390×844 / 320×568 mobile layouts, reduced motion, source and standalone loading. No browser errors were observed.

For repeatable browser checks, install Playwright/Chromium in the execution environment, serve the repository root on port 8095 (`python3 -m http.server 8095 --bind 127.0.0.1`), and run `npm run test:browser --prefix Abstracta_Codex_Project/software/1075-07-mod3`. Set `MOD3_REVIEW_BASE` to use a different server. The script expects Chromium at `/usr/bin/chromium`.

## Revision 3 — October 29, 2026

All Revision 2 assembly and glass behavior is retained. New features:

- **Saved progress:** browser-local step, A–G selection, completed checks and playback speed. Resume is explicit and always paused at the start of the saved step. Start over requires confirmation; cancel preserves saved data. Storage denial does not block the guide. State schema and guide fingerprint are checked before restoration. Bump `GUIDE_VERSION` in `progress-store.js` for incompatible future changes. A pending saved session is not overwritten before Resume or confirmed Start over.
- **Full-screen workspace:** native Fullscreen API when permitted; CSS expansion when unsupported or rejected. Explicit exit and Escape support, focus management and responsive sizing retain playback time and progress. The expanded workspace contains the instructions and transport controls.
- **Correct/incorrect comparisons:** separate schematic examples of connector orientation, shoulder gaps, collar stop and four bumpers. They do not alter the assembly model or assert measured tolerances.
- **You need:** per-stage new-part quantities and component glyphs, with inch tube lengths, previously assembled sections and tools shown separately. Summed additions reconcile to the current BOM; bone explanations do not duplicate actual parts.
- **Still instructions:** SVG placement diagrams and arrows are generated from model data without WebGL. Manual still mode pauses animation. WebGL unavailability uses the same stills and all stage text, preparation lists, checklists and printing. The exported HTML contains a no-JavaScript diagram/text library as well. `still-instructions.html` in this source folder (and the review package) is a separate script-free, printable guide. Static diagrams are also included in the main print checklist.
- **Inspection focus:** connections, orientation, fourteen feet, seventy-two 620 clips and four bumpers per shelf can be highlighted. Text and still equivalents are available. Checking a box records an installer observation; software cannot verify a physical unit.
- **Usability review:** `USABILITY_REVIEW.md` and the printable HTML/PDF review sheet provide tasks and blank observation fields. The sheet is prepared; no real usability study has been conducted.

`npm run export` regenerates the SVG library, script-free guide and review sheet before exporting the self-contained 3D HTML. `enhancements.test.js` adds state/schema/storage, fullscreen fallback, preparation reconciliation and SVG/comparison tests. `enhancements-browser.cjs` exercises restoration/reset, native and denied fullscreen, still/no-WebGL/no-JavaScript modes, five inspection targets, printing, mobile layout and reduced motion. Run with `MOD3_REVIEW_BASE=http://127.0.0.1:8094 node Abstracta_Codex_Project/software/1075-07-mod3/enhancements-browser.cjs` after serving the repository root on that port. The existing `test:browser` script remains the Revision 2 regression suite.

Preserved geometry: model nodes, tube spans, glass widths/depths/positions, all bracket/bumper transforms, corrected BOM and 4 mm glass mesh thickness. Clear-glass material, fixed 620 installation camera and paired assembly logic are unchanged. These visual aids do not resolve unverified fit, structural loading or the supplier review needed for the custom L grouping and support arrangement.

### Revision 3 validation results

24 Node tests passed. Both browser suites passed after correcting a short-phone overlap that had intercepted the Parts button. Coverage includes preserved Revision 2 behavior; saved-state restore/reset/cancel/version mismatch/storage denial; native and rejected-native fullscreen; keyboard exit and reduced motion; per-stage prep; manual still mode; five inspection targets; fixed 620 camera; print diagrams; 320 px and 390 px phone layouts; no-JavaScript and WebGL-disabled fallbacks. No unexpected browser errors were observed. The updated checklist is six A4 pages with SVG illustrations. The usability review sheet remains blank and marked prepared, not conducted.
