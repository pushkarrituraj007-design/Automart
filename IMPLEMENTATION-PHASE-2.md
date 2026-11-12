# AutoMart implementation — Phase 2

This pass upgrades the existing Spring Boot + Thymeleaf application in place.

## Delivered in this pass
- Refined the shared navigation: compact account control and sign-out inside its dropdown rather than a permanent header button.
- Added a responsive catalogue toolbar with instant filtering and client-side A–Z / manufacturer sorting.
- Refined the homepage hierarchy, hero/search presentation, section rhythm, vehicle rail, category band, product cards and trust explanation.
- Added a shared visual foundation for surfaces, typography, spacing, borders, responsive layouts, focus states and reduced-motion support.
- Improved vehicle directory, studio, tour, product detail, authentication and footer styling.
- Replaced the unsupported “trusted Indian brands” assertion with neutral directory language.
- Kept the vehicle viewer/tour limitations explicit: the current procedural model and editorial image are not OEM CAD or a real 360-degree capture.

## Important limitations still requiring a later phase
- No licensed vehicle-specific CAD/GLB assets or real 360-degree image sequences are included. The current viewer remains conceptual.
- Existing seeded catalogue records and external image URLs still need a reviewed asset/content audit. This pass does not invent SKU photography or exact fitment.
- Database remains H2 in-memory with `create-drop`; persistent PostgreSQL/MySQL and migrations remain a separate data migration task.
- Checkout/payment and contact submission are not production transaction workflows.
- Authentication/security needs a dedicated production hardening and integration-test pass.

## Run locally
From the project root:

```bash
mvn clean spring-boot:run -Dspring-boot.run.arguments=--server.port=8081
```

Then open http://localhost:8081. Maven build could not be run in the packaging environment because Maven is not installed there. JavaScript syntax checks passed for the updated catalogue script and existing shared/viewer scripts.
