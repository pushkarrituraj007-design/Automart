# AutoMart — Phase 5 product experience overhaul

## Product and visual direction

Reworked the main discovery journey around a restrained workshop/editorial identity: warm paper surfaces, graphite navigation, muted mechanical greens and a small signal-orange accent. The previous oversized icon treatments, glass-heavy panels, gradient headlines and unrelated page banners are no longer the primary design language.

## Main experience changes

- Rebuilt the home page around three genuine entry routes: vehicle, component system and manufacturer. Reduced the search field to a compact, focused control and added a small catalogue feature rail.
- Replaced category tiles with photographic system cards and a consistent index/count treatment.
- Replaced oversized brand tiles with a compact manufacturer index showing specialisation and catalogue count.
- Rebuilt the vehicle directory with a practical search/filter toolbar and model cards that prioritise the vehicle image and name.
- Reworked vehicle profiles to remove the excessive configuration boilerplate and repeated warnings. The page now leads with the vehicle, a concise profile, an interactive conceptual model, a photo reference, direct system links and associated parts.
- Updated the guided explorer to show both the vehicle photo reference and an interactive conceptual model. Component groups now lead directly to relevant catalogue searches.
- Rebuilt product cards and detail pages around the component name, manufacturer, system, application and manufacturer destination. Removed first-impression labels such as “UNVERIFIED” and internal catalogue terminology from product cards.
- Replaced promotional sample descriptions with practical identification notes. Tyre sizes, battery capacities, oil grades and named component types are surfaced without inventing compatibility.
- Changed home featured ordering to use newest record IDs rather than unverified rating values.
- Reduced the global navigation search width and tightened its presentation.

## Implementation approach

The application remains Java 17, Spring Boot, Spring MVC, Thymeleaf and JPA. Server-rendered routes, catalogue associations, counts, filtering inputs and seeded copy stay in Java/Thymeleaf. JavaScript is limited to browser interactions: catalogue sorting, vehicle directory filtering, shortlist behavior and the Three.js conceptual viewer.

## Known constraints

- The 3D viewer is procedural concept geometry, not an OEM CAD model or dimensional digital twin. It now has a more useful side-first view for motorcycles, front/side/rear presets and a real editorial photo beside the model.
- Vehicle and part images remain editorial/category references. They are not guaranteed exact SKU photography or trim-specific vehicle imagery.
- Catalogue associations are still not verified fitments. Exact year, generation, engine, trim and part number must be confirmed with the manufacturer or seller.
- The application remains a discovery/referral prototype; live stock, live pricing, warranty and checkout are not represented as verified services.

## Validation

- `node --check` passed for all static JavaScript files.
- `pom.xml` parsed as valid XML.
- Changed Java files were checked for syntax-level diagnostics with `javac`; full compilation/runtime testing was not possible because Maven is not installed in the execution environment.
