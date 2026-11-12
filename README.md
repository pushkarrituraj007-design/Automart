# AutoMart — Automotive Parts Discovery Marketplace

A Java 17 + Spring Boot 3 + Thymeleaf application combining the richer web marketplace from `autoparts-marketplace.zip` with the JavaFX parts-intelligence/data model from `AutoMart-Beta-0.1.zip`. The Spring Boot application is the runnable primary experience; the original JavaFX project and its MySQL schema/sample dataset are preserved under `reference-javafx/` and `database/` for reference.

## Run locally

1. Install JDK 17+ and Maven 3.8+.
2. From this directory run `mvn spring-boot:run`.
3. Open http://localhost:8080.
4. H2 console (development only): http://localhost:8080/h2-console — JDBC URL `jdbc:h2:mem:autopartsdb`, user `sa`, blank password.

## Latest interface work\n\nSee `IMPLEMENTATION-PHASE-5.md` for the latest product and design overhaul. The main discovery pages now use a consistent editorial automotive system, compact search, practical catalogue cards, cleaner vehicle profiles and a paired photo/concept-model explorer.\n\n## What is included

- Discovery catalogue across car and motorcycle categories, brands and vehicle families.
- Product detail pages with specifications/fitment caution and outbound official brand links.
- Search, category/brand/vehicle browsing, login/register demo, admin catalogue screens and legacy cart routes retained in the codebase.
- Browser-local shortlist, responsive horizontal rails, scroll reveal motion, warm glass surfaces and page-specific accent palettes.
- JavaFX source, JDBC repository and original MySQL schema/sample data retained in `reference-javafx/` and `database/`.

## Important catalogue truthfulness

This is a **discovery / referral prototype, not a seller**. It does not process orders or payments and must not imply live stock, live prices, product reviews, warranty coverage, fitment verification or manufacturer authorisation. Synthetic ratings, stock counts and sale prices were removed from seeded listings. Images currently use editorial category photography from Unsplash, not guaranteed exact SKU packshots; replace these with manufacturer-approved product assets before public launch. Product names are catalogue-style examples and official links currently lead to brand websites, not necessarily an exact product SKU page. Verify every part number, compatibility, image licence, product claim and destination URL with the manufacturer or authorised distributor before publishing.

## Demo access

- Admin: `admin@autoparts.com` / `admin123`
- Customer: `demo@autoparts.com` / `demo123`

**Security warning:** the supplied authentication is a classroom demo with simplified password handling. Do not deploy publicly without Spring Security, password hashing, CSRF-safe flows, validation, rate limiting, secrets management and production database configuration.

## Next production upgrades

1. Manufacturer/authorised-distributor product feed ingestion and source refresh timestamps.
2. Exact fitment catalogue keyed by make/model/year/variant/engine and verified part numbers.
3. Real product packshots with documented image rights.
4. OAuth/Spring Security, account-backed garage and saved comparisons.
5. Affiliate/referral tracking and clear disclosure, while outbound checkout remains on the source site.
6. Search indexing, accessibility testing, analytics consent and automated tests.
