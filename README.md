# SunSummary Desktop ☀️📊 (Windows Edition)

**SunSummary Desktop** brings the power of our professional solar project planning, financial scoping, and Bill of Materials (BOM) utility directly to your local workstation. Powered by a lightweight, native Windows executable, it allows developers, energy auditors, and engineering contractors to build comprehensive financial reports and pricing structures 100% locally and securely.

Every view is rendered in our signature **Neo-Brutalist Engineering UI**, featuring sharp borders, high-contrast layout grids, and clean black-and-yellow highlighting optimized for readability on-site and in the field.

---

## 🌟 Desktop-Specific Features

* **Zero Dependencies:** Runs natively on Windows out of the box. No installation of Node.js, Docker, or external runtimes required.
* **100% Offline & Private:** Unlike cloud-dependent tools, every financial simulation, tariff structure, and client proposal is processed locally on your machine. Your pricing data and business leads stay strictly confidential.
* **Rigorous Engineering Validation:** Fully interactive Bill of Materials (BOM) engine with strict numeric entry guards (`Math.max(0, val)`) and runtime JSON profile schema validation to intercept manually corrupted configuration files.
* **Premium PDF Proposal Engine:** Generates commercial-ready estimates, detailed technical matrices, and high-performance SVG cash flow projections directly onto local storage via unified HTML-to-PDF layout rendering.

---

## 📁 PC Distribution Structure

To ensure runtime stability, the executable launcher and its compiled frontend asset directory must reside within the same parent folder:

```text
├── SunSummary.exe        # Native Windows background server (lightweight & ultra-fast)
├── dist/                 # Local distribution folder containing compiled SPA assets
│   ├── index.html        # Main graphical interface entry point
│   ├── assets/           # Bundled financial calculations, SVG charts, and layouts
│   └── translations.ts   # Built-in bilingual engine (English / French localization)
└── README.txt            # Quick-start documentation and troubleshooting manual

```

---

## 🚀 Quick Start Guide

### 1. Launching the App

1. Download and extract the release directory.
2. Double-click **`SunSummary.exe`**.
3. A black command console will initialize to spin up the local server, and your machine's default web browser will automatically open to: `http://localhost:3000`.

> 💡 *If your web browser does not open automatically, simply launch any modern browser manually and navigate to `http://localhost:3000`.*

### 2. Bypassing Windows SmartScreen

Because this independent utility is compiled outside the Microsoft Store and without a commercial code-signing certificate, Windows SmartScreen may show a blue protective screen on its very first launch.

* Click **"More info"**
* Click **"Run anyway"**
*(Windows will cache this preference instantly and will not prompt you again for this release version).*

### 3. Closing the Application

To shut down the internal calculation engine and safely release the networking port, simply **close the black console window**.

---

## 🛠️ Troubleshooting & Port Management

* **Port Conflicts (`Could not find a free port`):** SunSummary automatically scans for an open local port from `3000` through `3019`. If you encounter an error, another local utility or developer package is using those ports. Close the active application or reboot your PC.
* **Antivirus False Positives:** Heuristic security engines occasionally flag unsigned standalone binary wrappers. The core application logic is entirely auditable. If Windows blocks execution silently, right-click `SunSummary.exe` and select *"Run as administrator"*.
* **Localization & Currencies:** The app features complete bilingual toggles (EN/FR) and multi-currency formatting configurations ($, €, £, CFA, etc.) handled directly inside the local `ProjectSettingsForm` component.
