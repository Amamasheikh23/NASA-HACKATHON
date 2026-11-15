# TerraAnalog — Earth Analog Discovery Lab

**Team:** NOVA FIVE  
**Challenge:** NASA Space Apps Challenge — *Earth as a Laboratory*

TerraAnalog is an interactive planetary analog discovery dashboard that compares terrestrial field sites against candidate Moon-base and Mars exploration targets across eight geological, environmental, and operational dimensions.

---

## Team — NOVA FIVE

| Role | Team Member | Focus Area |
| :--- | :--- | :--- |
| Project Leader & Research Coordinator | `[Hammad Qureshi]` | `[Role / Contribution, e.g., Planetary Science & Analog Research]` |
| Frontend Developer | `[Wania Mobin]` | `[Role / Contribution, e.g., Frontend Engineering & Mapping]` |
| Data Analyst | `[AMAMA SHEIKH]` | `[Role / Contribution, e.g., NASA POWER Data Integration]` |
| GIS & Mapping Specialist | `[Fatima Muhammad Yameen]` | `[Role / Contribution, e.g., UI/UX & Visualization]` |
| Documentation & Presentation Lead  | `[Fiza Zehra]` | `[Role / Contribution, e.g., Documentation & Presentation]` |

*(Replace placeholders above with individual team member names and roles prior to final submission.)*

---

## Application Views & Capabilities

### 1. Discovery Lab
- **Mission Target Selector:** Choose among **5 Moon targets** and **2 Mars targets** with orbital imagery, mission summary, temperature, and surface gravity.
- **Analog Site Scope Filter:** Filter surveyed Earth candidates by `All` (12 sites), `Moon`, or `Mars`.
- **Interactive Mission Weight Sliders:** Tune each of the 8 dimensions (`0.00×` to `1.50×`) to test how prioritizing geology, slope, thermal extremes, water/ISRU, subsurface shelter, dust, biosignatures, or mobility shifts the ranking. Each slider explicitly displays its data provenance.
- **Ranked Table & Site Dossier:** Displays ranked match score, Cosine/Euclidean breakdown, estimated slope, match tier (`High Fidelity`, `Partial Match`, `Low Fidelity`), live NASA POWER climate telemetry, *"Useful for"* mission notes, *"Where the analogy breaks down"* limits, an **8-axis SVG radar comparison chart**, an embedded **satellite mini-map**, and **CSV export**.

### 2. Global Map
- **Dual-Provider Interactive Mapping:** Uses **Google Maps Platform** (`@vis.gl/react-google-maps`) when `VITE_GOOGLE_MAPS_API_KEY` is configured and automatically switches to an interactive **Leaflet + Esri** fallback (`World_Imagery`, `World_Boundaries_and_Places`, `World_Topo_Map`) when no key is set or Google Maps fails to load—without any blocking configuration error. A non-blocking corner badge indicates the active map provider.
- **Map Modes:** Supports **Hybrid**, **Satellite**, and **Terrain** views in both Google Maps and the Leaflet fallback.
- **Surveyed Site Pins:** Color-coded markers scaled by current match ranking; clicking a marker or sidebar item pans to the site and displays its match summary.
- **Live Hover Inspection:** Moving the cursor over any region displays **Latitude**, **Longitude**, resolved **Country**, and live **NASA POWER climate category** (`Strong analog`, `Moderate analog`, or `Weak analog`) for the selected Moon or Mars target.
- **Click-Anywhere Climate Lookup:** Clicking any point on Earth queries the **NASA POWER Climatology API** in real time, displays climate classification, temperature, annual swing, precipitation, pressure, analog category, and computes Haversine distance to the nearest surveyed analog site.

### 3. Moon & Mars
- **Solar System Visual Context:** Full uncropped orbital imagery of **Earth**, **the Moon**, and **Mars**, plus overview cards for **Mercury, Venus, Jupiter, Saturn, Uranus, and Neptune**.
- **Three Worlds Comparison Table:** Compares radius, surface gravity, atmosphere, temperature, day length, signal delay, magnetic field, water availability, and dust/soil across Earth, the Moon, and Mars.
- **Candidate Target Cards:** Summarizes all 7 Moon and Mars targets with one-click deep links back into the Discovery Lab.

### 4. Scientific Brief
- Summarizes the research question, transparent 8-axis data provenance, live NASA POWER site load count, the *Kharan-Chagai (Balochistan)* hypothesis case study, physical limits of Earth analogs, Team NOVA FIVE's AI-use disclosure, and future raster-integration steps.

