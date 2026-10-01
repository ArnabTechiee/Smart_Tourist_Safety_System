## README: Smart Tourist Safety System (SIH25002)

**🚀 Live Demo:** [https://safesphere-dashboard.vercel.app/](https://safesphere-dashboard.vercel.app/)

## Project Overview

The Smart Tourist Safety System is an innovative solution designed to enhance the safety and security of tourists by leveraging a powerful fusion of AI, Geo-fencing, and Blockchain technology. This project addresses the SIH Problem Statement SIH25002, aiming to provide a comprehensive, real-time monitoring and alert system for tourist safety.

Our current prototype demonstrates the core AI and monitoring capabilities, offering a robust foundation for future integrations.

## Current Prototype Features (Next.js Frontend)

The current prototype provides a complete end-to-end simulation, showcasing the following functionalities:

*   **Live Map Movement for Multiple Tourists:** Visualize the real-time location and movement of multiple simulated tourists on an interactive map.
    
*   **Real-time AI-driven Anomaly Detection with Visual Alerts:** The system actively monitors tourist behavior and environmental factors, identifying anomalies that might indicate a safety risk. Visual alerts are triggered immediately on the dashboard when an anomaly is detected.
    
*   **Fully Functional SOS System (Raise and Resolve):** Tourists can initiate an SOS alert through the simulated mobile app. Authorities can receive, manage, and resolve these alerts, demonstrating a complete emergency response workflow.
    
*   **Dynamic Tourist Safety Score:** Each tourist is assigned a dynamic safety score that adjusts in real-time based on various factors, including their current location (e.g., proximity to high-risk areas) and time of day. This score provides a quick assessment of a tourist's safety status.
    
*   **Detailed, Timestamped Tourist Logs:** Comprehensive logs are maintained for each tourist, recording their movements, activities, and any safety-related events, all with precise timestamps for auditing and analysis.
    
*   **Proactive Safety Alerts (Simulated Mobile App):** Tourists receive proactive safety alerts directly on their simulated mobile app, based on their location, safety score, and detected anomalies.
    
*   **Automated E-FIR Generation & Reporting:**
    *   The system automatically triggers an Electronic First Information Report (E-FIR) if a tourist remains in an SOS or anomaly state for a critical duration. 
    *   The generated reports include a **Live Mini-Map** pinpointing the incident's exact coordinates.
    *   Authorities can instantly generate and download official **PDF Police Reports** directly from the dashboard.
    
*   **Modern & Premium UI (App Simulator):** The simulator interface has been completely redesigned with a deep dark mode, sleek glassmorphism panels, interactive glow effects, and micro-animations, providing a high-quality presentation experience.
    
## Technical Stack (Current Prototype)

*   **Frontend:** Next.js

## Future Enhancements & Integration Plan

Our final development phase will focus on integrating the following key features to complete the system:

*   **Blockchain Integration (Hyperledger Fabric):**
    *   **Secure Tourist Registration:** Integrate with a Hyperledger Fabric backend to provide a decentralized and immutable record for tourist registration, ensuring data integrity and enhanced security.
    *   **Transparent Data Management:** Leverage blockchain for transparent and tamper-proof logging of critical safety events and interactions.
    
*   **Emergency Contact Alerts (Twilio Integration):**
    *   **Automated SMS/WhatsApp Messages:** Integrate a service like Twilio to automatically send SMS or WhatsApp messages to pre-registered emergency contacts when a tourist raises an SOS alert or a critical safety incident is detected.
    
## Getting Started & Deployment

This project consists of three parts: a Node.js Backend, a Next.js Live Dashboard (Main Frontend), and a Next.js App Simulator. They are configured to run seamlessly together.

### Local Development Setup

To run the entire system locally, open **three separate terminal tabs** in the root directory:

**1. Start the Backend:**
```bash
cd backend
npm install
npm start
```
*(Runs on http://localhost:5001)*

**2. Start the App Simulator:**
```bash
cd app-simulation
npm install
npm run dev -- -p 3001
```
*(Runs on http://localhost:3001)*

**3. Start the Live Dashboard (Main App):**
```bash
cd live-dashboard
npm install
npm run dev
```
*(Runs on http://localhost:3000)*

**Testing Locally:**
Because of Next.js rewrites, you can test everything from a single URL!
- Go to `http://localhost:3000` to view the Live Dashboard.
- Go to `http://localhost:3000/simulator` to view the App Simulator seamlessly!

---

### Cloud Deployment (Vercel & Render)

**1. Deploy Backend to Render:**
- Create a new Web Service on Render pointing to your GitHub repo.
- Set Root Directory to `backend`.
- Build Command: `npm install`, Start Command: `node index.js`.
- Copy the provided URL (e.g., `https://your-backend.onrender.com`).
- **Keep-Alive (Optional but recommended):** Render's free tier sleeps after 15 minutes of inactivity. We have provided a `/ping` endpoint for this. Create a free account on [cron-job.org](https://cron-job.org/) and set up a cron job to ping `https://[Your Render Backend URL]/ping` every 10-14 minutes to keep the server awake permanently.

**2. Deploy App Simulator to Vercel:**
- Create a new project on Vercel from your repo.
- Set Root Directory to `app-simulation`.
- Add Environment Variable: `NEXT_PUBLIC_API_URL` = `[Your Render Backend URL]`.
- Deploy and copy the Vercel URL (e.g., `https://your-sim.vercel.app`).

**3. Deploy Live Dashboard to Vercel (Main Site):**
- Create another project on Vercel from your repo.
- Set Root Directory to `live-dashboard`.
- Add Environment Variables:
  - `NEXT_PUBLIC_API_URL` = `[Your Render Backend URL]`
  - `SIMULATOR_URL` = `[Your Vercel App Simulator URL]` *(No trailing slash)*
- Deploy and attach your custom domain!

## Contribution

We welcome contributions to this project! If you're interested in helping us develop this system further, please refer to our `CONTRIBUTING.md` (to be created) for guidelines.
