# CloudTelemetry & Incident Automation Platform

A cloud-native platform where servers report real-time metrics, security
events, and audit logs to a centralized dashboard. Built by a 6-person
team — each member owns one layer of the architecture.

## Architecture

```
Next.js Frontend UI
        │
API Gateway / Auth        (Security Lead)
        │
   ┌────┼────┐
Core   Analytics   Automated
Backend Pipeline   Test Suite
        │
GCP / Terraform + Docker/K8s + CI/CD    (Platform)
```

## Tech stack

| Layer          | Technology                        |
|----------------|-----------------------------------|
| Frontend       | Next.js (React) + Tailwind CSS    |
| Backend API    | Python + FastAPI                  |
| Database       | PostgreSQL + Redis                |
| Infrastructure | GCP + Terraform                   |
| Containers     | Docker + Kubernetes (GKE)         |
| CI/CD          | GitHub Actions                    |
| Security       | JWT / RBAC, Trivy, SonarQube      |
| Testing        | Pytest, Playwright, k6            |

## Team

| Role                          | Owns                         |
|-------------------------------|------------------------------|
| Lead Platform Engineer & SRE  | /infra, /k8s, /.github       |
| Backend & API Engineer        | /backend                     |
| Security & SecOps Engineer    | security config, CI scanning |
| Frontend & UI/UX Engineer     | /frontend                    |
| Data Analyst & BI Specialist  | /backend/analytics           |
| QA & Performance Engineer     | /tests                       |

## Getting started

1. Clone the repo
2. `cp .env.example .env` and fill in local values
3. `docker-compose up -d` — starts Postgres + Redis
4. Backend setup: see `/backend/README.md`
5. Frontend setup: see `/frontend/README.md`

## Contributing

- Branch naming: `type/short-description` — e.g. `feat/telemetry-ingest`
- Every change goes through a Pull Request. No direct pushes to `main`.
- 1 approval and a passing CI run required before merging.

## Status

Phase 1 — scaffolding complete. Phase 2 — infra and core services in progress.