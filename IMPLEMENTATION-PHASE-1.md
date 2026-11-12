# AutoMart reconstruction — Phase 1

## Implemented in this build

- `/` now redirects to `/login`; registration and login are the public entry points.
- All application routes require an authenticated session. Static CSS/JS and authentication endpoints remain public.
- New account passwords are stored with BCrypt. Existing demo/seed passwords are accepted once and upgraded to BCrypt at next successful login.
- Authentication screens use a dedicated editorial layout and no longer display the application navigation or homepage behind the login form.
- `/shortlist` is now a dedicated page. It reads saved product IDs from the existing browser shortlist and resolves their catalogue data through `/shortlist/items`.
- `/vehicles/{id}/tour` provides a separate guided tour experience with Exterior, Interior, Mechanical and Electrical sections and interactive hotspot selections.
- The Vehicle Intelligence canvas now renders a motorcycle silhouette for the seeded motorcycle models and different body proportions for SUV/sedan/hatchback-style cars. This remains a conceptual model, not OEM CAD.
- Vehicle detail pages link to the guided tour.
- Category imagery has been remapped to relevant component imagery where a suitable source was available. Where a dependable category image was not available, a clearly labelled neutral placeholder is used rather than an unrelated engine/car/mechanic photograph.
- Chain and sprocket kits are classified under the new Drivetrain category rather than Engine Parts.
- Removed unsupported claims that seeded vehicle parts are direct-fit and tested for Indian road/climate conditions.
- Added distinct accent treatments for the home, shop, categories, brands and vehicle workspaces, plus readability corrections.

## Important limitations

- The guided tour is a functional first-stage information architecture, not a true 360-degree photo sphere. It currently uses the vehicle's existing editorial image and changes the guided system/hotspot information. Exact 360 exterior/interior captures and licensed vehicle-specific 3D/CAD assets are still required.
- The vehicle models in the Three.js viewer are conceptual category silhouettes. They distinguish motorcycles from cars and vary the general car proportions, but are not accurate representations of each named model or generation.
- Exact variant, year, engine-code and OEM fitment data is not present in the current database. The app must continue to describe fitment as indicative until verified applications are added.
- Some category images remain neutral labelled placeholders pending appropriate photography. No unrelated image is substituted to make a category appear populated.
- Build verification was not possible in this environment because Maven is not installed. Run `mvn -DskipTests package` on the Mac before launching.

## Run locally

```bash
mvn -DskipTests package
mvn spring-boot:run -Dspring-boot.run.arguments=--server.port=8081
```

Open `http://localhost:8081`. First route is `/login`.

Seeded demo access (for local development only):
- `demo@autoparts.com` / `demo123`
- `admin@autoparts.com` / `admin123`

Change or remove demo credentials before any public deployment.
