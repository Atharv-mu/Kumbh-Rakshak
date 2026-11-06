# Kumbh Rakshak (कुंभ रक्षक)

> **Better situational awareness. Faster coordination. Safer pilgrimages.**

An AI-assisted platform concept for crowd safety, early risk detection and medical emergency coordination at large-scale pilgrimages.

<p align="center">
  <a href="https://atharv-mu.github.io/Kumbh-Rakshak/"><img src="https://img.shields.io/badge/Live_MVP-Visit_Site-ff9800?style=for-the-badge&logo=githubpages&logoColor=white" alt="Live MVP"></a>
  <img src="https://img.shields.io/badge/License-MIT-orange?style=for-the-badge" alt="MIT License">
  <img src="https://img.shields.io/badge/Status-Hackathon_MVP-10b981?style=for-the-badge" alt="Hackathon MVP">
</p>

**Live MVP:** [atharv-mu.github.io/Kumbh-Rakshak](https://atharv-mu.github.io/Kumbh-Rakshak/)

---

## Contents

- [About the project](#about-the-project)
- [The problem](#the-problem)
- [Key features](#key-features)
- [Technology stack](#technology-stack)
- [How it works](#how-it-works)
- [Getting started](#getting-started)
- [Current limitations](#current-limitations)
- [Future scope](#future-scope)
- [Privacy, security and safety](#privacy-security-and-safety)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## About the project

Managing crowds at large religious gatherings such as the Kumbh Mela is a major challenge. Millions of pilgrims gather in a limited area, so congestion, medical emergencies and slow response times become serious safety concerns.

Kumbh Rakshak is a web-based dashboard that brings crowd monitoring and emergency coordination into one place. It combines simulated thermal screening, map-based crowd density monitoring, automated risk alerts, medical resource tracking and volunteer task management, with the goal of helping authorities spot risks earlier and respond in a more coordinated way.

It is a hackathon MVP that demonstrates how technology could support safer, better-organised pilgrimages.

## The problem

Large public gatherings create several challenges for crowd management and emergency response:

- **Crowd congestion:** narrow pathways, ghat entrances, bridges and other bottlenecks can become overcrowded.
- **Stampede risk:** sudden changes in crowd movement can create dangerous situations.
- **Medical emergencies:** heat exhaustion, high body temperature, dehydration and other health problems need timely attention.
- **Delayed coordination:** communication gaps between control rooms, medical teams and volunteers can slow the response.
- **Limited real-time visibility:** without a central system, it is hard to track crowd conditions and medical resources across many locations.

---

## Key features

### 1. Multi-city pilgrimage management

The dashboard covers four pilgrimage cities, each with designated areas for monitoring and emergency coordination.

| City | Monitored areas |
|---|---|
| Prayagraj | Triveni Ghat, Daraganj, Parade Ground |
| Haridwar | Har Ki Pauri, Subhash Ghat, Bairagi Camp |
| Ujjain | Ram Ghat, Mahakal Corridor, Narsinghat |
| Nashik | Ramkund Main Ghat, Panchavati, Sadhugram |

Users can switch between cities to explore the interface and its simulated operational data.

### 2. Thermal screening and medical alerts

The prototype simulates thermal camera feeds to show how abnormal temperature readings could be flagged for medical review. It flags simulated readings above **102°F**, creates follow-up tasks for flagged individuals, links alerts to designated medical facilities, and walks through the workflow from detection to medical handover.

> This feature uses simulated data. It is not a validated AI thermal screening system, and a temperature reading alone cannot confirm an infection.

### 3. GIS-based crowd density monitoring

The dashboard uses Leaflet.js and OpenStreetMap to show crowd conditions across designated sectors, using a simple colour code:

- **Green (Normal):** crowd levels are within the configured operating range.
- **Yellow (Moderate):** crowd levels need closer monitoring.
- **Red (Critical):** crowd levels have reached a configured alert threshold.

Map tooltips show each sector's estimated headcount, thermal risk indicators and assigned medical facilities.

### 4. Early warning and crowd alerts

A threshold-based alert system shows how overcrowded sectors could be identified. It monitors simulated occupancy and triggers an alert when occupancy exceeds **96% of a sector's configured capacity**. The alert also plays a warning sound generated with the browser's Web Audio API.

> The thresholds are for demonstration only and are not universal safety standards. Real crowd-dispersal decisions require verified field information and approved emergency procedures.

### 5. Medical resource monitoring

The medical dashboard gives an overview of simulated resources and response activity. It shows ICU bed and isolation ward availability, resource status and paramedic shifts, and tracks flagged individuals through medical follow-up, handover and admission.

### 6. Volunteer task management

The platform shows how field volunteers could be coordinated from one interface. Users can create and manage assignments, assign follow-up tasks for flagged individuals, link incidents to medical facilities, and track task progress, which helps connect the command centre with field teams.

### 7. Role-based dashboard access

The login screen demonstrates three roles with different responsibilities.

| Role | Responsibilities | Demo email |
|---|---|---|
| Command Admin | Overall monitoring, sector management and manual alert controls | `admin.commander@kumbhrakshak.gov.in` |
| Medical Officer (CMO) | Medical triage, ward capacity and patient records | `cmo.officer@kumbhrakshak.gov.in` |
| Volunteer Lead | Field assignments, intercept tasks and ground-level updates | `volunteer.lead@kumbhrakshak.gov.in` |

These are illustrative identities, not real government accounts. See the login implementation in the code for the credentials it expects.

> **Security note:** The prototype's role selection is not production-grade access control. A real deployment would need secure authentication and server-side authorisation.

---

## Technology stack

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| Vanilla JavaScript | Dashboard logic and simulation |
| Tailwind CSS | Styling and UI components |
| Leaflet.js | Interactive maps and GIS visualisation |
| OpenStreetMap | Map layer |
| Lucide Icons | Interface icons |
| Web Audio API | Browser-generated warning audio |
| LocalStorage | Local persistence of supported application state |
| Google Fonts | Inter and Outfit typography |

---

## How it works

Kumbh Rakshak is a lightweight, browser-based application.

1. **Dashboard:** shows crowd sectors, alerts, medical resources and operational information.
2. **Simulation engine:** refreshes the demonstration data every second.
3. **Risk monitoring:** checks simulated temperature readings and sector occupancy against the configured thresholds.
4. **GIS visualisation:** plots sectors and their crowd status on an interactive map.
5. **Response coordination:** demonstrates volunteer assignments and medical follow-up.
6. **Local storage:** keeps supported application state in the browser.

This is a frontend prototype. The current architecture does not provide live sensor integration, validated AI inference or synchronisation between multiple users.

---

## Getting started

### Prerequisites

- A modern web browser
- Git, if you want to clone the repository
- An internet connection, for the externally hosted libraries, fonts and map tiles

Node.js and npm are not needed.

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/atharv-mu/Kumbh-Rakshak.git
   cd Kumbh-Rakshak
   ```
2. Run the application. If `index.html` is the entry point, open it directly in your browser. Or start a local server:
   ```bash
   python -m http.server 8000
   ```
   Then open http://localhost:8000.
3. Explore the dashboard:
   - Select a pilgrimage city
   - Sign in with a demo role
   - Explore the crowd density map and sector tooltips
   - Review the simulated thermal alerts
   - Check medical resources and volunteer tasks
   - Test the crowd occupancy alerts

---

## Current limitations

- The MVP is designed mainly for desktop browsers, so some features may not work well on mobile devices.
- Areas that need work include responsive layouts for small screens, mobile-friendly navigation and dashboard panels, touch interaction on the map, and easier medical and volunteer management screens.
- All operational data is simulated, so the app must not be used as a live public-safety monitoring system.

---

## Future scope

- [ ] Improve mobile responsiveness and touch interactions
- [ ] Integrate thermal sensors and validated computer vision models
- [ ] Explore real-time crowd estimation from approved camera or sensor feeds
- [ ] Add backend APIs and synchronised multi-user updates
- [ ] Integrate verified hospital capacity and ambulance dispatch systems
- [ ] Add GPS-enabled volunteer tracking
- [ ] Add historical incident analysis and crowd-flow forecasting
- [ ] Implement secure authentication and permission management
- [ ] Support multiple languages for field teams and pilgrims
- [ ] Improve offline capability and communication reliability
- [ ] Test usability and safety with emergency response professionals

---

## Privacy, security and safety

Kumbh Rakshak is a hackathon prototype that demonstrates one possible approach to crowd monitoring and emergency coordination.

Before any real-world use, it would need secure authentication, proper data protection, validated screening methods, reliable sensor integrations, and testing with qualified medical and crowd-safety professionals.

Treat all readings, patient information, occupancy values and resource counts as demonstration data unless independently verified. The platform is not a substitute for professional medical assessment, trained crowd management or official emergency response systems.

---

## Contributing

Contributions and suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make and test your changes.
4. Commit with a descriptive message.
5. Open a pull request describing your improvements.

---

## License

This project is intended to be released under the MIT License. Before publishing it as MIT-licensed, make sure the repository includes a `LICENSE` file with the full MIT License text.

---

## Acknowledgments

Built with these open-source tools:

- [Leaflet.js](https://leafletjs.com/) for interactive maps
- [OpenStreetMap](https://www.openstreetmap.org/) for map data
- [Tailwind CSS](https://tailwindcss.com/) for styling
- [Lucide](https://lucide.dev/) for icons
- [Google Fonts](https://fonts.google.com/) for typography

---

*Developed as a hackathon MVP exploring technology-assisted crowd safety and medical emergency coordination.*
