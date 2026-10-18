# 🛡️ Kumbh Rakshak (कुंभ रक्षक)

**An AI-assisted platform for crowd safety, early risk detection, and medical emergency coordination at large-scale pilgrimages.**

🔗 **Live MVP:** https://atharv-mu.github.io/Kumbh-Rakshak/

![License: MIT](https://img.shields.io/badge/License-MIT-orange.svg)
![Tech Stack](https://img.shields.io/badge/Tech-HTML5%20%7C%20JavaScript%20%7C%20Tailwind%20%7C%20Leaflet-blue.svg)
![Status](https://img.shields.io/badge/Status-Hackathon%20MVP-emerald.svg)

---

## About the Project

Managing crowds at large religious gatherings like the Kumbh Mela is a major challenge. Millions of pilgrims gather in a limited area, making crowd congestion, medical emergencies, and delayed response serious safety concerns.

**Kumbh Rakshak** is a web-based dashboard designed to help address these challenges through a centralized crowd monitoring and emergency coordination system.

The platform brings together simulated thermal screening, GIS-based crowd density monitoring, automated risk alerts, medical resource tracking, and volunteer task management. It aims to help authorities identify potential risks earlier and coordinate responses more effectively.

The project is currently a hackathon MVP that demonstrates how technology can support safer and better-organized pilgrimages.

## The Problem

Large public gatherings create several challenges for crowd management and emergency response:

- **Crowd congestion:** Narrow pathways, ghat entrances, bridges, and other bottlenecks can become overcrowded.
- **Stampede risks:** Sudden changes in crowd movement can create dangerous situations.
- **Medical emergencies:** Heat exhaustion, elevated body temperature, dehydration, and other health concerns require timely attention.
- **Delayed coordination:** Communication gaps between control rooms, medical teams, and volunteers can slow down response times.
- **Limited real-time visibility:** Managing crowd conditions and medical resources across multiple locations can be difficult without a centralized system.

Kumbh Rakshak aims to bring these operations into one dashboard, helping teams monitor conditions, identify potential risks, and coordinate emergency tasks.

## Key Features

### 1. Multi-City Pilgrimage Management

The dashboard supports four major pilgrimage locations, with designated areas for monitoring and emergency coordination.

- **Prayagraj:** Triveni Ghat, Daraganj, Parade Ground
- **Haridwar:** Har Ki Pauri, Subhash Ghat, Bairagi Camp
- **Ujjain:** Ram Ghat, Mahakal Corridor, Narsinghat
- **Nashik:** Ramkund Main Ghat, Panchavati, Sadhugram

Users can switch between locations to explore the monitoring interface and its simulated operational data.

### 2. Thermal Screening and Medical Alerts

The prototype simulates thermal camera feeds to demonstrate how abnormal temperature readings can be flagged for medical review.

- Flags simulated temperature readings above **102°F**.
- Generates follow-up tasks for flagged individuals.
- Connects alerts with designated medical facilities.
- Demonstrates the workflow from initial detection to medical handover.

*Note: This feature uses simulated data. It does not represent a validated AI thermal screening system, and temperature readings alone cannot confirm an infection.*

### 3. GIS-Based Crowd Density Monitoring

The dashboard uses Leaflet.js and OpenStreetMap to visualize crowd conditions across designated sectors.

Crowd levels are displayed using a simple color-coded system:

- 🟢 **Normal:** Crowd levels are within the configured operating range.
- 🟡 **Moderate:** Crowd levels require closer monitoring.
- 🔴 **Critical:** Crowd levels have reached a configured alert threshold.

Interactive map tooltips display sector information, including estimated headcount, thermal risk indicators, and assigned medical facilities.

### 4. Early Warning and Crowd Alerts

Kumbh Rakshak includes a threshold-based alert mechanism to demonstrate how overcrowded sectors can be identified.

- Monitors simulated crowd occupancy.
- Triggers an alert when occupancy exceeds **96% of the configured sector capacity**.
- Generates warning audio using the browser's Web Audio API.
- Helps operators identify areas that may require additional attention.

The thresholds are intended for demonstration purposes and are not universal safety standards. Real-world crowd dispersal decisions require verified field information and approved emergency procedures.

### 5. Medical Resource Monitoring

The medical dashboard provides an overview of simulated medical resources and response activities.

- Monitor ICU bed and isolation ward availability.
- Review medical resource status.
- Track simulated paramedic shifts.
- Coordinate medical follow-up for flagged individuals.
- Track cases through medical handover and admission workflows.

### 6. Volunteer Task Management

The platform demonstrates how field volunteers can be coordinated through a centralized interface.

- Create and manage volunteer assignments.
- Assign follow-up tasks for flagged individuals.
- Associate incidents with designated medical facilities.
- Track task progress and response updates.
- Improve coordination between the command center and field teams.

### 7. Role-Based Dashboard Access

The login interface demonstrates three user roles with different operational responsibilities.

| Role | Responsibilities |
|---|---|
| Command Admin | Overall monitoring, sector management, and manual alert controls |
| Medical Officer (CMO) | Medical triage, ward capacity, and patient records |
| Volunteer Lead | Field assignments, intercept tasks, and ground-level updates |

The following mock identities are provided for demonstration:

| Role | Demo Email |
|---|---|
| Command Admin | `admin.commander@kumbhrakshak.gov.in` |
| Medical Officer | `cmo.officer@kumbhrakshak.gov.in` |
| Volunteer Lead | `volunteer.lead@kumbhrakshak.gov.in` |

These are illustrative identities, not verified government accounts. Refer to the application's login implementation for the required credentials.

**Security note:** The prototype's role selection should not be treated as production-grade access control. A real deployment would require secure authentication and server-side authorization.

## Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| Vanilla JavaScript | Dashboard logic and simulation |
| Tailwind CSS | Styling and UI components |
| Leaflet.js | Interactive maps and GIS visualization |
| OpenStreetMap | Geographic map layer |
| Lucide Icons | Interface icons |
| Web Audio API | Browser-generated warning audio |
| LocalStorage | Local persistence of supported application state |
| Google Fonts | Inter and Outfit typography |

## How It Works

Kumbh Rakshak uses a lightweight, browser-based architecture.

1. **Dashboard:** Displays crowd sectors, alerts, medical resources, and operational information.
2. **Simulation engine:** Updates demonstration data at regular one-second intervals.
3. **Risk monitoring:** Evaluates simulated temperature readings and sector occupancy against configured thresholds.
4. **GIS visualization:** Displays sector locations and their crowd status on an interactive map.
5. **Response coordination:** Demonstrates volunteer assignments and medical follow-up workflows.
6. **Local storage:** Retains supported application state in the browser.

The current application is a frontend prototype. Live sensor integration, validated AI inference, and centralized synchronization between multiple users are not established by the current architecture.

## Getting Started

### Prerequisites

- A modern web browser.
- Git, if you want to clone the repository.
- An internet connection for externally hosted libraries, fonts, and map tiles.

Node.js and npm are not required for the standalone version.

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/atharv-mu/Kumbh-Rakshak.git
cd Kumbh-Rakshak
```

**2. Run the application**

If the project uses `index.html` as its entry point, open it directly in your browser.

Alternatively, start a local server:

```bash
python -m http.server 8000
```

Then open http://localhost:8000 in your browser.

**3. Explore the dashboard**

- Select a pilgrimage location.
- Sign in using a supported demo role.
- Explore the crowd density map and sector tooltips.
- Review simulated thermal alerts.
- Check medical resources and volunteer tasks.
- Test the configured crowd occupancy alerts.

## Current Limitations

The current MVP is primarily designed for desktop browsers. Some features and interactions may not work as expected on mobile devices.

Areas for improvement include:

- Responsive layouts for smaller screens.
- Mobile-friendly navigation and dashboard panels.
- Touchscreen interactions for the GIS map.
- Better usability for medical and volunteer management interfaces.

The application also relies on simulated operational data and should not be used as a live public-safety monitoring system.

## Future Scope

Planned improvements and potential extensions include:

- [ ] Improve mobile responsiveness and touch interactions.
- [ ] Integrate thermal sensors and validated computer vision models.
- [ ] Explore real-time crowd estimation using approved camera or sensor feeds.
- [ ] Add backend APIs and synchronized multi-user updates.
- [ ] Integrate verified hospital capacity and ambulance dispatch systems.
- [ ] Introduce GPS-enabled volunteer tracking.
- [ ] Add historical incident analysis and crowd-flow forecasting.
- [ ] Implement secure authentication and permission management.
- [ ] Support multiple languages for field teams and pilgrims.
- [ ] Improve offline capabilities and communication reliability.
- [ ] Conduct usability and safety testing with emergency response professionals.

## Privacy, Security, and Safety

Kumbh Rakshak is a hackathon prototype intended to demonstrate a potential approach to crowd monitoring and emergency coordination.

Before real-world deployment, it would require secure authentication, appropriate data protection, validated screening methods, reliable sensor integrations, and testing with qualified medical and crowd-safety professionals.

Simulated readings, patient information, occupancy values, and resource counts should be treated as demonstration data unless independently verified.

The platform is not a substitute for professional medical assessment, trained crowd management, or official emergency response systems.

## Contributing

Contributions and suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make and test your changes.
4. Commit your changes with a descriptive message.
5. Open a pull request describing your improvements.

## License

This project is intended to be released under the MIT License. Ensure that the repository includes a `LICENSE` file containing the full MIT License text before publishing it as an MIT-licensed project.

## Acknowledgments

Kumbh Rakshak uses open-source technologies, including:

- [Leaflet.js](https://leafletjs.com/) for interactive maps.
- [OpenStreetMap](https://www.openstreetmap.org/) for geographic mapping.
- [Tailwind CSS](https://tailwindcss.com/) for styling.
- [Lucide](https://lucide.dev/) for icons.
- [Google Fonts](https://fonts.google.com/) for typography.

---

**Kumbh Rakshak — Better situational awareness. Faster coordination. Safer pilgrimages.**

*Developed as a hackathon MVP exploring technology-assisted crowd safety and medical emergency coordination.*
