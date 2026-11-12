# AutoMart — Phase 4 implementation

This phase targets the latest reported defects rather than adding another global theme layer.

## Implemented

- Replaced catalogue description-substring matching with relevance scoring across product name, part number, manufacturer, category and vehicle identity. Generic marketing/technical descriptions are excluded from broad-term matching, preventing `engine` from matching every filter whose description mentions an engine.
- Replaced the free-text catalogue filter field with a closed-by-default category/system selector. Kept Sort as a matching select control, added part-number sorting, and made the visible result count update with filtering.
- Added a make selector to the vehicle directory alongside live make/model/year search.
- Expanded vehicle profiles with a structured configuration panel. Missing generation, engine, fuel, transmission and trim values are explicitly marked unavailable rather than fabricated.
- Added an editorial vehicle image panel and clearer model-reference labels to the vehicle profile.
- Added front/side/rear camera presets to the conceptual viewer and made the visible system markers clickable. The model remains procedural concept geometry, not a vehicle-specific CAD asset.
- Added a global image-error fallback mechanism and 11 distinct component/system fallback illustrations plus a vehicle fallback illustration. Existing photo URLs remain labelled as reference imagery, not exact SKU photography.
- Changed the seeder so image mappings refresh on existing demo rows at startup; previously its early return could leave stale/broken URLs in the database.
- Improved account-dropdown stacking, overflow and text contrast so the menu is not clipped behind page content.
- Added page-contextual footer content for vehicle research, catalogue, general pages, authentication and checkout.
- Improved product-detail contrast and made vehicle associations explicitly unverified.

## Important limitations

- Product images are still category-level references, not exact SKU photographs. The SVGs are labelled fallback illustrations and are only used if a remote image fails.
- Vehicle images are editorial references and are not guaranteed to match exact generation/trim.
- Vehicle profile data model still has only make, model, year range, image and description. The UI now marks missing technical configuration honestly; it does not invent engine/trim data.
- The 3D viewer is still conceptual procedural geometry. Genuine model-specific 3D/360 tours require licensed vehicle assets and verified component coordinates.
- Search is still in-memory over the current demo catalogue; database-backed indexing, pagination and OEM cross-reference entities remain future architecture work.
- No payment, inventory or live supplier availability is claimed.

## Validation

- JavaScript syntax checks passed with `node --check` for all static JS files.
- Maven packaging could not be run in this environment because `mvn` is not installed. A successful Spring Boot compile/runtime is therefore not claimed.
