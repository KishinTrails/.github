<p align="center">
  <img src="logo.png" alt="Kishin Trails Logo" width="200"/>
</p>

# Kishin Trails

## ⚠️ WARNING: Under Heavy Development ⚠️

**This project is currently under active and heavy development. It is NOT ready for general use and may contain bugs, incomplete features, or breaking changes. Use at your own risk.**

Kishin Trails is a mobile-first application for exploring and tracking hiking trails with fog-of-war exploration mechanics. Its map reveals the S2 cells you have walked through and the points of interest in them; its athlete pages show your Garmin activities, body measurements and the progression of a training plan.

---

## ✨ Features

- **Map**  
  MapLibre GL map in three styles, with fog of war over the S2 cells not yet explored
  (Google's S2 geometry library)
- **POI Markers**  
  Points of interest from OpenStreetMap: peaks, natural areas, and industrial zones
- **GPS Tracking**  
  In the Android app, a background service records each newly explored cell
- **Athlete Pages**  
  Garmin activities with their maps and charts, and Withings body measurements
- **Training Plan**  
  Week-by-week progression of a plan, each training completed by a Garmin run
- **Single Account**  
  JWT login for the one account the server is configured with
- **Mobile Ready**  
  Ionic Framework UI with Capacitor for Android builds

---

## 🧠 Technology Stack

| Component | Technology |
|-----------|------------|
| Frontend  | Vue 3, TypeScript 5, Ionic 8, Vite 7, MapLibre GL |
| Backend   | FastAPI, Python, SQLAlchemy, PostgreSQL, GeoPandas, Shapely, S2 |

---

## 📂 Projects

- [Kishin Trails Frontend](https://github.com/KishinTrails/kishin-frontend) — Mobile-first Vue 3 application with Ionic UI
- [Kishin Trails API](https://github.com/KishinTrails/kishin-api) — FastAPI backend for OSM data, explored cells, athlete data and training plans

---

## CHANGELOG

- [CHANGELOG](CHANGELOG.md)

---

## 🧪 Quality and Testing

Kishin Trails uses **AI-assisted development** tools to accelerate coding, followed by **human validation** and **automated tests** for correctness.

**Frontend Testing:**
- Vitest for unit tests
- ESLint + TypeScript for code quality

**Backend Testing:**
- Pytest with pytest-asyncio
- Coverage reporting
- A throwaway PostgreSQL container per test run
- Pylint and ty for code quality

---

## 📜 License

This project is released under the [PolyForm Noncommercial License 1.0.0](LICENSE). Any
noncommercial purpose is permitted, which the licence spells out as including personal
study, hobby projects and use by charities, schools, public research organisations and
government bodies. It grants no licence for commercial use. The `LICENSE` file is the
terms; this paragraph is not.

---

*© 2026 Kishin Trails. Built with care, code, and a spirit to explore.*
