# AutoMart — Beta 0.1 design and Java architecture update

## Reference used
The JavaFX Beta 0.1 reference was inspected directly. Its dark graphite surfaces, blue gradient primary actions, Inter/SF typography, glass panels, sidebar-style navigation language, rounded cards, compact status pills and comparison-table treatment have been translated into the web stylesheet.

## Java-first changes in this milestone
- Added `CatalogueService`: Java-owned catalogue retrieval, normalization, multi-field search and stable ordering.
- Added `FitmentService`: Java-owned conservative fitment evaluation with explicit `INDICATIVE`, `NOT_MATCHED`, and `INSUFFICIENT_DATA` outcomes. A model association is never presented as confirmed trim/engine fitment.
- Updated `ProductController` to delegate catalogue search to the service instead of embedding business rules in the controller.
- Translated the Beta 0.1 blue/graphite visual system into the web CSS while retaining existing Thymeleaf templates and Spring Boot routes.

## Still required
- Persisted generation/variant/engine/transmission records and verified fitment application tables.
- Supplier accounts, quotation requests and role-secured workflows.
- Replacing illustrative image mappings with licensed, vehicle-/SKU-specific imagery.
- Tests and local Maven build verification. Maven is not executable in this build environment, so compile status is not claimed.

## Phase 6 refinement (12 Nov 2026)
See `IMPLEMENTATION-PHASE-6.md` for the vehicle studio and guided walkthrough rebuild. The key changes are independent camera presets, separate interactive system assemblies, persistent clickable markers, system-specific walkthrough content, component inspection actions, keyboard navigation, bottom-docked viewer controls, and contrast fixes based on the supplied screenshots.
