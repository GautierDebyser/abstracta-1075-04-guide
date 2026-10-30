# #200 Mod — animated assembly instructions

Reference: #200 Mod, Martin Beck, 9/24/25, Chrome finish, Original 13 mm, glass shelving. This guide follows `../../ASSEMBLY_GUIDELINES.md` and the latest saved-progress/full-screen/still-instruction architecture. The user authorized publication at https://gautierdebyser.github.io/abstracta-1075-04-guide/200-mod/ .

## Drawing and model

Eleven bays wide × one bay deep × three tiers, with four horizontal shelf levels. All tubes are drawing code **395**, with the explicitly labeled **15.08″ cut length**. Each horizontal ladder uses twelve depth bones plus twenty-two joining tubes (34 total). Four ladders plus three tiers of twenty-four uprights give exactly:

| Part | Quantity |
|---|---:|
| 395 / 15.08″ tube | 208 |
| Original 3T | 8 |
| Original 4T | 48 |
| Original 5T | 40 |
| 1414 glass shelf | 44 |
| 620 corner clip | 176 |
| 012 vinyl bumper | 176 |

No separate short legs, feet or glides are specified or added. Shelf size is the manufacturer catalog's 14 15/16″ square. Glass thickness is not specified by the drawing; the existing clear-glass component is used with its 4 mm schematic mesh thickness. The 244 lb figure is drawing unit weight, not a load rating.

Printed overall size: 47.28″ H × 172.00″ W × 16.10″ D. The literal 15.08″ cut plus nominal 13 mm shoulder assumptions give 47.287″ × 172.022″ × 16.104″; the small differences are documented rather than changing the specified cut length.

## Component fit and references

Existing Original connectors, 913 mallet and 620 geometry are reused. `bracket-620.js` instantiates `createBracket620` from the earlier guide without changing its shape, reach, curved ends, placement convention or offsets. The user's instruction that the components fit as designed takes priority; no photo-review geometry proposals have been applied.

Visual reference sources include the repository's `Abstracta-3D-Images` collection, existing bracket reference images, manufacturer September 2025 assembly instructions and October 2025 catalog. Chrome is rendered as specified; connector identification colors are optional. The shared clear-glass material and contact shading are retained.

## Assembly and controls

Fourteen stages cover parts, connector orientation, twelve bones A–L, receiving-bone ladder joins, three sets of twenty-four uprights, four ladders, 620/012 installation, glass and inspection. The first two upright insertions in each tier use the 913; subsequent uprights slide into place. The receiving bone moves onto each joining pair as a rigid component. The bone demonstration rotates the whole bone to place two prongs on the wood, without changing the connector topology. Chrome unit dimensions remain unchanged during all motion.

Steps start paused. Use Start this step, Pause/Resume, Replay, speed and progress slider; only Play full sequence advances automatically. Saved progress has a separate #200 Mod storage key and schema, offers explicit paused restoration, and requires confirmation to reset. Native full screen has a CSS fallback. The static mode, embedded no-JavaScript library and separate still HTML work without WebGL. Preparation lists derive new parts from the model, while existing assemblies and tools remain separate. Final inspection highlights joints, glass, clips and bumpers; checks record installer observations, not software verification of the physical unit.

The 620 view remains fixed: first four clips install individually, then all other 172 install simultaneously. Each of the 44 shelves receives four clips and four bumpers. Physical working orientation, assistance, stability/anchoring and loading remain for supplier verification; no manufacturer or structural approval is implied.

## Run and export

From the repository root:

```sh
npm start --prefix Abstracta_Codex_Project/software/200-mod
```

Open http://localhost:8088/software/200-mod/ . Python 3 and the existing pinned Three.js installation in `software/1075-04/node_modules/three` are needed. If missing, run `npm ci --prefix Abstracta_Codex_Project/software/1075-04`.

The self-contained `assembly-guide/200-mod.html` can also be opened directly in a browser. It embeds Three.js, code, styling, static SVG diagrams and the 620 reference image, with no runtime CDN dependency. If local HTML is restricted, use the server above. The review ZIP contains the interactive file, script-free still guide, model/BOM JSON, screenshots, checklist PDF and blank usability review sheet.

```sh
npm test --prefix Abstracta_Codex_Project/software/200-mod
npm run export --prefix Abstracta_Codex_Project/software/200-mod
```

For browser checks, serve the repository root on port 8093 and run `npm run test:browser --prefix Abstracta_Codex_Project/software/200-mod`. Playwright and `/usr/bin/chromium` are required; `MOD200_REVIEW_BASE` can change the test server URL. Export regenerates static illustrations and the prepared usability review sheet without WebGL. No actual usability study has been conducted.

## Source map

- `model.js`: unit-specific topology, drawing, BOM and instructions.
- `app.js`: viewer and assembly UI adapted from the latest guide.
- `assembly-motion.js`: eleven paired receiving-bone joins.
- `motion.js`: clip timing and step durations.
- `bracket-620.js`: unchanged legacy component instanced at unit-specific shelf corners.
- `guide-data.js`, `preparation.js`, `still-diagrams.js`: A–L orientation, checklists, per-stage parts and static alternatives.
- `playback.js` and `fullscreen.js`: reuse the established shared behavior.
- `progress-store.js`: #200 Mod-specific saved state and twelve-bone validation.

## Validation

Eleven geometry/motion/state tests pass. Browser checks pass all fourteen stages and all twelve bone selections with two prongs contacting the wood at both ends, eleven paired joins, three sets of twenty-four seated uprights, the 34-tube top ladder, fixed camera for four then 176 clips, playback controls, saved paused restoration, fullscreen, still mode, inspection, printing, desktop/mobile/reduced-motion layouts, source loading and WebGL-disabled fallback. Chrome material was checked in both the finished frame and bone/orientation demonstrations. No browser errors were observed. The prepared usability review sheet has not been conducted.