---

## Surveyed Locations & Planetary Targets

### 12 Earth Analog Locations

| Site | Region | Focus | Coordinates |
| :--- | :--- | :--- | :--- |
| Atacama Desert - Yungay | Chile | Mars | `-24.10°, -69.90°` |
| Antarctic Dry Valleys - Wright Valley | Antarctica | Mars | `-77.50°, 161.50°` |
| Mauna Loa Saddle Lava Fields | Hawaii, USA | Moon and Mars | `19.50°, -155.60°` |
| Lanzarote - Timanfaya Lava Tubes | Canary Islands, Spain | Moon | `29.00°, -13.70°` |
| Stillwater Banded Anorthosite Zone | Montana, USA | Moon | `45.40°, -109.90°` |
| Sudbury Igneous Complex Melt Sheet | Ontario, Canada | Moon | `46.60°, -81.20°` |
| Dasht-e Lut Yardang Desert | Iran | Mars | `30.50°, 58.30°` |
| Kharan-Chagai Desert *(hypothesis)* | Balochistan, Pakistan | Mars | `28.90°, 64.60°` |
| Qaidam Basin Salt Yardangs | China | Mars | `37.50°, 93.50°` |
| Haughton Impact Structure | Devon Island, Canada | Moon and Mars | `75.40°, -89.70°` |
| Danakil Depression | Ethiopia | Mars | `14.20°, 40.30°` |
| Puna de Atacama Volcanic Plateau | Chile / Argentina | Mars | `-25.50°, -67.60°` |

### 5 Moon Targets

| Target | Region | Coordinates | Mission Context |
| :--- | :--- | :--- | :--- |
| Shackleton Rim and Connecting Ridge | Lunar south pole | `-89.9°, 0.0°` | Near-continuous sunlight on ridge crests beside permanently shadowed craters |
| Marius Hills Pit and Lava Tube | Oceanus Procellarum | `14.1°, -56.7°` | Basaltic plains with a skylight pit of interest for subsurface shelter concepts |
| Mare Tranquillitatis Pit and Basalt Plain | Mare Tranquillitatis | `8.3°, 33.2°` | Skylight pit that may provide access to a subsurface cavity or potential lava-tube structure (extent and continuity uncertain) |
| Aristarchus Plateau and Vallis Schröteri | Oceanus Procellarum NW | `23.7°, -47.4°` | Pyroclastic glass deposits and sinuous rille for volatile/oxygen ISRU and volcanic stratigraphy |
| Tycho Crater Rim and Impact Melt Sheet | Southern lunar highlands | `-43.3°, -11.2°` | Young Copernican complex crater with steep terraced walls and pooled impact-melt ponds |

### 2 Mars Targets

| Target | Region | Coordinates | Mission Context |
| :--- | :--- | :--- | :--- |
| Jezero Crater Delta | Isidis region | `18.4°, 77.7°` | Mars 2020 Perseverance landing site; ancient river delta and biosignature/sample-return target |
| Utopia Planitia Ice Plains | Northern lowlands | `47.0°, 118.0°` | Flat northern lowland terrain with shallow ground ice relevant to future water ISRU |

---

## Methodology & Data Provenance

Every Earth analog site and planetary target is represented as a normalized 8-dimensional vector (`0.0` to `1.0`). **Only one axis is computed from live NASA API data; one is computed from a formula using manually estimated slope; and six are literature-based estimates.**

### Eight Scoring Dimensions

