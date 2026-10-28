# Chair Unit · interactive assembly instructions

Source: user-supplied #Chair Unit / KSM Design Source drawing, dated 10/22/26.
White Original zinc 13 mm system. Printed dimensions: 123.28″ H × 127.27″ W ×
32.20″ D. Shelving: **None**. The approval fields are blank.

## Run and export

Reuses Three.js 0.180.0, OrbitControls, the existing guide architecture, and the
museum viewer's parametric Original connector mesh. From this directory:

```sh
# Only if the shared Three.js installation is absent:
npm ci --prefix ../1075-04 --cache /workspace/.npm-cache
npm start
```

Open `/software/chair-unit/` on the server at port 8084. Drag to rotate, wheel
to zoom, use Next/Previous or arrow keys, or Play sequence. Thirteen stages
show the four horizontal ladders, three upright tiers, short legs, adjustable
feet and accessory instructions. Show remaining frame and connector colors
are optional. The parts dialog exports the JSON model and BOM.

`npm test` validates quantities, stock cuts/end allowances, topology, staging
and nominal dimensions. `npm run export` produces the self-contained file
`../../../assembly-guide/chair-unit.html` for browser viewing/sharing.

## Verified transcription and model derivation

Four bays wide × one bay deep × three long-upright tiers. Five depth bones and
eight longitudinal tubes form each of four horizontal ladders: **52 × #805
(31.18″)**. Three sets of ten uprights give **30 × #1000 (38.85″)**. Ten short
legs use **10 × #130 (4.69″)**. Part codes are not cut lengths in millimeters.

Every bottom/intermediate ladder uses four 4T and six 5T connectors; the top
uses four 3T and six 4T. Totals: **4 × 3T, 18 × 4T, 18 × 5T**, exactly matching
the drawing. Bottom joints include downward prongs for the leg tubes. Prongs
stay inside the tubes; compact shoulder meshes are provisional, not exact CAD.
No 6T, Cubitz parts, oversized balls or exposed connector spikes are used.

The nominal 13 mm shoulder allowance and rounded inch cuts produce about
123.29″ × 127.28″ × 32.20″. Differences from the printed size are ~0.01″;
unmeasured 705 foot extension is excluded. A foot end has no Original
connector: the leg tube is trimmed only at its upper connector shoulder.

Specified accessories: **64 × 625, 64 × 012, 10 × 705**. The 625 reference has
parallel tube clips; 620 is not substituted. Four brackets per shelf implies
sixteen potential shelf positions, but no panel sizes/allocation are stated
and the drawing explicitly specifies no shelving. Accordingly shelf panels
are not invented. Brackets/bumpers appear in the BOM and instructions, not as
unmeasured detailed meshes. The 705 shapes are explicitly schematic.

## Physical sequence and limitations

Manufacturer general instructions describe bones → ladders → uprights,
progressive seating, short legs last, then feet after hammering, then accessories.
Follow those principles with stable support and assistance. The animation's
upright orientation is explanatory, not a self-supporting erection method.
Confirm stability/anchoring, shelf hardware allocation and loading before use.
The drawing's 96 lb value is unit weight, **not a load rating**. "Chair Unit"
does not establish that this frame is seating furniture.

Tube wall thickness, exact casting dimensions, connector insertion depths,
705 installed height and mechanical tolerances are unknown. No manufacturing
accuracy or structural approval is claimed. The Drawing notes dialog contains
a transcription and an embedded authoritative 625 appearance reference.

## View appearance update

At the user’s request, the current guide renders the tubes black on a light
background. The source drawing specifies White. This rendering override does
not change tube dimensions, quantities, connectors or accessory specifications.

## 913 mallet demonstration

The Base bones stage opens a close-up of a supported #805 tube, with a
schematic 913 nylon mallet tapping each connector into position. Choose any
of the five bones to see the appropriate 4T or 5T connectors. Pause/replay
the tapping, orbit/zoom, or disable the close-up to return to the full frame.
The main sequence spends sixteen seconds on this step. The demonstration
respects reduced-motion preferences and supplies an explicit Resume control.

Tool identity and silhouette come from the manufacturer assembly PDF, page 1;
the supported-bone procedure is on page 2. The tool dimensions, insertion
depth, travel, speed and support-block proportions are unmeasured visual
aids, not force or fit specifications. Actual frame geometry/BOM is unchanged.

The support layout is corrected to end-on: the lower connector shoulder rests
on the top of a wood block, the tube stands upright, and the mallet approaches
the upper connector from above. The bone turns end-for-end for the second
end. The block is no longer under the middle of a horizontal tube.
The separate uploaded 913 photograph is not available in the checkout/chat
attachments; the existing catalog-based schematic remains pending that image.

The bone close-up now begins with a four-second alignment stage: both
connectors are shown on the wooden block, their prong directions rotate into
matching alignment, and the view holds for a check. No mallet is shown or
operated during alignment. The existing supported, upright seating sequence
then follows. Replay returns to alignment, not straight to hammering.
