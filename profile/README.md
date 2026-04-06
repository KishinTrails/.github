<p align="center">
  <img src="logo.png" alt="Kishin Trails Logo" width="200"/>
</p>

# Kishin Trails

## ⚠️ WARNING: Under Heavy Development ⚠️

**This project is currently under active and heavy development. It is NOT ready for general use and may contain bugs, incomplete features, or breaking changes. Use at your own risk.**

Kishin Trails is a mobile-first application for exploring and tracking hiking trails with fog-of-war exploration mechanics. It provides an interactive map interface for discovering points of interest while tracking your explored areas using H3 geospatial indexing.

---

## ✨ Features

- **Interactive Map**  
  MapLibre GL-based map with OpenStreetMap tiles for smooth navigation
- **Fog of War**  
  Track explored areas with H3 geospatial indexing (Uber's hexagonal spatial index)
- **POI Markers**  
  Display points of interest including peaks, natural areas, and industrial zones
- **Authentication**  
  JWT-based login/logout with protected routes
- **Offline Caching**  
  LocalStorage persistence for POI data
- **Mobile Ready**  
  Ionic Framework UI with Capacitor for Android builds
- **Dark Mode**  
  System-aware dark theme support

---

## 🧠 Technology Stack

| Component | Technology |
|-----------|------------|
| Frontend  | Vue 3, TypeScript 5, Ionic 8, Vite 7, MapLibre GL |
| Backend   | FastAPI, Python, SQLAlchemy, GeoPandas, Shapely |

---

## 📂 Projects

- [Kishin Trails Frontend](https://github.com/KishinTrails/kishin-frontend) — Mobile-first Vue 3 application with Ionic UI
- [Kishin Trails API](https://github.com/KishinTrails/kishin-api) — FastAPI backend for OSM data and geo-spatial operations

---

## CHANGELOG

- [CHANGELOG](CHANGELOG.md)

---

## 🧪 Quality and Testing

Kishin Trails uses **AI-assisted development** tools to accelerate coding, followed by **human validation** and **automated tests** for correctness.

**Frontend Testing:**
- Vitest for unit tests
- Cypress for e2e tests
- ESLint + TypeScript for code quality

**Backend Testing:**
- Pytest with pytest-asyncio
- Coverage reporting
- In-memory SQLite for test isolation

---

## 📜 License

This project is released under the [MIT License](LICENSE).

---

*© 2026 Kishin Trails. Built with care, code, and a spirit to explore.*
