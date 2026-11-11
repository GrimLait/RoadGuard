# RoadGuard 🛡️

> **Intelligent Road Surface Defect Detection System** powered by YOLO, FastAPI, and React.

---

### 🎓 Academic Context
This repository contains the practical implementation of the **Bachelor's Thesis**.
* **Institution:** Ivan Franko National University of Lviv (Львівський національний університет імені Івана Франка)
* **Author:** Nazarii Hreb ([@GrimLait](https://github.com/GrimLait))
* **Academic Year:** 2024–2025

---

## 📌 Project Overview
**RoadGuard** is an automated platform designed to collect, verify, and monitor road pavement defects (potholes, cracks, etc.). 

Key architectural highlights:
* **Computer Vision Core:** Real-time object detection using **YOLO** with an integrated **Double-Threshold Algorithm**:
  * `< 15%` — Automatic spam/noise filtering.
  * `15% – 84%` — Uncertainty zone routed to human moderation.
  * `>= 85%` — High-confidence automated confirmation.
* **Smart Moderation:** Box-level moderation with soft-delete capabilities (`is_valid`) to preserve hard negatives for model retraining.
* **Role-Based Access:** Distinct workflows for *Citizens* (standard verification) and *Road Workers* (trusted pre-approved publishing with background data markup).
* **Interactive Geo-Map:** Dynamic visualization of active defect reports.

---

## 🛠️ Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend** | React (Vite, TypeScript), Tailwind CSS, Leaflet (OpenStreetMap) |
| **Backend API** | Python 3.11+, FastAPI, SQLAlchemy, Pydantic |
| **AI / Computer Vision** | YOLOv8 / YOLOv11 (PyTorch) |
| **Database** | PostgreSQL 16 + PostGIS (Geospatial queries) |
| **DevOps / Infra** | Docker, Docker Compose |

---

## 📁 Repository Structure

```text
RoadGuard/
├── backend/          # FastAPI server, business logic & YOLO inference engine
├── frontend/         # React SPA (Citizen portal & Moderation dashboard)
├── ml_research/      # Model training scripts, datasets & augmentation research
├── docs/             # Technical specifications, diagrams & architecture records
├── docker-compose.yml# Container orchestration setup
└── README.md         # Project entry point

---

## 📄 Documentation (Документація)

Повна проєктна документація українською мовою знаходиться в директорії [`/docs`](./docs):

1. **[System Architecture (architecture.md)](./docs/architecture.md)** — Детальний опис архітектурних рішень та обґрунтування стеку.
2. **[SRS & Use-Case Specification (PDF)](./docs/roadguard_documentation.pdf)** — Повна специфікація вимог, діаграми прецедентів, ERD та послідовності.

---

## 📝 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
