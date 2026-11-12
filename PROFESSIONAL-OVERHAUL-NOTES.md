# AutoMart — Professional Overhaul Notes

## What changed in this pass

### 1. Vehicle Intelligence Studio restoration
- Restored the richer pre-redesign `vehicle-studio.js` implementation from `src-backup-before-redesign`.
- Reinstated the 3D system markers, system filtering, solid/wireframe modes and reset behaviour.
- Added front/side/rear camera presets while preserving the restored 3/4 default view on the vehicle profile.
- Made the 3D markers clickable; selecting a marker activates the corresponding component-system filter.
- Added visibility-aware rendering so the WebGL scene stops animating while off-screen or while the browser tab is hidden.
- Expanded the viewer to a full-width stage instead of splitting its space with a duplicate vehicle photo.
- Kept the model explicitly labelled as conceptual geometry, not OEM CAD or a verified digital twin.

### 2. Guided tour rebuilt
- Replaced the old four-tab text switcher with a five-step walkthrough: Exterior, Powertrain, Running Gear, Electrical, and Cabin & Controls.
- Added a real progress indicator, step count, previous/next navigation, restart behaviour, system purpose, component groups and fitment-check guidance.
- Connected the tour steps to camera presets and 3D system hotspots.
- Connected the 3D markers and system shortcuts back to the correct guided-tour step.
- Added a separate photo-reference panel with an explicit disclosure that the available image is not a 360-degree capture or a trim-verified view.
- Added a catalogue continuation action.

### 3. Spatial UI and motion system
- Added layered surfaces, restrained glass, stronger depth, controlled borders and more consistent spacing.
- Improved heading scale, body contrast, focus states and control affordances.
- Added scroll-triggered reveals and staggered card entrances.
- Added reduced-motion support.
- Applied responsive layouts for the vehicle studio and guided tour.

### 4. Source validation
- JavaScript syntax checked with Node for `vehicle-studio.js`, `vehicle-tour.js` and `script.js`.
- Updated Thymeleaf templates parsed as HTML.
- CSS parsed with `tinycss2` with zero parse errors.

## Important limitations — intentionally not faked

- The archive contains no licensed model-specific GLB/GLTF vehicle assets and no complete multi-angle 360-degree photo sets. The existing conceptual model is retained and improved; it is not represented as a production-accurate vehicle model.
- The tour is now a structured system walkthrough with camera presets and catalogue links. It is not a true photographic 360-degree tour. Real exterior/interior view switching requires the correct image set for each vehicle generation and trim.
- The project still uses its existing sample catalogue and H2 configuration. Persistent production data, manufacturer/OEM reference ingestion, supplier moderation, and evidence-backed fitment require a separate data/backend implementation.
- A Maven build could not be run in this environment because Maven is not installed. Run `mvn clean package` locally before launching the application.

## Files changed
- `src/main/resources/templates/vehicle-detail.html`
- `src/main/resources/templates/vehicle-tour.html`
- `src/main/resources/static/js/vehicle-studio.js`
- `src/main/resources/static/js/vehicle-tour.js`
- `src/main/resources/static/js/script.js`
- `src/main/resources/static/css/style.css`
