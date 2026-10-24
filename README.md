# 🌍 Pulse — Earthquake Explorer

**Explore earthquakes. Visualize seismic waves. Discover Earth's interior.**

Pulse is an interactive, educational earthquake explorer that combines live USGS observations, a 3D Earth visualization, historical earthquake replay, seismic travel-time estimates, and recorded earthquake evidence in one browser-based experience.

> **Educational project:** Pulse visualizes earthquake observations and scientific reference models. It does not provide earthquake warnings, predictions, or emergency guidance.

---

## ✨ Overview

Earthquakes generate seismic waves that travel through the Earth and reveal information about its interior. Pulse makes these concepts easier to explore through interactive maps, historical replays, reference ray paths, and recorded seismic data.

Instead of presenting earthquake information as a static list, Pulse lets users explore individual events, inspect approximate seismic arrivals, revisit historical activity, and investigate how scientific models describe wave propagation.

## 🚀 Key Features

### 🌎 Live Earthquake Explorer
- Explore earthquake observations from the USGS.
- Select individual earthquakes and inspect event details.
- Navigate between cities, geographic coordinates, and supported seismic stations.
- View earthquake activity over configurable time ranges and magnitude thresholds.

### 🪐 Interactive 3D Earth
- Explore a three-dimensional representation of Earth.
- Switch between surface observations and interior reference scenarios.
- Investigate seismic ray paths as educational visualizations.
- Use an accessible 2D fallback map when needed.

### ⏱️ Historical Earthquake Replay
- Replay an earthquake timeline from its actual origin time.
- Explore a 90-minute replay window.
- Control playback at 1×, 10×, 30×, and 60× speeds.
- Share paused replay states through URL hash routes and query parameters.

### 📡 Seismic Travel-Time Estimates
- Estimate approximate direct P-wave and S-wave arrival times using the IASP91 reference model.
- Explore estimates for supported earthquake depths and receiver locations.
- Distinguish modeled arrival times from observed recordings.
- Display no estimate when the requested phase or model conditions are unsupported.

### 📚 Historical Evidence and Explore Mode
- Submit bounded historical earthquake queries.
- Explore verified landmark snapshots.
- Request available station recordings from EarthScope.
- Compare observations with a dated 2011 Tohoku earthquake reference recording.

### 💾 Local Exports and Preferences
- Export screenshots and JSON data locally.
- Share replay configurations through URL state.
- Keep earthquake observations and waveform data in memory during the session.
- Store visitor preferences in browser `localStorage`.

---

## 🧪 Science and Data

Pulse combines public observations with scientific reference models.

| Component | Purpose |
|---|---|
| USGS earthquake feeds | Earthquake observations and event metadata |
| IASP91 | Reference model for seismic travel-time calculations |
| EarthScope | On-demand access to supported seismic recordings |
| Natural Earth geometry | Geographic visualization data |
| TauP comparison | Numerical interpolation validation against a reference implementation |

### Understanding the limitations

- IASP91 is a one-dimensional reference Earth model, not an earthquake prediction or detection system.
- Arrival estimates are model-based and should not be interpreted as guaranteed observed arrival times.
- The interface selects the earliest supported direct P or S phase; unavailable estimates do not imply an absence of seismic activity.
- Interior reference rays are independent educational scenarios, not necessarily solutions for the selected earthquake.
- Surface propagation uses separately labeled illustrative fixed-speed geometry.
- Numerical agreement with TauP validates the relevant calculations against that reference, not real-world accuracy.

Pulse is intended for scientific exploration and education, not operational seismic monitoring.

---

## 🛠️ Technology Stack

- **JavaScript / TypeScript** — application logic and type safety
- **Node.js and npm** — development tooling and dependency management
- **Web visualization** — interactive Earth, geographic, and seismic views
- **USGS APIs and feeds** — earthquake observations
- **EarthScope services** — requested seismic recordings
- **Playwright** — browser-based end-to-end testing
- **GitHub Pages** — public deployment

See the source repository and project documentation for the exact implementation details.

---

## ⚙️ Getting Started

### Prerequisites

- Node.js **22.23.3**
- npm
- Git
- A modern web browser

The documented standard build does not require Python, API keys, a database, an account, or an environment file.

### 1. Clone the repository

Replace `YOUR-USERNAME` with your GitHub username. The following assumes you have permission to publish a copy of the project.

```bash
git clone https://github.com/YOUR-USERNAME/pulse.git
cd pulse
```

### 2. Install the required Node.js version

If you use nvm:

```bash
nvm install
nvm use
```

Make sure the selected version matches the project's `.nvmrc` file.

### 3. Install dependencies

```bash
npm ci
```

### 4. Start the development server

```bash
npm run dev
```

Open the local URL printed by the development server. The documented default is:

`http://127.0.0.1:5173/pulse/`

### 5. Run quality checks

```bash
npm run checks
```

This runs the project's documented checks for linting, TypeScript, unit tests, and asset integrity.

### 6. Build for production

```bash
npm run build
```

### 7. Preview the production build

```bash
npm run preview
```

The documented default preview URL is:

`http://127.0.0.1:4173/pulse/`

### 8. Run browser tests

Install the Chromium browser required by Playwright:

```bash
npx playwright install chromium
```

Then run:

```bash
npm run test:e2e
```

---

## 🔍 Default Experience

The documented defaults include:

- Live earthquake observations
- Past 24 hours of activity
- Magnitude threshold of M4.5+
- New Delhi as the initial receiver
- Stationary camera
- Seismic stations disabled
- Surface reference propagation disabled

USGS refreshes are limited to at most once per minute. Historical queries and waveform retrieval require explicit requests.

---

## 🔐 Privacy and Service Dependencies

Pulse is designed to work without subscription accounts or billing credentials.

The documented runtime services are:

- GitHub Pages for hosting
- USGS for earthquake observations
- EarthScope for requested seismic recordings

Earthquake observations and waveform data remain in application memory, while visitor preferences use browser `localStorage`. External service availability and free-use limits still apply.

---

## 📖 Documentation

For implementation details, scientific assumptions, data provenance, and deployment guidance, consult the project documentation:

- [Third-party notices](THIRD_PARTY_NOTICES.md)
- [Data provenance](public/assets/provenance.json)
- [Scientific methodology](docs/science.md)
- [Data sources](docs/data_sources.md)
- [Deployment guide](docs/deployment.md)
- [Operations runbook](docs/runbook.md)
- [Acceptance report](docs/acceptance_report.md)

### Browser compatibility

The documented target includes current and previous desktop versions of Chrome, Edge, Firefox, and Safari, along with current mobile Safari and Chrome.

Automated browser test results should be distinguished from validation on physical devices.

---

## 📄 License and Attribution

The original project identifies MIT-licensed authored code, public-domain Natural Earth geometry, and third-party scientific software and seismic data subject to their respective license and acknowledgment requirements.

Before redistributing this project, review the original repository's license and retain all required notices and acknowledgments, including those relating to ObsPy TauP and IU/GSN seismic recordings and metadata.

---

*Pulse — making earthquake observations and seismic science more accessible through interactive exploration.*
