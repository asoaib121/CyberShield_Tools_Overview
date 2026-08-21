# 🛡️ CyberShield AI — LLM Phishing & Threat Detection Studio

[![Google Gemini](https://img.shields.io/badge/AI-Gemini_3.6_Flash-4285F4?style=for-the-badge&logo=google)](https://ai.google.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-5-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](./LICENSE)
[![GitHub](https://img.shields.io/badge/Repo-Phishing_Link_Detection-181717?style=for-the-badge&logo=github)](https://github.com/asoaib121/Phishing_Link_Detection_Tools_With_LLM_Model)

> Enterprise-style cybersecurity analysis studio that combines **Large Language Models (Google Gemini / OpenAI)** with **Explainable AI (XAI) heuristics** to detect phishing URLs, malicious emails, risky web content, and suspicious files — then explains *why* a threat was flagged.

---

## 🌐 Live Demo

Experience the live application hosted on Vercel:  
👉 **[https://shoaib-cybershield-with-llm.vercel.app](https://shoaib-cybershield-with-llm.vercel.app/) or (https://phishing-link-detection-tools-wi-git-738381-asoaib121s-projects.vercel.app/)**

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Where LLMs Are Used](#-where-llms-are-used)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Quick Start](#-quick-start)
- [Environment Variables](#-environment-variables)
- [API Endpoints](#-api-endpoints)
- [Usage Guide](#-usage-guide)
- [Credits & Contributors](#-credits--contributors)
- [Copyright & License](#-copyright--license)
- [Disclaimer](#-disclaimer)
- [Contributing](#-contributing)

---

## 🎯 Overview

**CyberShield AI** is a full-stack phishing and cyber-threat intelligence toolkit designed for learning, demos, SOC-style workflows, and research.

It provides:

- Multi-category scanning (**URL · Email · Web HTML · File**)
- Hybrid detection (**rules + graph/heuristic algorithms + LLM XAI**)
- Interactive **AI Threat Advisor** chatbot
- **Scan history comparison** with deep LLM re-analysis
- **Global threat risk map** (geolocation markers)
- One-click **PDF / JSON / CSV** security reports

Primary repository:  
[https://github.com/asoaib121/Phishing_Link_Detection_Tools_With_LLM_Model](https://github.com/asoaib121/Phishing_Link_Detection_Tools_With_LLM_Model)

---

## 🌟 Key Features

| Feature | Description |
|--------|-------------|
| 🔗 URL Threat Scanner | Domain spoofing, SSL signals, redirects, blacklist/heuristic risk scoring |
| 📧 Email Classifier | Urgency lures, brand impersonation, attachment hints, LLM social-engineering analysis |
| 🌐 Web Content Analyzer | HTML forms, iframes, external scripts, DOM/obfuscation hints |
| 📁 File Analyzer | MD5/SHA-256, entropy, macros, suspicious API markers |
| 🤖 AI Threat Advisor | Dynamic chatbot for security + educational Q&A (algorithms, testing, etc.) |
| 🔬 Deep Re-Analysis | Category-aware Gemini deep explanation engine |
| 📊 History Comparison | Compare any 2 scans (same or cross-category) with attack-chain narrative |
| 🌍 Risk Map | Leaflet dark-map visualization of resolved host/IP origins |
| 📄 Report Export | Dark-themed PDF (`jspdf` + `autotable`), JSON, and CSV metrics |
| ⚙️ Gemini Studio | In-app API key / model configuration & connectivity check |
| 🔌 Offline Fallback | Continues with local heuristics if LLM quota/API is unavailable |

---

## 🧠 Where LLMs Are Used

| Module | File(s) | Purpose |
|--------|---------|---------|
| URL / Email / Web / File scan XAI | `llmEmailAnalysis.js` + `server.js` | Risk classification + human-readable explanation |
| Sandbox preview narration | `server.js` | Behavioral safety commentary |
| AI Chat Advisor | `llmChat.js` | Threat Q&A + general knowledge answers |
| Deep Re-Analyze | `llmDeepAnalysis.js` | Long-form XAI report per category |
| Scan Comparison | `llmDeepAnalysis.js` | Cross-scan delta + attack-chain correlation |
| PDF Report content | `public/app.js` | Embeds full LLM deep explanation into exports |

**Default model:** `gemini-3.6-flash` (configurable). Optional OpenAI fallback via `OPENAI_API_KEY`.

---

## 🛠 Tech Stack

**Backend**
- Node.js + Express 5
- dotenv, cors, multer
- Google Gemini API / OpenAI API

**Frontend**
- Vanilla HTML / CSS / JavaScript (`public/`)
- Dark cyan cybersecurity UI theme
- Leaflet (threat map)
- jsPDF + jspdf-autotable (reports)

**Algorithms / XAI Heuristics**
- Feature graph traversal (DFS / BFS)
- Minimax / Alpha-Beta style attack-defense scoring
- Fuzzy risk inference
- Brand impersonation & blacklist checks

**Optional / Related**
- `chatboot/` — Python Flask conversational agent (ELF)
- Browser extension scaffold in `extension/`
- Deploy helpers: `render.yaml`, `Procfile`, `vercel.json`

---

## 📁 Project Structure

```text
.
├── server.js                 # Express API + scan pipelines
├── llmChat.js                # Chat advisor (Gemini/OpenAI)
├── llmEmailAnalysis.js       # Scan-time LLM XAI classifier
├── llmDeepAnalysis.js        # Deep re-analyze + comparison engine
├── threatIntel.js            # Domain/URL threat intelligence helpers
├── public/
│   ├── index.html            # Main UI
│   ├── app.js                # Frontend logic
│   └── styles.css            # Dark cybersecurity theme
├── chatboot/                 # Optional Python chatbot module
├── extension/                # Browser extension demo files
├── .env.example              # Environment template
├── LICENSE                   # MIT License
└── README.md
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js **18+**
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)

### 1) Install
```bash
npm install
```

### 2) Configure environment
Copy `.env.example` to `.env` and set your key:
```env
LLM_PROVIDER=auto
GEMINI_API_KEY=your_gemini_api_key_here
GEMINI_MODEL=gemini-3.6-flash
GEMINI_GOOGLE_SEARCH=false
PORT=3000
```

### 3) Run
```bash
npm start
```

Open: **[http://localhost:3000](http://localhost:3000)**

### Optional public tunnel
```bash
npm run share
```

---

## 🔐 Environment Variables

| Variable | Description |
|----------|-------------|
| `GEMINI_API_KEY` | Google Gemini API key (**required** for full LLM features) |
| `GEMINI_MODEL` | Model name (default: `gemini-3.6-flash`) |
| `GEMINI_GOOGLE_SEARCH` | `true/false` — search grounding (may hit quota faster) |
| `OPENAI_API_KEY` | Optional OpenAI fallback |
| `LLM_PROVIDER` | `auto` \| `gemini` \| `openai` |
| `TAVILY_API_KEY` | Optional web reputation search |
| `PORT` | Server port (default `3000`) |

> ⚠️ Never commit real API keys. Keep secrets only in local `.env` (already gitignored).

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/scan-url` | URL threat scan + LLM XAI |
| `POST` | `/scan-email` | Email/message phishing analysis |
| `POST` | `/scan-website` | HTML/DOM/iframe analysis |
| `POST` | `/scan-file` | File hash/entropy/macro analysis |
| `POST` | `/api/chat` | AI Threat Advisor |
| `POST` | `/api/reanalyze` | Universal deep LLM re-analysis |
| `POST` | `/api/compare-scans` | Cross-category scan comparison |
| `POST` | `/api/threat-geo` | Host/IP geolocation for risk map |
| `POST` | `/api/check-gemini` | Gemini connectivity diagnostics |
| `GET` | `/history` | Recent scan history |
| `GET` | `/dashboard` | Telemetry summary |
| `GET` | `/health` | Health check |

---

## 📘 Usage Guide

1. Open the app and choose a scanner tab (**URL / Email / Web / File**).
2. Run a scan and review risk score, indicators, and XAI cards.
3. Use **Ask AI Cyber Advisor** for follow-up questions.
4. Open **Dashboard** → select any **2** history items → **Compare Selected**.
5. Click **LLM Deep Re-Analyze** for a long-form explanation.
6. Export **PDF / JSON / CSV** from the sidebar or report panel.
7. Review the **Interactive Risk Map** under scan results.

---

## 🙏 Credits & Contributors

### Project Lead / Maintainer
- **asoaib121** — Core product development, LLM integration, backend architecture  
  Repository: [Phishing_Link_Detection_Tools_With_LLM_Model](https://github.com/asoaib121/Phishing_Link_Detection_Tools_With_LLM_Model)

### UI / UX Design Contribution
Special thanks to **Md Rafiuddin Khan Rafi** for valuable contributions to the **user interface design** of this project (layout polish, visual structure, and design collaboration).

- GitHub: [@mdrafiuddinkhanrafi](https://github.com/mdrafiuddinkhanrafi)
- Profile: [Md Rafiuddin Khan Rafi](https://github.com/mdrafiuddinkhanrafi) — CSE student at Green University of Bangladesh; passionate about cybersecurity & software engineering

### Technologies & Libraries
- [Google Gemini API](https://ai.google.dev/)
- [Express](https://expressjs.com/)
- [Leaflet](https://leafletjs.com/)
- [jsPDF](https://github.com/parallax/jsPDF) / [jspdf-autotable](https://github.com/simonbengtsson/jsPDF-AutoTable)

If you contributed and are missing from this list, open an issue or PR and we will gladly update credits.

---

## ©️ Copyright & License

### Copyright Notice
```text
Copyright (c) 2026 CyberShield AI Contributors
Copyright (c) 2026 asoaib121 / Project Maintainers
```

This repository and its original source code, documentation, and design assets (except third-party libraries and explicitly credited contributions) are protected under applicable copyright law.

### License (MIT)
This project is released under the **MIT License**. See the full legal text in [`LICENSE`](./LICENSE).

**In plain terms (non-legal summary):**
- ✅ You may use, copy, modify, merge, publish, distribute, and sell copies of this software.
- ✅ You may use it for private and commercial projects.
- ⚠️ You **must** keep the copyright notice and license text in copies/substantial portions.
- ❌ The software is provided **“AS IS”** without warranty of any kind.
- ❌ Authors are **not liable** for damages arising from use of this software.

### Third-Party Notices
Third-party packages retain their own licenses (MIT/Apache/etc.). Using Gemini/OpenAI APIs is subject to the respective provider Terms of Service and usage quotas.

### Trademark / Branding
“CyberShield AI” is used here as the project product name. Do not imply official endorsement by Google, OpenAI, or other vendors without permission.

---

## ⚠️ Disclaimer

This tool is intended for **education, research, authorized testing, and defensive security workflows**.

- Do **not** use it to attack, harass, or scan systems/accounts you do not own or lack permission to test.
- LLM outputs can be incomplete or incorrect — always apply human judgment.
- Not a substitute for enterprise SOC tooling, legal advice, or certified forensic processes.

---

## 🤝 Contributing

Contributions are welcome:

1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/your-feature`)  
3. Commit clearly (`git commit -m "Add: your feature"`)  
4. Push and open a Pull Request  

Please avoid committing `.env`, API keys, or personal credentials.

---

## 📬 Contact / Links

- **Main Repo:** [asoaib121/Phishing_Link_Detection_Tools_With_LLM_Model](https://github.com/asoaib121/Phishing_Link_Detection_Tools_With_LLM_Model)
- **UI Design Credit:** [mdrafiuddinkhanrafi](https://github.com/mdrafiuddinkhanrafi)

---

<div align="center">

**Built for learning · cybersecurity · explainable AI**

⭐ If this project helps you, consider starring the repository.

`© 2026 CyberShield AI · Released under the MIT License`

</div>
