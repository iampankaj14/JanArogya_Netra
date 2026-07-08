# 👁️ JanArogya Netra

### *The Eye of Public Healthcare*

**An AI-powered District Health Intelligence Command Center** that watches every PHC/CHC in a district in real time, predicts problems before they become crises, and tells health officers exactly what to do about it.

Built for **Google Cloud Build with AI — Code for Communities** · Track: **Smart Health**

---

## 🔗 Deliverables

| Deliverable | Link |
|---|---|
| 🚀 **Working Prototype** | [janarogya-netra-demo.surge.sh](https://janarogya-netra-demo.surge.sh) |
| 💻 **GitHub Source Code** | [(you are here)](https://github.com/iampankaj14/JanArogya_Netra) |
| 🎯 **Pitch Deck** | [pitch deck pdf](https://drive.google.com/file/d/18R7tS44F7i8DuH1V8GW-VStW1s5fmUSn/view) |

---

## 🔒 Demo Login Credentials

> Use the following demo accounts to explore the application.

| Role | Email | Password |
|------|-------|----------|
| **🏥 District Health Officer (DHO)** | `rajesh.kumar@health.gov.in` <kbd>Copy</kbd> | `RAJESHGOV@1234` <kbd>Copy</kbd> |
| **🩺 Block Medical Officer (BMO)** | `ananya.sharma@health.gov.in` <kbd>Copy</kbd> | `ANANYAGOV@1234` <kbd>Copy</kbd> |
| **👨‍⚕️ PHC Staff** | `vikram.patel@phc.org` <kbd>Copy</kbd> | `VIKRAM@GOV1234` <kbd>Copy</kbd> |

## 🩺 Problem Statement

District Health Officers (DHOs) overseeing dozens of Primary and Community Health Centers have almost no real-time visibility into what's happening on the ground. Medicine stockouts, sudden disease spikes, and PHCs that go silent are typically discovered *after* they've already become emergencies — via a phone call, a paper report, or a crisis. There is no single system that continuously watches every facility, understands the trend, and recommends a corrective action before it's too late.

## 💡 Solution

**JanArogya Netra** is a district-wide command center, not another passive dashboard. It follows one loop everywhere: **Data → Reasoning → Decision → Action.**

- **🧠 AI Situation Room** — a live, prioritized feed of anomalies (stockouts, outbreak signals, inactive PHCs) reasoned over by Google's Gemini models, with a conversational AI assistant that can explain *why* something is flagged and *what to do* next.
- **🔄 Smart Resource Redistribution** — detects medicine surplus at one PHC and shortage at another, and recommends/tracks transfer orders between facilities so stock moves to where it's actually needed instead of expiring on a shelf.
- **📈 Predictive Inventory & Disease Forecasting** — trends footfall, consumption, and disease patterns per facility to forecast upcoming shortages and outbreak risk ahead of time, not after the fact.
- **🗺️ Live District Map** — geospatial view of every PHC/CHC color-coded by health status, for at-a-glance district triage.
- **🌐 Multi-language Support** — full i18n so the tool is usable by officers and field staff across language regions, not just English speakers.
- **🔔 Real-time Alerts** — push and in-app notifications the moment a facility crosses a risk threshold.
- **🎙️ Voice Input** — hands-free data entry and querying for field conditions where typing isn't practical.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | Expo (SDK 56) · React Native 0.85 · Expo Router (file-based navigation) |
| **Language** | TypeScript |
| **Styling** | NativeWind (Tailwind CSS for React Native) |
| **State Management** | Zustand · TanStack React Query |
| **Backend / Data** | Firebase (Auth, Firestore, Storage) |
| **AI / Reasoning** | Google Gemini (`@google/generative-ai`) |
| **Maps** | react-native-maps + Google Maps Platform |
| **Voice** | expo-speech · expo-speech-recognition |
| **i18n** | i18next / react-i18next |
| **Animations** | react-native-reanimated |
| **Deployment (web demo)** | Static Expo web export, hosted on Surge |

---

## 🚀 How to Run Locally

### Prerequisites
- Node.js 18.x or 20.x (LTS)
- npm
- Expo Go app (for physical device testing) or Android Studio / Xcode (for emulators)

### Setup

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd janarogya-netra

# 2. Install dependencies
npm install

# 3. Configure environment variables
cp .env.example .env
# then fill in your own Firebase, Gemini, and Google Maps API keys in .env
```

### Run

```bash
npm start          # Start the Expo dev server (scan QR with Expo Go)
npm run android    # Run on Android emulator/device
npm run ios        # Run on iOS simulator/device
npm run web        # Run in browser
```

> The app also ships with local mock data (`dummy/`) so core screens are explorable even without live Firebase credentials configured.

---

## 📁 Directory Structure

```
app/                  # Expo Router screens — every file/folder here is a route
  (tabs)/             # Tab navigator: Situation Room, District Map, PHCs, Inventory, Reports, Profile...
  _layout.tsx         # Root navigation stack, providers, and global setup
  login.tsx           # Auth entry point

components/           # Reusable, presentation-focused UI
  common/             # App-wide shared components (headers, menus, AI assistant widget)
  ui/                 # Core design-system primitives (buttons, cards, inputs, navigation)
  features/           # Feature-specific composed components (e.g. dashboards)

features/             # Feature-first business logic modules (auth, dashboard, situation-room,
                       # district-map, phcs, notifications, profile, ai)

services/             # Integration layer — talks to the outside world
  api/                # Axios networking setup
  firebase/           # Firebase app/Auth/Firestore initialization
  ai/                 # Gemini client + speech services
  repositories/       # Data-access layer abstracting Firebase/local data behind one API

hooks/                # Custom React hooks (data fetching per domain, theming, voice input)
context/              # React context providers (Auth)
constants/            # Design tokens, static enums, translations
theme/                # Centralized color/spacing/typography theme
shared/               # Cross-cutting types, constants, and utilities
utils/                # Generic helpers (formatters, error types, event bus)
dummy/                # Local mock data powering offline/demo mode
firebase/, firestore.rules, storage.rules   # Backend config & security rules
```

---

## 👥 Team

Built for the Google Cloud Build with AI — Code for Communities hackathon, Smart Health track.