| # | Dimension Key | Label | Provenance | How It Is Obtained |
| :---: | :--- | :--- | :--- | :--- |
| 1 | `thermal` | Thermal & Illumination Extremes | **NASA POWER API (Computed)** | Calculated directly from live NASA POWER climatology `T2M` (mean annual temperature) and `T2M_MAX`/`T2M_MIN` (annual temperature range): `0.6 × clamp((25 - temp) / 115) + 0.4 × clamp(rng / 100)`. Falls back to initial baseline values only if the API is unreachable. |
| 2 | `terrain` | Terrain & Slope Roughness | **Formula on Estimated Slope** | Calculated using `clamp(slope / 20)`, **where the underlying slope values (and site elevations) are manually entered estimates—not NASA elevation raster measurements** (not extracted from NASADEM, ASTER, or LRO LOLA). |
| 3 | `geology` | Geology & Mineralogy | **Literature-Based Estimate** | Hand-set `0..1` score from published planetary analog studies (not from orbital spectroscopy rasters). |
| 4 | `waterIce` | Water, Permafrost & ISRU | **Literature-Based Estimate** | Hand-set `0..1` score from published planetary analog studies. |
| 5 | `subsurface` | Subsurface & Lava Tubes | **Literature-Based Estimate** | Hand-set `0..1` score from published planetary analog studies. |
| 6 | `aeolian` | Aeolian & Regolith Dust | **Literature-Based Estimate** | Hand-set `0..1` score from published planetary analog studies. |
| 7 | `biosignature` | Extremophiles & Biosignatures | **Literature-Based Estimate** | Hand-set `0..1` score from published planetary analog studies. |
| 8 | `mobility` | Rover Mobility & EVA Ops | **Literature-Based Estimate** | Hand-set `0..1` score from published planetary analog studies. |

### Weighted Euclidean & Cosine Similarity

For each Earth site vector $a \in [0, 100]^8$, planetary target vector $b \in [0, 100]^8$, and user-selected mission weights $w \in [0, 1.5]^8$:

1. **Weighted Euclidean Similarity** (measures absolute magnitude closeness across axes):
   $$\text{Euclidean} = 100 - \sqrt{\frac{\sum_{i=1}^{8} w_i (a_i - b_i)^2}{\sum_{i=1}^{8} w_i}}$$
2. **Weighted Cosine Similarity** (measures proportional profile shape across axes):
   $$\text{Cosine} = \frac{100 \sum_{i=1}^{8} w_i a_i b_i}{\sqrt{\sum_{i=1}^{8} w_i a_i^2} \cdot \sqrt{\sum_{i=1}^{8} w_i b_i^2}}$$
3. **Combined Exploratory Index:**
   $$\text{Combined Index} = 0.60 \times \text{Euclidean} + 0.40 \times \text{Cosine}$$

> **Important:** Because six axes are literature-based estimates and the terrain axis relies on manually estimated slopes rather than orbital raster datasets, the combined score is an **exploratory heuristic decision-support index**—it must **never** be interpreted as a measured planetary similarity score.

---

## Scientific Limitations

- **No Reduced Gravity:** Terrestrial sites (`9.81 m/s²`) cannot replicate lunar (`1.62 m/s²`) or Martian (`3.71 m/s²`) gravity for regolith mechanics, dust settling, or mobility dynamics.
- **Atmosphere & Radiation:** Earth cannot reproduce the lunar near-vacuum, the thin Martian $\text{CO}_2$ atmosphere (`~0.6 kPa`), or unshielded solar/cosmic radiation environments.
- **Thermal Timescale Mismatch:** Earth climate ranges from NASA POWER reflect seasonal annual swings (`T2M_MAX - T2M_MIN`), whereas Moon and Mars ranges reflect extreme diurnal (day-night) temperature cycles.
- **Non-Raster Axis Estimates:** Six dimensions and site slope/elevation values are hand-set literature estimates rather than automated remote-sensing raster statistics (e.g., MODIS, ASTER, NASADEM, LRO LOLA, MRO CRISM).
- **Click-Anywhere Map Lookup:** Interactive map clicks score **climate variables only** (`temp`, `rng`, `rain`, `press`) from NASA POWER against the 12 surveyed sites; they do not evaluate local geology or subsurface features at arbitrary coordinates.
- **Hypothesis & Uncertain Targets:** *Kharan-Chagai* is included explicitly as an unverified hypothesis candidate, and *Mare Tranquillitatis* notes that the full extent and continuity of any subsurface cavity remain uncertain.

---

## Project Structure

```text
├── index.html                        # HTML entry point
├── package.json                      # Dependencies & scripts
├── bun.lock                          # Locked dependency graph
├── .env.example                      # Environment variable template
├── src/
│   ├── App.tsx                       # Main shell, NASA POWER fetch loop, conditional Maps provider
│   ├── data/
│   │   └── planetaryAnalogs.ts       # 8-axis schema, 7 targets, 12 Earth sites, similarity & NASA POWER client
│   ├── components/
│   │   ├── DiscoveryLabView.tsx      # Target selector, sliders, ranked table, site dossier
│   │   ├── GlobalAnalogMap.tsx       # Google Maps primary + Leaflet/Esri fallback, hover & click inspection
│   │   ├── MoonAndMarsView.tsx       # Solar System gallery, 3-world comparison table, target cards
│   │   ├── RadarComparisonChart.tsx  # 8-axis SVG radar chart
│   │   └── ScientificBriefView.tsx   # Methodology, limits, AI disclosure, roadmap
│   └── assets/images/                # Illustrative planetary imagery
└── README.md
```

