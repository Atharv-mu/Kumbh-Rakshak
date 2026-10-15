# 🛡️ Kumbh Rakshak (कुंभ रक्षक)

> **AI-Powered Thermal Surveillance, Early Stampede Mitigation & Multi-City Medical Triage System for Mass Pilgrimages**

[![License: MIT](https://img.shields.io/badge/License-MIT-orange.svg)](https.opensource.org/licenses/MIT)
[![Stack: HTML5/JS/Tailwind](https://img.shields.io/badge/Stack-Tailwind_CSS_|_Leaflet_GIS-blue.svg)](#)
[![Status: Hackathon_Prototype](https://img.shields.io/badge/Status-Live_Prototype-emerald.svg)](#)

---

## 📌 Problem Statement

During massive congregation events like the **Kumbh Mela** (Prayagraj, Haridwar, Ujjain, Nashik), controlling multi-million crowd flows poses two catastrophic risks:
1. **Sudden Stampedes:** High crowd accumulation at bottlenecks like river ghat entrances, pontoon bridges, and narrow lanes.
2. **Health Outbreaks & Heatstrokes:** Fast cross-transmission of high fevers, heat exhaustion, and viral rash infections across packed crowds.

Traditional surveillance relies on manual monitoring, which reacts *after* panic or disease outbreaks begin. **Kumbh Rakshak** solves this by providing a unified real-time command dashboard combining **AI thermal screening**, **GIS crowd density heatmaps**, **ground volunteer tasking**, and **acoustic dispersal sirens**.

---

## 🚀 Key Features

### 🌐 1. Multi-City Pilgrimage Multi-Tenancy
Switch between major festival locations instantly from the header or login overlay:
* 📍 **Prayagraj Sangam** (Triveni Ghat, Daraganj, Parade Ground)
* 📍 **Haridwar Ganga Ghat** (Har Ki Pauri, Subhash Ghat, Bairagi Camp)
* 📍 **Ujjain Shipra Ghat** (Ram Ghat, Mahakal Corridor, Narsinghat)
* 📍 **Nashik Ramkund** (Ramkund Main Ghat, Panchavati, Sadhugram)

### 🌡️ 2. AI Thermal Camera Fever & Rash Detection
* **Real-time Thermal Feeds:** Simulates entry-gate thermal vision detecting abnormal body heat (`>102°F`).
* **One-Click Dispatch:** Flagged pilgrims generate instant volunteer intercept tasks mapped to designated Medical Wards.

### 🗺️ 3. GIS Sector Heatmaps & Sticky Tooltips
* Color-coded Leaflet vector rings for crowd pressure (🟢 Normal, 🟡 Moderate, 🔴 Critical).
* **Hover Tooltips (`sticky: true`):** Move the cursor over any sector to inspect live headcount, thermal risk level, and medical facility assignments without popup flickering.

### 🚨 4. Early Stampede Siren & Crowd Dispersal Alarms
* Automatically triggers when live sector density crosses safety limits (>96% capacity).
* Synthesizes warning audio via Web Audio API to disperse crowded zones and direct traffic to buffer sectors.

### 🏥 5. Live Medical Room & Escort Tracking
* Tracks free ICU beds, isolation wards, and paramedic shifts.
* Log ground volunteer tasks from initial flag to medical room admission.

---

## 💻 Tech Stack & Architecture

* **Frontend:** Standalone HTML5 + Modern Vanilla JavaScript (Zero build step required)
* **Styling:** Tailwind CSS CDN + Google Fonts (*Inter* & *Outfit*)
* **GIS Engine:** Leaflet.js with OpenStreetMap layer
* **Icons:** Lucide Icons
* **Audio Synthesis:** Browser-native HTML5 Web Audio API
* **State & Data:** LocalStorage + 1-second real-time simulation tick engine

---

## 🔐 Role-Based Access Control (RBAC)

The full-screen login modal allows testing three distinct user personas:

| Role Title | Mock Security Credential | Access Level |
| :--- | :--- | :--- |
| **Command Admin** | `admin.commander@kumbhrakshak.gov.in` | Full command, manual sirens, sector modifications |
| **Medical Officer (CMO)** | `cmo.officer@kumbhrakshak.gov.in` | Triage management, isolation beds, patient logs |
| **Volunteer Lead** | `volunteer.lead@kumbhrakshak.gov.in` | Field tasks, intercept assignments, ground updates |

---

## 🛠️ Quick Start

No Node.js, `npm install`, or backend server setup needed.

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/kumbh-rakshak.git](https://github.com/your-username/kumbh-rakshak.git)
   cd kumbh-rakshak
