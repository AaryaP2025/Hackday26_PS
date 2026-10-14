# DepShield AI — Dependency Resilience Analyzer

> **Hackathon Submission** | Track 1: Gemma 4 Dependency Resilience | Track 2: Maintenance Agent Skill

An AI-powered developer tool that helps maintainers identify, understand, and resolve dependency risks in any GitHub repository — powered by **Gemma 4** (via Google AI Studio).

---

## 🚀 Quick Start

### 1. Prerequisites
- Node.js 18+
- A [Google AI Studio](https://aistudio.google.com/apikey) API Key (for Gemma 4)
- *(Optional)* A GitHub Personal Access Token (increases API rate limits)

### 2. Install & Run
```bash
# Clone / navigate to project
cd dep-resilience

# Install dependencies
npm install

# Start the server
npm start
```

Then open **http://localhost:3000** in your browser.

### 3. Configure API Keys
In the app, click **"Configure API Keys"** and enter:
- **Google AI Studio API Key** — required for Gemma 4 analysis
- **GitHub Token** — optional, raises rate limit from 60 to 5000 req/hour

---

## 🎯 What It Does

### For Any GitHub Repository:

1. **🔍 Dependency Risk Detection** — Fetches and parses dependency manifests (package.json, requirements.txt, go.mod, Cargo.toml, Gemfile, pom.xml, pubspec.yaml) and runs **Gemma 4** AI analysis to identify at-risk packages.

2. **🗺️ Usage Mapping** — Uses GitHub Search API + AI to find exactly where each dependency is imported/used in the codebase.

3. **🚀 Migration Plans** — AI-generated step-by-step replacement guides for each at-risk dependency.

4. **📦 Dependency Exit Capsules** — Reusable, exportable Markdown documents containing:
   - Dependency details
   - Risk indicators (AI-Inferred vs Observed)
   - Usage locations
   - Proposed replacement
   - Migration steps
   - Test suggestions
   - Compatibility gaps
   - Open concerns

5. **💬 AI Chat** — Ask Gemma 4 any questions about the repository's dependencies.

---

## 🤖 AI Model

| Property | Value |
|---|---|
| Model | **Gemma 4** (`gemma-3-27b-it`) |
| Access Method | Google AI Studio API |
| Provider | Google DeepMind |
| Track | Track 1: Dependency Resilience |

---

## 📋 Supported Package Managers

| Ecosystem | File |
|---|---|
| Node.js / npm | `package.json` |
| Python / pip | `requirements.txt` |
| Go | `go.mod` |
| Rust | `Cargo.toml` |
| Ruby | `Gemfile` |
| Java / Maven | `pom.xml` |
| Dart / Flutter | `pubspec.yaml` |

---

## 🏗️ Architecture

```
dep-resilience/
├── server.js              # Express server entry point
├── routes/
│   └── api.js             # REST API endpoints
├── services/
│   ├── github.js          # GitHub API client
│   ├── ai.js              # Gemma 4 AI service
│   └── parser.js          # Multi-ecosystem dep parser
└── public/
    ├── index.html         # Frontend SPA
    ├── css/style.css      # Design system
    └── js/app.js          # Frontend logic
```

### API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/api/analyze` | POST | Full repo analysis |
| `/api/dependency-detail` | POST | Usage map for specific dep |
| `/api/exit-capsule` | POST | Generate Exit Capsule |
| `/api/chat` | POST | AI chat about deps |

---

## ⚠️ Important Notes

- **AI recommendations are clearly labeled** 🤖 vs **observed data** ✅
- All AI analysis requires human verification before applying to production
- GitHub API unauthenticated rate limit: 60 req/hour (use a token to increase to 5000)
- The Gemma model used: `gemma-3-27b-it` via Google AI Studio

---

## 📜 License

MIT — Open Source

---

*DepShield AI · Powered by Gemma 4 · Track 1 & 2 Submission*