---

## Local Setup & Installation

### Prerequisites
- **Node.js** (v18+ or v20+) with **npm** (`10.x`), or **Bun** (`1.4+`).

### 1. Install Dependencies
Both `package.json` and `bun.lock` are aligned (`esbuild: ^0.28.0` satisfies `vite@^8.3.0`'s peer requirement of `^0.27.0 || ^0.28.0`), so standard `npm install` resolves cleanly without `--legacy-peer-deps`:

```bash
npm install
```

Or install using the Bun lockfile:

```bash
bun install --frozen-lockfile
```

### 2. Optional — Configure Google Maps API Key
Copy `.env.example` to `.env` if you want to enable Google Maps Platform as the primary map provider:

```env
VITE_GOOGLE_MAPS_API_KEY="YOUR_GOOGLE_MAPS_API_KEY"
```

If no key is provided (or if Google Maps fails to load), the Global Map and Discovery Lab mini-map automatically use the **Leaflet + Esri** open tile fallback with Hybrid, Satellite, and Terrain layers intact.

### 3. Run Development Server, Type-Check, and Build

```bash
npm run dev      # Starts Vite dev server at http://localhost:3000
npm run lint     # Runs TypeScript type checking (tsc --noEmit)
npm run build    # Builds production bundle to dist/
```

---

## References & Data Sources

- **NASA POWER Project (Prediction Of Worldwide Energy Resources):**  
  https://power.larc.nasa.gov/  
  *(Climatology API endpoint used by the app: `https://power.larc.nasa.gov/api/temporal/climatology/point`)*
- **NASA Moon Exploration:**  
  https://science.nasa.gov/moon/
- **NASA Artemis Program:**  
  https://www.nasa.gov/humans-in-space/artemis/
- **NASA Lunar Reconnaissance Orbiter (LRO):**  
  https://science.nasa.gov/mission/lro/
- **NASA Mars 2020 Perseverance Rover (Jezero Crater):**  
  https://science.nasa.gov/mission/mars-2020-perseverance/
- **NASA Mars Reconnaissance Orbiter (MRO):**  
  https://science.nasa.gov/mission/mro/
- **NASA Solar System Planets Overview:**  
  https://science.nasa.gov/solar-system/planets/
- **Mapping & Geocoding Libraries:**  
  - `@vis.gl/react-google-maps` (Google Maps Platform React wrapper)  
  - `leaflet` (`https://leafletjs.com/`) with Esri `World_Imagery`, `World_Boundaries_and_Places`, and `World_Topo_Map` tile services (`server.arcgisonline.com`)  
  - BigDataCloud Client Reverse Geocoding API (`https://api.bigdatacloud.net/data/reverse-geocode-client`)

---

## AI Use Disclosure (NASA Space Apps)

In accordance with NASA Space Apps Challenge transparency guidelines, **Team NOVA FIVE** discloses that generative AI tools were used during the development of TerraAnalog for:
- **Coding & Architecture:** Scaffolding and refactoring the React, TypeScript, Vite, and Tailwind CSS codebase, including the similarity scoring helper and NASA POWER client requests.
- **Interface Development:** Building the four workspace views (Discovery Lab, Global Map, Moon & Mars, and Scientific Brief) and interactive controls.
- **Data Visualizations:** Implementing the SVG 8-axis radar comparison chart, Google Maps Platform and Leaflet/Esri map integrations, and cursor/click inspection overlays.
- **Image Generation:** Creating illustrative orbital visuals of Earth, the Moon, Mars, and the other Solar System planets (`src/assets/images/`).
- **Documentation & Copy:** Drafting and editing `README.md` and explanatory interface text.

**Team NOVA FIVE** directed the project concept, team scope, and submission materials. The team does not claim independent scientific verification of the NASA POWER climatology values, the manually estimated slopes, the literature-based axis estimates, or the exploratory heuristic similarity calculations; outputs should be treated as an exploratory decision-support prototype pending formal scientific and raster-based validation.
