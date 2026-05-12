# GitPulse

> AI Engineering Intelligence Agent — Google Cloud Rapid Agent Hackathon 2026

GitPulse is an Elastic-powered AI agent that continuously aggregates GitLab activity, generates automated standup reports, detects blockers, predicts sprint risk, and executes follow-up actions through GitLab MCP.

---

## Track

Elastic

---

## The Problem

Engineering teams lose hours every week to manual standups, undetected blockers, and slow pipeline triage. GitPulse eliminates that overhead by turning raw GitLab activity into actionable team intelligence — automatically, every morning.

---

## What GitPulse Does

- **Automated Daily Standup Reports** — agent reads GitLab activity via Elastic and generates a plain-English summary of what each developer did, what is active, and what is blocked
- **Blocker Detection** — identifies stale MRs, repeated CI failures, and untouched issues before standup begins
- **Sprint Risk Prediction** — analyses backlog velocity, merge throughput, and pipeline health to flag delivery risk early
- **Workload Insights** — detects overloaded reviewers and uneven contribution patterns
- **Automated Actions** — creates GitLab issues, assigns reviewers, and posts summaries via GitLab MCP

---

## Architecture

```
GitLab Activity
      │
      ▼
Elastic MCP (Intelligence Layer)
  - Ingests commits, MRs, pipelines, issues
  - Aggregates metrics
  - Detects patterns and blockers
      │
      ▼
Gemini via Google Cloud Agent Builder (Reasoning Layer)
  - Analyses structured Elastic data
  - Generates summaries and risk assessments
  - Plans follow-up actions
      │
      ▼
GitLab MCP (Action Layer)
  - Creates issues
  - Assigns reviewers
  - Posts standup summaries
  - Re-runs failed pipelines
      │
      ▼
React Dashboard (Frontend)
  - Dashboard, History, Setup, Run pages
  - Hosted on Vercel / Cloud Run
```

See [docs/architecture.png](docs/architecture.png) for the full diagram.

---

## Tech Stack

| Layer | Technology |
|---|---|
| AI / Agent Orchestration | Google Cloud Agent Builder + Gemini |
| Intelligence Engine | Elastic MCP |
| Action Execution | GitLab MCP |
| Backend | Python + FastAPI on Cloud Run |
| Frontend | React + Shadcn/UI |
| Scheduling | Google Cloud Scheduler |
| Secrets | Google Cloud Secret Manager |
| Hosting | Google Cloud Run + Vercel |

---

## Team

| Name | Role |
|---|---|
| [Name 1] | AI / Agent Engineer |
| [Name 2] | Backend + Cloud Engineer |
| [Name 3] | Frontend Engineer |
| [Name 4] | Frontend + Demo Lead |

---

## Live Demo

> [URL will be added before submission]

## Demo Video

> [YouTube link will be added before submission]

---

## Getting Started

See [docs/SETUP.md](docs/SETUP.md) for full local setup instructions.

### Quick start

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/gitpulse.git
cd gitpulse

# Backend
cd backend
pip install -r requirements.txt
cp .env.example .env   # fill in your credentials
python main.py

# Frontend
cd ../frontend
npm install
npm run dev
```

---

## Environment Variables

All secrets are stored in **Google Cloud Secret Manager**. For local development, copy `.env.example` to `.env` and fill in values. Never commit `.env` to Git.

| Variable | Description |
|---|---|
| `GEMINI_API_KEY` | Gemini API key from Google AI Studio |
| `ELASTIC_URL` | Elastic cluster endpoint |
| `ELASTIC_API_KEY` | Elastic API key |
| `GITLAB_TOKEN` | GitLab Personal Access Token |
| `GITLAB_PROJECT_ID` | GitLab project to monitor |

---

## License

MIT — see [LICENSE](LICENSE)