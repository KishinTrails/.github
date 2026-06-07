# Changelog

All notable changes to the Kishin Trails project will be documented in this file.

---

## [0.2.1] - 2026-06-07 - "The Beautify Mini-Update"

### ✨ Added

#### Frontend
- `mapStyleService` — persists the chosen map style to `localStorage` and exposes a shared `styleToThemeClass()` helper used by both the map and login pages
- Collapsible controls panel: hidden by default on mobile viewports (<768 px), with a floating `☰` toggle button and an in-panel `✕` close button
- Login page now reads the stored map style on mount and applies the matching theme

### 🔄 Changed

#### Frontend
- Map style selector replaced with a `<select>` dropdown (was radio buttons)
- Controls panel restyled using CSS custom properties organised into `theme-standard` and `theme-ukiyo` token sets, so the panel colours update automatically when the map style changes
- Ukiyo-e Toner is now the default map style (persisted across sessions)
- `initMap` now reads `STYLE_MAP[mapStyle]` instead of hardcoding `STANDARD_STYLE`, so the correct tiles load on first render

---

## [0.2.0] - 2026-05-31 - "The Exploration Update"

### 💥 Breaking Changes

- Replaced H3 hexagonal cell indexing with **Google's S2 geometry library** across both frontend and backend. All cell identifiers are now S2 hex token strings (e.g., `89c25a221`). Existing explored-cell records using H3 IDs are incompatible.

### ✨ Added

#### Frontend
- `s2Utils` library for S2 cell ↔ lat/lon conversion and cell boundary polygon generation
- Android GPS tracking now works when the screen is off (Capacitor background location)
- Android app streams newly explored S2 cells to the backend in real time

#### Backend
- `POST /trails/explored` endpoint to record a newly explored S2 cell
- Docker image with full CI/CD deployment pipeline

### 🔄 Changed

#### Frontend
- Fog overlay, POI overlay, Perlin noise overlay, and tile selection all migrated to S2
- Wake lock replaced with Fused Location Provider (FLP)-managed CPU waking for better battery life
- Location update intervals split between foreground and background modes
- `updateVisibleCells` skipped while in active explore mode to reduce redundant redraws
- Professional TSDoc docstrings added across all service, composable, utility, and plugin files

#### Backend
- Full S2 migration across all modules: cache, Overpass queries, trails router, `import_gpx`, `debug_geo`, `find_perlin_params`

### 🐛 Fixed

#### Frontend
- `PoiOverlay` now handles invalid S2 cell IDs gracefully
- Removed duplicate `cellFromLatLng` definition in `s2Utils`
- Corrected Android Kotlin package declarations

#### Backend
- Inverted lat/lng in Overpass API response parsing
- Inverted coordinates in cell-from-polygon S2 computation
- CORS configuration not applied correctly on startup
- Multiple cell conditions not handled correctly in `find_perlin_params`

### 🧪 Testing

#### Backend
- Updated test suite for S2 cell identifiers (trails, cache idempotency, S2 utilities)

### 📝 Notes

- S2 cells are always stored and transmitted as hexadecimal token strings, never as raw `uint64` IDs
- The Docker image pins `s2geometry` from source (no PyPI release) — build times are longer than typical Python images

---

## [0.1.0] - 2026-04-06 - "The Visualization Update"

### ✨ Added

#### Frontend
- Canvas-based fog-of-war rendering with H3 hexagonal cells
- POI overlay system with dynamic icon rendering (peaks, natural areas, industrial zones)
- Real-time viewport statistics (explored cells, visible fog coverage)
- Debounced map movement updates to limit API calls
- Signed Android APK build script with keystore configuration

#### Backend
- POI caching layer to reduce Overpass API queries
- GPX import script for trail data population
- Debug utilities for geospatial operations
- Tile population script for cache pre-seeding

#### Infrastructure
- GitHub Actions CI pipelines for both repositories
- Automated linting, type checking, and test execution
- Coverage reporting for backend tests

### 🧪 Testing

#### Frontend
- Unit tests for all service modules (auth, cache, POI, trails)
- Component tests for FogOverlay and PoiOverlay
- Composable tests for useTrailMap logic
- Utility function tests (color helpers)

#### Backend
- Test suite for Overpass integration
- POI transformation and filtering tests
- Security module tests (JWT, password hashing)
- Trail tracking endpoint tests
- Utility function tests (H3 operations, value sanitization)

### 📝 Notes

- This is the first milestone release focusing on core visualization features
- Both projects remain under active development (0.x.x versioning indicates pre-1.0 stability)
- Fog-of-war mechanic uses canvas overlays with H3 cell masking
- POI system prioritizes peaks, then natural/industrial features per cell
- Backend caches all POI data to minimize external API dependencies
