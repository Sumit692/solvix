# ☀️ Solvix

### AI-Powered Renewable Energy Planning & Site Analysis Platform

**Solvix** is an intelligent renewable energy planning platform that helps landowners and farmers understand the renewable energy potential of their land and design optimized solar, wind, and energy-storage systems.

Instead of relying on complex engineering tools or expensive initial consultations, Solvix combines **interactive maps, geospatial analysis, weather and solar data, 3D terrain visualization, financial modeling, and AI-assisted optimization** into one platform.

> **See what your land can power.**

---

## 🚀 Live Demo

🌐 **[solvix-energy.vercel.app](https://solvix-energy.vercel.app)**

---

## 🎯 Problem

Planning a renewable energy installation is not as simple as choosing a few solar panels.

Landowners need to consider:

* ☀️ Solar irradiance and sunlight availability
* 🌬️ Wind potential
* 🗺️ Land area and terrain
* ⛰️ Elevation and slope
* 🏠 Existing structures and usable areas
* 🔋 Energy-storage requirements
* ⚡ Grid connection
* 💰 Installation cost and expected savings
* 📊 Energy production
* 🌱 Environmental impact
* 📍 Location-specific information

Traditional feasibility studies can require multiple tools, datasets, and expert consultations.

**Solvix brings these stages together into a single interactive workflow.**

---

# ✨ Key Features

## 🗺️ Interactive Land Selection

Users can select their land directly on an interactive map.

* Search for a location
* Draw a polygon around the property
* Calculate approximate land area
* View geographic coordinates
* Analyze the selected site
* Visualize the selected region

Built using **Leaflet + React Leaflet + Leaflet Draw**.

---

## 🤖 AI-Assisted Energy Planning

Solvix includes an agent-style analysis workflow that processes the selected site and user requirements.

The analysis workflow is divided into stages:

1. **Data Collection**
2. **Constraint Integration**
3. **Technology Optimization**
4. **System Design**
5. **Financial Modeling**

The interface presents the analysis progressively so users can understand what the system is doing instead of receiving only a final number.

---

## ⛰️ 3D Terrain Visualization

Solvix converts geographic elevation information into a 3D terrain representation.

The system:

* Generates an elevation grid
* Retrieves elevation data
* Builds terrain geometry
* Visualizes the site in 3D
* Displays potential placement zones
* Provides an interactive terrain experience

Powered by:

* **Three.js**
* **React Three Fiber**
* **@react-three/drei**
* **Open-Meteo Elevation API**

---

## ☀️ Solar & Weather Analysis

The platform retrieves location-specific environmental data to estimate renewable energy potential.

The site-analysis pipeline considers:

* Solar radiation
* Global tilted irradiation
* Direct normal irradiance
* Cloud coverage
* Temperature
* Precipitation
* Wind speed
* Peak sun hours

Weather and solar information is retrieved through **Open-Meteo**.

---

## 🌬️ Renewable Technology Analysis

Solvix supports different renewable technology configurations including:

* ☀️ Solar
* 🌬️ Wind
* 🔋 Battery Storage
* 💧 Micro-hydro

Users can define their technology preferences and constraints before running the analysis.

---

## 💰 Financial & Energy Modeling

The platform provides a detailed view of the expected system performance.

The dashboard can present metrics such as:

* System capacity
* Annual energy production
* Investment requirements
* Payback period
* Annual savings/revenue
* CO₂ reduction
* Production trends
* Cost breakdown
* Cash-flow projections

The analytics interface uses **Recharts** for interactive visualizations.

---

## 📊 Analytics Dashboard

Solvix provides multiple analytics views.

### Production

* Daily production
* Monthly production
* Annual projections
* Production trends
* Weather-related impact

### Financial

* Cost breakdown
* Cash-flow projection
* Payback timeline
* Financing scenarios
* Incentive analysis

### Environmental

* CO₂ reduction
* Environmental impact
* Renewable energy contribution

---

## 🧠 AI Energy Architect

Solvix includes an agent-oriented optimization workflow designed to help generate renewable energy configurations based on user requirements.

Users can provide constraints such as:

### Financial

* Budget
* Financing preference
* Payback priority

### Energy

* Energy goal
* Target production
* Grid connection

### Land

* Existing structures
* Land usage
* Restricted areas

### Technical

* Solar
* Wind
* Storage
* Hydro
* Maintenance requirements
* Aesthetic preferences

### Timeline

* ASAP
* This year
* Next 1–2 years
* Exploring

The system then uses these constraints as part of the site-analysis and optimization workflow.

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │      Solvix UI      │
                         │   Next.js + React   │
                         └──────────┬──────────┘
                                    │
                ┌───────────────────┼───────────────────┐
                │                   │                   │
                ▼                   ▼                   ▼
        ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
        │ Interactive  │    │   Analysis   │    │   3D Terrain │
        │     Maps     │    │    Engine    │    │ Visualization│
        │   Leaflet    │    │  Next API    │    │ Three.js/R3F │
        └──────┬───────┘    └──────┬───────┘    └──────┬───────┘
               │                   │                   │
               └───────────────────┼───────────────────┘
                                   │
                     ┌─────────────┴─────────────┐
                     │       External Data       │
                     ├───────────────────────────┤
                     │ Open-Meteo                │
                     │ Mapbox                    │
                     │ Nominatim / OpenStreetMap │
                     │ Utility APIs              │
                     │ AI / Optimization APIs    │
                     └───────────────────────────┘
```

---

# 🛠️ Tech Stack

## Frontend

* **Next.js 16**
* **React 19**
* **TypeScript**
* **Tailwind CSS 4**
* **shadcn/ui**
* **Framer Motion**
* **Zustand**
* **Lucide React**

## Maps & Geospatial

* **Leaflet**
* **React Leaflet**
* **Leaflet Draw**
* **Mapbox**

## 3D Visualization

* **Three.js**
* **React Three Fiber**
* **@react-three/drei**

## Data Visualization

* **Recharts**

## AI & APIs

* **OpenAI SDK**
* AI optimization workflow
* **Open-Meteo APIs**
* Utility tariff API integration
* Roof segmentation API integration

## Authentication

* **Auth0**
* `@auth0/nextjs-auth0`
* JWT / authentication utilities

## State Management

* **Zustand**

---

# 📂 Project Structure

```text
solvix/
│
├── app/
│   ├── api/
│   │   ├── agent/
│   │   │   └── optimize/
│   │   ├── auth/
│   │   ├── roof-segmentation/
│   │   ├── site-analysis/
│   │   ├── terrain/
│   │   │   ├── elevation/
│   │   │   └── placements/
│   │   └── utility-tariff/
│   │
│   ├── area-select/
│   ├── home/
│   ├── login/
│   ├── overview/
│   ├── register/
│   ├── layout.tsx
│   └── page.tsx
│
├── components/
│   ├── 3d/
│   ├── agent/
│   ├── analytics/
│   ├── auth/
│   ├── constraints/
│   ├── home/
│   ├── landing/
│   ├── layout/
│   ├── map/
│   ├── overview/
│   └── ui/
│
├── hooks/
│
├── lib/
│   ├── auth/
│   ├── mock-data.ts
│   ├── placements.ts
│   └── utils.ts
│
├── stores/
│   ├── auth-store.ts
│   ├── plan-store.ts
│   └── ui-store.ts
│
├── types/
│
├── PRD.md
├── LEARNINGS.md
├── TASK_TRACKER.md
├── package.json
└── README.md
```

---

# 🔄 User Workflow

```text
Landing Page
      │
      ▼
Login / Register
      │
      ▼
Home Dashboard
      │
      ▼
Select New Plan
      │
      ▼
Select Land on Map
      │
      ▼
Define Constraints
      │
      ▼
AI Site Analysis
      │
      ├── Terrain Analysis
      ├── Solar Analysis
      ├── Wind Analysis
      ├── Technology Optimization
      └── Financial Modeling
      │
      ▼
3D Site Visualization
      │
      ▼
Renewable Energy Plan
      │
      ▼
Overview
      │
      ├── Analytics
      ├── Financial Analysis
      └── Environmental Analysis
```

---

# 🔌 API Routes

Solvix uses Next.js API routes for its backend functionality.

| Endpoint                  | Purpose                                                |
| ------------------------- | ------------------------------------------------------ |
| `/api/site-analysis`      | Performs location, weather, solar and site analysis    |
| `/api/terrain/elevation`  | Retrieves elevation data for the selected region       |
| `/api/terrain/placements` | Streams renewable placement zones                      |
| `/api/roof-segmentation`  | Processes roof suitability information                 |
| `/api/utility-tariff`     | Retrieves/estimates location-based electricity tariffs |
| `/api/agent/optimize`     | Runs the optimization workflow                         |
| `/api/auth/login`         | Authentication                                         |
| `/api/auth/signup`        | User registration                                      |
| `/api/auth/logout`        | Logout                                                 |
| `/api/auth/session`       | Session information                                    |
| `/api/auth/callback`      | Authentication callback                                |

---

# 🌍 External Data Sources

Solvix is designed around location-aware renewable analysis.

### Open-Meteo

Used for:

* Weather information
* Solar radiation
* Irradiance
* Wind speed
* Elevation

### OpenStreetMap / Nominatim

Used for:

* Reverse geocoding
* Location identification

### Mapbox

Used for:

* Satellite imagery
* Map visualization

### Utility Tariff Providers

The application supports provider-backed tariff lookup with fallback estimation when an external provider is unavailable.

---

# ⚙️ Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/solvix.git

cd solvix
```

## 2. Install Dependencies

```bash
npm install
```

## 3. Configure Environment Variables

Create a `.env.local` file in the project root.

Example:

```env
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Mapbox
MAPBOX_TOKEN=your_mapbox_token
NEXT_PUBLIC_MAPBOX_TOKEN=your_mapbox_token

# Auth0
AUTH0_DOMAIN=your_auth0_domain
AUTH0_CLIENT_ID=your_auth0_client_id
AUTH0_CLIENT_SECRET=your_auth0_client_secret
NEXT_PUBLIC_AUTH0_DOMAIN=your_auth0_domain
NEXT_PUBLIC_AUTH0_CLIENT_ID=your_auth0_client_id

# AI
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=your_model

# Roof Segmentation - optional
ROOF_SEGMENTATION_API_URL=
ROOF_SEGMENTATION_API_KEY=
ROOF_SEGMENTATION_PROVIDER=

# Utility Tariff API - optional
UTILITY_TARIFF_API_URL=
UTILITY_TARIFF_API_KEY=
```

> Never commit API keys or secrets to GitHub.

## 4. Start the Development Server

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

---

# 📱 Application Modules

### Landing Page

Introduces Solvix and explains the renewable planning workflow.

### Authentication

Provides login and registration interfaces with Auth0 integration.

### Dashboard

Users can manage their renewable energy plans.

Features include:

* Search
* Filtering
* Sorting
* Grid/List view
* Plan status
* Plan deletion

### Area Selection

Users select their property using the interactive map.

### Constraints

Users define their:

* Budget
* Energy goals
* Technology preferences
* Land constraints
* Financing preferences
* Timeline

### AI Analysis

The agent workflow analyzes the selected site and constraints.

### Overview

Provides the final renewable energy plan and major metrics.

### Analytics

Provides production, financial and environmental analysis.

---

# 🔐 Security Considerations

The project includes authentication and agent permission checks.

The optimization endpoint supports delegated permission scopes such as:

```text
read:finance
read:energy_history
```

Requests without the required permission scope are rejected.

For production deployment:

* Store secrets using environment variables
* Enable proper Auth0 configuration
* Restrict API access
* Validate all external API responses
* Add rate limiting
* Avoid exposing private API keys to the client
* Replace demo/fallback calculations with verified production data sources

---

# 📈 Current Project Status

### Implemented

* [x] Landing page
* [x] Authentication UI
* [x] Dashboard
* [x] Plan management
* [x] Interactive map
* [x] Land selection
* [x] Constraint configuration
* [x] Site analysis API
* [x] Weather & solar analysis
* [x] Elevation analysis
* [x] 3D terrain visualization
* [x] Renewable placement visualization
* [x] AI/agent analysis workflow
* [x] Analytics dashboard
* [x] Production charts
* [x] Financial charts
* [x] Environmental analysis
* [x] Utility tariff integration
* [x] Roof segmentation integration
* [x] Responsive UI
* [x] Animated interactions

### Future Improvements

* [ ] Production-grade renewable simulation models
* [ ] Real utility interconnection data
* [ ] More accurate financial modeling
* [ ] Automated BOM generation
* [ ] Permit and compliance workflows
* [ ] PDF report generation
* [ ] Advanced solar panel placement optimization
* [ ] Real-time utility pricing
* [ ] Precision agriculture integration
* [ ] IoT sensor integration for irrigation and crop monitoring

---

# 💡 Why Solvix?

Solvix focuses on making renewable energy planning **visual, interactive, and understandable**.

Instead of presenting users with spreadsheets and disconnected engineering tools, the platform combines:

**Location → Data → Terrain → AI → Energy System → Financial Analysis**

into one workflow.

---

# 👨‍💻 Team

Built by:

* **Raj**
* **Sumit**
* **Shashank**

### Track

🌱 **Renewables**

---

# 🏆 Project Vision

> **From land to energy — intelligently.**

Solvix aims to make renewable energy planning more accessible by turning complex geospatial, technical, and financial analysis into an interactive digital experience.

---

## ⭐ If you find this project interesting

Give the repository a ⭐ and feel free to explore, fork, and contribute.

---
