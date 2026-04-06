# Changelog

All notable changes to the Kishin Trails project will be documented in this file.

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
