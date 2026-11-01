# CAV-SHIELD
### AI-Driven Cyber-Physical Intrusion Detection System for Connected Autonomous Vehicles

![Project Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Frontend](https://img.shields.io/badge/Frontend-React%2019-blue)
![Backend](https://img.shields.io/badge/Backend-Node.js%20%7C%20Express-green)
![Language](https://img.shields.io/badge/Language-TypeScript-blue)

## Overview

**CAV-SHIELD** is an AI-driven Cyber-Physical Intrusion Detection System designed to monitor, analyze, and detect potentially malicious activities in Connected and Autonomous Vehicles (CAVs).

The system focuses on monitoring Controller Area Network (CAN) bus communication, identifying abnormal message patterns, simulating cyberattacks, and presenting security-related information through a real-time monitoring dashboard.

It combines vehicle telemetry simulation, intrusion detection workflows, attack injection mechanisms, and Python-based IDS integration into a unified security monitoring interface.

## Key Features

### 1. Security Operations Dashboard
- Centralized vehicle security monitoring.
- Overview of CAN bus frames and detected attacks.
- Normal traffic and attack statistics.
- IDS detection-rate visualization.

### 2. CAN Bus Traffic Monitoring
- Real-time CAN traffic visualization.
- CAN ID and payload inspection.
- DLC and ECU source information.
- Captured frame monitoring.

### 3. Attack Simulation
The platform provides a controlled environment for simulating different CAN bus attack scenarios, including:

- **Speed Spoofing:** Manipulation of vehicle speed-related messages.
- **Invalid Brake:** Injection of abnormal brake-related commands.
- **Fuzzy Attack:** Generation of unusual or randomized CAN payloads.
- **CAN DoS:** Simulation of excessive CAN message traffic.

### 4. Vehicle Telemetry
Monitoring of simulated vehicle parameters, including:
- Vehicle speed
- Engine RPM
- Brake pressure
- Obstacle distance
- Steering angle
- Battery percentage
- Gear status

### 5. Security Alerts and Event History
- Detection and presentation of suspicious activities.
- Security event monitoring.
- Attack-related information and telemetry review.

### 6. Python IDS Integration
- Python-based external IDS integration.
- Backend communication through HTTP APIs.
- Model registration and heartbeat monitoring.
- External inference endpoint support.

### 7. Deployment
- Frontend hosted on Vercel.
- Backend hosted on Render.
- Environment-based API configuration.
- Cross-origin communication enabled through CORS.

## System Architecture

```text
       Vehicle / CAN Traffic
                |
                v
       CAN Traffic Simulator
                |
                v
       Backend API (Express)
                |
        +-------+--------+
        |                |
        v                v
  IDS Processing    Python IDS
        |                |
        +-------+--------+
                |
                v
       Security Monitoring
                |
                v
       React Dashboard
                |
                v
       Alerts / Analytics
```

## Technology Stack

| Component | Technology |
|---|---|
| Frontend | React 19 |
| Build Tool | Vite 8 |
| Language | TypeScript |
| Backend | Node.js |
| API Framework | Express.js |
| Styling | Tailwind CSS |
| Icons | Lucide React |
| IDS Integration | Python |
| Communication | REST API, Server-Sent Events |
| Frontend Hosting | Vercel |
| Backend Hosting | Render |
| Version Control | Git and GitHub |

## Project Structure

```text
CAV-SHIELD/
│
├── server/
│   ├── server.ts
│   ├── routes.ts
│   └── canEngine.ts
│
├── src/
│   ├── components/
│   │   ├── PythonIntegrationView.tsx
│   │   ├── CanBusTrafficMonitor.tsx
│   │   └── ...
│   │
│   ├── hooks/
│   │   └── useCanBus.ts
│   │
│   └── ...
│
├── public/
├── package.json
├── vite.config.ts
├── tsconfig.json
└── README.md
```

*The structure above highlights the principal application directories and files.*

## Getting Started

### Prerequisites

Install the following before running the project:

- Node.js
- npm
- Git
- Python (if using the external Python IDS integration)

### 1. Clone the Repository

```bash
git clone https://github.com/luckyshivhare/can.git
```

### 2. Navigate to the Project

```bash
cd can
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure Environment Variables

Create a `.env` file in the project root:

```env
VITE_API_BASE_URL=http://localhost:3000
```

For the deployed frontend, configure:

```env
VITE_API_BASE_URL=https://can-shield-api.onrender.com
```

Use the appropriate backend URL for your environment.

### 5. Run the Application

Start the development server using:

```bash
npm run dev
```

Run the backend using the development command configured in the project's `package.json`.

### 6. Build for Production

```bash
npm run build
```

The production frontend build is generated in the `dist/` directory.

## Backend API

The backend provides endpoints for monitoring, simulation, and IDS integration.

| Endpoint | Purpose |
|---|---|
| `/api/health` | Backend health check |
| `/api/ids/status` | Retrieve IDS and simulation status |
| `/api/ids/stream` | Stream CAN bus updates |
| `/api/ids/simulate` | Control simulation and attack operations |
| `/api/ids/ingest` | Receive external telemetry |
| `/api/ids/predict-external` | External IDS inference |
| `/api/ids/test-connect-python` | Test Python integration |

## Deployment

### Frontend – Vercel

The frontend is deployed using Vercel.

**Deployment configuration:**
- Framework: Vite
- Build command: `npm run build`
- Output directory: `dist`
- Environment variable: `VITE_API_BASE_URL`

### Backend – Render

The backend is deployed using Render.

**Deployment configuration:**
- Runtime: Node.js
- Build command: `npm install; npm run build`
- Start command: `npm run start`
- Environment: `NODE_ENV=production`

### Live Application

- **Frontend:** https://can-tau-topaz.vercel.app
- **Backend Health:** https://can-shield-api.onrender.com/api/health
- **GitHub Repository:** https://github.com/luckyshivhare/can

## Testing and Verification

The following checks can be performed:

1. Verify that the frontend loads successfully.
2. Check backend availability through `/api/health`.
3. Verify CAN bus simulation and telemetry updates.
4. Test the attack simulation controls.
5. Verify security alerts and event history.
6. Check Python IDS connectivity and heartbeat status.
7. Inspect browser developer tools for API and network errors.

## Security Considerations

- Use controlled environments for attack simulation.
- Do not connect experimental attack-generation code to production vehicle networks.
- Protect external IDS endpoints and sensitive configuration.
- Restrict API access appropriately before production use.
- Use HTTPS for deployed frontend/backend communication.

## Limitations

- The dashboard's simulated CAN traffic does not represent a live physical vehicle CAN connection.
- Physical CAN hardware integration requires additional hardware and testing.
- External Python IDS inference depends on a separately running and configured Python service.
- Detection performance should be validated using appropriate datasets and real-world testing before operational use.

## Future Enhancements

- Physical CAN bus hardware integration.
- Advanced machine learning-based anomaly detection.
- Improved real-time attack classification.
- V2X communication security monitoring.
- Advanced threat intelligence and analytics.
- Integration with automotive cybersecurity testing environments.

## Team

**Developed by Team SARVADHA**

A collaborative engineering effort focused on automotive cybersecurity, artificial intelligence, and connected vehicle protection.

**Repository:** https://github.com/luckyshivhare/can

---

*Disclaimer: CAV-SHIELD is intended for educational, research, and controlled cybersecurity testing purposes. It is not certified for deployment in safety-critical vehicle systems.*
