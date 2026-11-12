# AutoMart Phase 3 — focused homepage and vehicle directory

## What changed
- Replaced the previous long homepage with a deliberately short discovery page: one hero/search action, two clear routes (vehicle or component), and one concise fitment disclaimer. Featured product, brand, category and repeated vehicle rails were removed from the homepage so those destinations have their own pages.
- Rebuilt the vehicle directory with searchable vehicle cards, year ranges, descriptions, explicit profile actions, responsive layout and an empty search state.
- Added a dedicated vehicle-directory script with live filtering and result counts.
- Replaced text-only placeholder category images for lighting, engine and drivetrain with photographic editorial references.
- Added image error fallbacks to vehicle cards.
- Corrected catalogue-card title/description colours where light card surfaces were paired with low-contrast white text. Improved product-detail panel text contrast as well.
- Improved brand-card text contrast.

## Important limitations
- Vehicle images are editorial reference photographs, not guaranteed exact model/generation/trim photographs. The UI labels them as model references. A verified vehicle photo library still needs sourced/licensed assets.
- Product images are category-level references unless the exact SKU image has been supplied. They must not be treated as exact product photography.
- This phase does not create OEM CAD, genuine 360-degree tours, verified fitment, or production inventory.
- The current application seeds data only when the catalogue is empty. If a persistent database already contains old rows, reseeding will not replace their old image URLs.

## Verification
- `node --check src/main/resources/static/js/vehicle-directory.js` passed.
- ZIP integrity check passed.
- Maven is not installed in the build environment, so Java compilation and Spring Boot runtime verification could not be performed here.

## Run locally
```bash
cd ~/Downloads/automart-merged
mvn clean spring-boot:run -Dspring-boot.run.arguments=--server.port=8081
```
Then open http://localhost:8081/home.
