# AutoMart — Phase 6: Vehicle Studio & Guided Walkthrough Refinement

## What changed

### Vehicle Studio
- Replaced the shared camera/model rotation behaviour with an independent orbit camera. Front, side, rear, top and three-quarter presets now change the actual camera position.
- Reworked the procedural motorcycle and car concept assemblies into separate exterior, powertrain, running-gear, electrical and cabin groups.
- Added system isolation: selecting a system hides unrelated assemblies so the selected mechanical group can be inspected without five labels pretending to change the view.
- Moved system markers into a persistent marker layer. Markers remain selectable while an assembly is isolated, so the user can jump between systems from the model itself.
- Added a selected-system camera focus, bounded zoom, orbit elevation limits, on-screen zoom controls, solid/wireframe modes, fullscreen and a reset action.
- Kept the concept-model / not-OEM-CAD disclosure visible. The geometry is illustrative and must not be represented as a manufacturer-accurate digital twin.

### Guided walkthrough
- Rebuilt the five walkthrough states: Exterior, Powertrain, Running gear, Electrical, and Cabin & controls.
- Each state now has distinct explanatory content, a component list, system-specific camera focus and a matching 3D assembly isolation state.
- Component rows open an inspection detail with practical fitment checks and a catalogue research link.
- Added progress, previous/next navigation, restart behaviour, keyboard shortcuts (1–5, left/right arrows, F for fullscreen), and model-marker-to-tour synchronisation.
- Removed the repeated generic vehicle photo from the walkthrough. The selected model system is now the main visual context instead of the same image being reused for every system.
- Moved camera controls into a compact dock at the bottom of the model stage rather than floating over the vehicle.

### Readability and visual refinement
- Increased contrast across the tour's light editorial introduction, dark technical inspector and muted supporting text.
- Reworked the model stage as a layered spatial environment with controlled lighting, a floor/grid, restrained glass dock, and clearer depth hierarchy.
- Added component selection states, hover/focus feedback and responsive layout adjustments.
- Corrected the authentication story headline contrast visible in the supplied screenshot (light text on the dark left panel).
- Preserved reduced-motion support and the existing site-wide scroll reveal behaviour.

### Vehicle profile page
- Preserved the front/side/rear camera controls and system index.
- Connected system index controls to the corresponding 3D assembly focus and catalogue filtering/readout.

## Validation performed

- `node --check` passed for `vehicle-studio.js` and `vehicle-tour.js`.
- CSS parsed with `tinycss2` with zero top-level parse errors.
- Vehicle tour and vehicle detail templates parsed with BeautifulSoup; each has one model canvas and no duplicate IDs.
- Maven build/test was not run because Maven is not installed in the execution environment. Run `mvn clean test` and `mvn spring-boot:run` locally before merging.

## Known limitations / honest scope

- The 3D geometry remains a procedural concept model, not an OEM CAD model or licensed photogrammetry asset. It now has meaningful, system-specific assemblies and interactions, but accurate model-specific body geometry requires a suitable licensed GLB/GLTF asset.
- A true 360-degree photographic tour still requires a matching multi-angle image set for the exact generation/trim. The walkthrough now changes the actual 3D assembly view instead of reusing a single photo as if it were five views.
- Product links are research links into the current catalogue. They do not prove vehicle fitment. Verified fitment still requires engine/variant-specific records and evidence.
