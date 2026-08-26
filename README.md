<div align="center">

# MRITYUNJAY LAD

### Backend Engineer · Python · FastAPI · PostgreSQL · Distributed Systems

**I build backend systems that deal with real-world complexity: concurrency, distributed state, asynchronous work, data integrity, and failure.**

<br>

[![GitHub](https://img.shields.io/badge/GitHub-ladmrityunjay80--ui-181717?style=for-the-badge&logo=github)](https://github.com/ladmrityunjay80-ui)
[![Email](https://img.shields.io/badge/Email-ladmrityunjay80%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ladmrityunjay80@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/)

</div>

---

## 👋 WHO I AM

I'm a self-taught software engineer transitioning from **5+ years in B2B SaaS and enterprise technology** into backend engineering.

I learn by building complete systems — not just isolated demos.

My portfolio deliberately covers:

- API design
- relational data modelling
- authentication and authorization
- asynchronous processing
- queues and workers
- real-time communication
- distributed state
- caching and streams
- rate limiting
- circuit breakers
- reconciliation
- observability
- AI-powered automation

> **I don't want to just say I know a technology. I want the repository to show where I used it, why I used it, and what problem it solved.**

---

# 🚀 ENGINEERING PORTFOLIO

The projects below are the core of my portfolio.

**Every project links directly to its source repository.**  
Open the repository to inspect the implementation, project structure, tests, infrastructure and documentation.

---

# 01 · SYNCCANVAS

## 🎨 High-Concurrency Real-Time Collaboration

**Problem:** synchronize multiple users editing the same canvas while handling reconnects, permissions, quotas and missed events.

### Architecture

```text
                         ┌─────────────────┐
                         │     React UI    │
                         │ TypeScript/Vite │
                         └────────┬────────┘
                                  │
                             WebSocket
                                  │
                                  ▼
                         ┌─────────────────┐
                         │     FastAPI     │
                         │  Room Gateway   │
                         └───────┬─────────┘
                                 │
                    ┌────────────┼────────────┐
                    ▼            ▼            ▼
              Redis Pub/Sub  Redis Streams  PostgreSQL
                    │            │            │
                    ▼            ▼            ▼
               Fan-out       Replay       Persistence
```

### What the code demonstrates

- Real-time multi-user collaboration
- Typed Pydantic WebSocket envelopes
- Redis Pub/Sub fan-out
- Redis Streams replay buffer
- Reconnect with `last_event_id`
- Presence cursors
- JWT authentication
- Editor / viewer permissions
- Message rate limiting
- Board and element quotas
- Leader-elected background workers
- Client-side undo / redo
- PNG / SVG export
- Health and metrics endpoints
- GitHub Actions CI/CD

### Stack

`FastAPI` `WebSockets` `Redis Pub/Sub` `Redis Streams` `PostgreSQL` `Alembic` `React` `TypeScript` `Tailwind` `Zustand`

### 🔎 SOURCE

**[→ OPEN REPOSITORY](https://github.com/ladmrityunjay80-ui/SyncCanvas)**

**[→ BACKEND SOURCE](https://github.com/ladmrityunjay80-ui/SyncCanvas/tree/main/backend)**

**[→ FRONTEND SOURCE](https://github.com/ladmrityunjay80-ui/SyncCanvas/tree/main/frontend)**

---

# 02 · GATEFLOW

## 🚪 API Gateway & Distributed Rate Limiter

**Problem:** protect downstream microservices while routing requests, authenticating clients, enforcing limits and surviving backend failures.

### Architecture

```text
                         INTERNET
                             │
                             ▼
                        ┌─────────┐
                        │  Nginx  │
                        └────┬────┘
                             │
                 ┌───────────┴───────────┐
                 ▼                       ▼
          ┌─────────────┐         ┌─────────────┐
          │ GateFlow A  │         │ GateFlow B  │
          └──────┬──────┘         └──────┬──────┘
                 │                       │
                 └───────────┬───────────┘
                             ▼
                        ┌─────────┐
                        │  Redis  │
                        └────┬────┘
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
        users-service  orders-service    metrics
```

### What the code demonstrates

- API-key authentication
- HMAC-SHA256 key hashing at rest
- Constant-time admin key comparison
- Atomic Redis Lua token buckets
- Tier-based rate limiting
- Stateful circuit breakers
- Dynamic route configuration
- Hot-reload route invalidation
- Streaming request / response proxying
- Redis Sentinel / HA support
- Audit streams
- Telemetry streams
- Prometheus metrics
- Structured JSON logging
- Consolidated downstream OpenAPI

### Stack

`Python` `FastAPI` `Redis` `Lua` `Nginx` `Prometheus` `Docker`

### 🔎 SOURCE

**[→ OPEN REPOSITORY](https://github.com/ladmrityunjay80-ui/GateFlow)**

**[→ VIEW DOCUMENTATION](https://github.com/ladmrityunjay80-ui/GateFlow/tree/main/docs)**

---

# 03 · SCRAPEMESH

## ⚡ Distributed Web Scraping & Parsing

**Problem:** distribute scraping workloads across workers while respecting domain limits, retries, `robots.txt`, proxy failures and result aggregation.

### Architecture

```text
                    ┌──────────────┐
                    │ FastAPI API  │
                    └──────┬───────┘
                           │
                           ▼
                     ┌───────────┐
                     │ RabbitMQ  │
                     └─────┬─────┘
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
         Worker 1      Worker 2      Worker 3
             │             │             │
             └─────────────┼─────────────┘
                           │
                ┌──────────┼──────────┐
                ▼          ▼          ▼
              Redis    PostgreSQL   MinIO
             metrics    results     raw HTML
```

### What the code demonstrates

- Celery distributed workers
- RabbitMQ task broker
- Redis result backend
- Multi-domain adapter pattern
- CSS / XPath extraction
- Proxy rotation
- Proxy failure eviction
- `robots.txt` compliance
- Per-domain concurrency slots
- Randomized delays
- Redis atomic batch counters
- Celery chord finalization
- Dead-letter queue
- Gzipped raw HTML cold storage
- VADER sentiment analysis
- Flower monitoring
- Structured JSON logging

### Stack

`FastAPI` `Celery` `RabbitMQ` `Redis` `PostgreSQL` `MinIO` `httpx` `Docker`

### 🔎 SOURCE

**[→ OPEN REPOSITORY](https://github.com/ladmrityunjay80-ui/ScrapeMesh)**

---

# 04 · ANALYTICS & OPERATIONS

## 📊 Payment Reconciliation + Financial Analytics Platform

**Problem:** ingest operational and payment data from multiple sources, reconcile transactions, expose business metrics and monitor the pipeline.

### Data Flow

```text
 PostgreSQL ───────┐
 Stripe ───────────┤
 Razorpay ─────────┤
 CSV / Excel / JSON ┤
                   ▼
             ┌─────────────┐
             │  Ingestion  │
             └──────┬──────┘
                    ▼
             ┌─────────────┐
             │ Reconcile   │
             └──────┬──────┘
                    ▼
          ┌─────────┼─────────┐
          ▼         ▼         ▼
       Metrics   Alerts    Forecasting
          │         │         │
          └─────────┼─────────┘
                    ▼
              Live Dashboard
```

### What the code demonstrates

- Multi-source ingestion
- Stripe / Razorpay reconciliation
- Transaction matching
- Revenue analytics
- MRR / ARPU
- Gateway and product metrics
- Operational metrics
- Forecasting
- Model retraining
- Drift detection
- Model registry
- Threshold alerts
- Email / Slack notifications
- JWT + RBAC
- TOTP MFA
- OAuth2 / OIDC SSO
- Refresh-token rotation
- OpenTelemetry
- Prometheus
- Sentry
- Jaeger / OTLP
- Health checks
- Operational runbooks
- Rate limiting
- Audit logging
- DVC-lite artifact versioning

### Stack

`FastAPI` `PostgreSQL` `SQLAlchemy Async` `Celery` `Redis` `Next.js` `TypeScript` `AWS S3` `Docker` `Kubernetes`

### 🔎 SOURCE

**[→ OPEN REPOSITORY](https://github.com/ladmrityunjay80-ui/Analytics_And_Operations_Tool)**

**[→ ARCHITECTURE](https://github.com/ladmrityunjay80-ui/Analytics_And_Operations_Tool/tree/main/docs/architecture)**

**[→ RUNBOOKS](https://github.com/ladmrityunjay80-ui/Analytics_And_Operations_Tool/tree/main/docs/runbooks)**

---

# 05 · AI WORKFLOW AUTOMATION

## 🤖 Multi-Tenant AI Workflow Platform

**Problem:** turn business processes into executable, observable workflows while supporting AI decisions, documents, multi-tenancy and background processing.

### Architecture

```text
                 ┌──────────────────┐
                 │    React UI      │
                 │ Workflow Editor  │
                 └────────┬─────────┘
                          │
                          ▼
                   ┌─────────────┐
                   │   FastAPI   │
                   └──────┬──────┘
                          │
             ┌────────────┼────────────┐
             ▼            ▼            ▼
         PostgreSQL     Redis       AWS S3
             │            │            │
             │         Celery           │
             │            │             │
             └────────────┼─────────────┘
                          ▼
                    AI Providers
                  OpenAI / Anthropic
```

### What the code demonstrates

- AI-powered workflow execution
- Multi-tenant organizations
- Workspace isolation
- RBAC
- JSON / YAML workflow definitions
- Sequential execution
- Parallel execution
- Retry and error handling
- WebSocket execution monitoring
- Workflow versioning
- Rollback
- PDF processing
- Email/document parsing
- AI structured extraction
- Invoice processing
- Resume matching
- Email triage
- S3 document storage
- Email / Slack / webhook notifications

### Stack

`FastAPI` `PostgreSQL` `SQLAlchemy` `Celery` `Redis` `React` `Vite` `Zustand` `OpenAI` `Anthropic` `AWS S3`

### 🔎 SOURCE

**[→ OPEN REPOSITORY](https://github.com/ladmrityunjay80-ui/AI_Enhanced_Workflow_Automation_Tool)**

---

# 06 · E-COMMERCE & SaaS DASHBOARD

## 🛒 Full-Stack Business Management Platform

**Problem:** build a realistic SaaS application where authentication, permissions, payments, inventory, subscriptions, background jobs and real-time data all interact.

### System

```text
React / TypeScript
        │
        ▼
     FastAPI
        │
 ┌──────┼──────────┐
 ▼      ▼          ▼
Postgres Redis    Celery
 │                 │
 └──────┬──────────┘
        ▼
 Payments / Storage / Email
```

### What the code demonstrates

- User management
- RBAC
- Permission-gated UI
- Customer management
- Product management
- Inventory
- Orders
- Atomic stock handling
- Subscriptions
- Trials
- Plans
- Categories
- Invoices
- Payment processing
- Stripe
- Razorpay
- PayPal
- OAuth
- JWT access / refresh tokens
- Webhook signature verification
- Real-time dashboards
- Celery background jobs
- Redis
- S3 / Cloudinary
- GitHub Actions CI/CD
- Backend and frontend tests

### Stack

`React` `TypeScript` `Vite` `FastAPI` `PostgreSQL` `SQLAlchemy` `Zustand` `Redis` `Celery` `Recharts`

### 🔎 SOURCE

**[→ OPEN REPOSITORY](https://github.com/ladmrityunjay80-ui/E_Commerce_And_SaaS_Dashboard)**

---

# 07 · CRM BACKEND + FRONTEND

## 💼 Full-Stack CRM

This project is particularly meaningful because it connects my **previous B2B SaaS / sales background** with software engineering.

### Backend

```text
FastAPI
   │
   ├── Authentication
   ├── Users
   ├── Leads
   ├── Contacts
   ├── Companies
   ├── Deals
   ├── Activities
   └── Products
          │
          ▼
      PostgreSQL
```

### What the code demonstrates

- FastAPI REST APIs
- JWT authentication
- Password hashing
- RBAC
- SQLAlchemy models
- Pydantic schemas
- PostgreSQL
- CRUD API design
- Database configuration
- API versioning
- OpenAPI / Swagger documentation
- React + TypeScript frontend
- React Query
- Zustand
- Protected routes
- Dashboard
- Leads management

### 🔎 SOURCE

**[→ OPEN GITHUB PROFILE / REPOSITORIES](https://github.com/ladmrityunjay80-ui?tab=repositories)**

---

# 🧭 REPOSITORY MAP

| Repository | Primary Engineering Problem | Core Technologies |
|---|---|---|
| **[SyncCanvas](https://github.com/ladmrityunjay80-ui/SyncCanvas)** | Real-time distributed state | FastAPI · WebSockets · Redis Streams |
| **[GateFlow](https://github.com/ladmrityunjay80-ui/GateFlow)** | Gateway / rate limiting | FastAPI · Redis · Lua · Nginx |
| **[ScrapeMesh](https://github.com/ladmrityunjay80-ui/ScrapeMesh)** | Distributed workloads | Celery · RabbitMQ · Redis |
| **[Analytics & Operations](https://github.com/ladmrityunjay80-ui/Analytics_And_Operations_Tool)** | Reconciliation / analytics | FastAPI · PostgreSQL · Celery |
| **[AI Workflow Automation](https://github.com/ladmrityunjay80-ui/AI_Enhanced_Workflow_Automation_Tool)** | AI workflow execution | FastAPI · Celery · Redis · AI |
| **[SaaS Dashboard](https://github.com/ladmrityunjay80-ui/E_Commerce_And_SaaS_Dashboard)** | Full-stack SaaS | React · FastAPI · PostgreSQL |
| **CRM** | Business application / APIs | FastAPI · PostgreSQL · React |

---

# 🔬 CODE-FIRST ENGINEERING

I prefer to make engineering decisions visible in the code.

## Distributed Systems

```text
RabbitMQ
   │
   ├── Celery workers
   │
   └── Dead-letter queues

Redis
   │
   ├── Pub/Sub
   ├── Streams
   ├── Rate limits
   ├── Caching
   └── Atomic counters
```

## Real-Time Systems

```text
Client
  │
  │ WebSocket
  ▼
FastAPI
  │
  ▼
Redis Pub/Sub
  │
  ├── Room fan-out
  └── Presence

Redis Streams
  │
  └── Missed-event replay
```

## Reliability

```text
Request
  │
  ├── Authentication
  ├── Rate limit
  ├── Validation
  ├── Routing
  ├── Retry / fallback
  ├── Circuit breaker
  └── Observability
```

## Data Integrity

```text
Raw Sources
    ↓
Normalization
    ↓
Matching
    ↓
Reconciliation
    ↓
Validation
    ↓
Analytics / Alerts
```

---

# 🧠 ENGINEERING PRINCIPLES

### 1. Build the whole path

I learn fastest when I can trace a request from:

`client → API → database → queue → worker → external service → result`

### 2. Make failure explicit

A system isn't interesting only when everything works.

I care about:

- retries
- reconnects
- duplicate events
- rate limits
- stale state
- worker failure
- dependency failure
- partial processing
- dead-letter queues
- circuit breakers

### 3. Use the right data store for the job

PostgreSQL for durable relational state.

Redis for fast state, coordination, streams and rate limiting.

Object storage for large artifacts.

Queues for asynchronous work.

### 4. Observe what you build

I increasingly treat:

`logs + metrics + traces + health checks + runbooks`

as part of the system rather than an afterthought.

---

# 🛠️ TECHNOLOGY STACK

### Backend

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square)

### Frontend

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)

### Databases / Messaging

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat-square&logo=celery&logoColor=white)

### Infrastructure / Observability

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)

---

# 📈 GITHUB ACTIVITY

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=ladmrityunjay80-ui&show_icons=true&include_all_commits=true&hide_border=true&rank_icon=github" height="170" alt="GitHub statistics">

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ladmrityunjay80-ui&layout=compact&langs_count=8&hide_border=true" height="170" alt="Top languages">

<br><br>

<img src="https://streak-stats.demolab.com?user=ladmrityunjay80-ui&hide_border=true" alt="GitHub contribution streak">

</div>

---

# 🎯 CURRENT DIRECTION

```text
Python
   ↓
FastAPI
   ↓
PostgreSQL
   ↓
Redis
   ↓
Async Processing
   ↓
Distributed Systems
   ↓
Observability
   ↓
Production Engineering
```

I'm currently focused on becoming a stronger **backend / platform engineer**, particularly around:

- system design
- distributed systems
- API architecture
- PostgreSQL
- Redis
- asynchronous processing
- real-time systems
- reliability
- performance
- testing
- observability
- AI-enabled backend systems

---

# 💼 FROM B2B SAAS TO SOFTWARE ENGINEERING

Before software engineering, I spent **5+ years in B2B SaaS and enterprise technology**.

That background is directly useful when building software.

I understand:

- customer workflows
- business requirements
- CRM processes
- enterprise buying environments
- product demonstrations
- operational pain points
- translating business problems into software requirements

My CRM project is an example of that overlap: the domain knowledge from my previous career influenced the way I approached the system.

> **I bring both sides of the problem: understanding what the business needs and learning how to build the system that delivers it.**

---

# 🔗 START HERE

If you're a recruiter or engineering manager, these are the repositories I'd recommend opening first:

### 🥇 SyncCanvas
**Best representation of:** real-time systems + distributed state

→ **[OPEN SOURCE](https://github.com/ladmrityunjay80-ui/SyncCanvas)**

### 🥈 GateFlow
**Best representation of:** backend infrastructure + reliability

→ **[OPEN SOURCE](https://github.com/ladmrityunjay80-ui/GateFlow)**

### 🥉 ScrapeMesh
**Best representation of:** distributed workers + asynchronous processing

→ **[OPEN SOURCE](https://github.com/ladmrityunjay80-ui/ScrapeMesh)**

### 📊 Analytics & Operations
**Best representation of:** data pipelines + reconciliation + observability

→ **[OPEN SOURCE](https://github.com/ladmrityunjay80-ui/Analytics_And_Operations_Tool)**

### 🤖 AI Workflow Automation
**Best representation of:** AI + backend architecture + workflows

→ **[OPEN SOURCE](https://github.com/ladmrityunjay80-ui/AI_Enhanced_Workflow_Automation_Tool)**

### 🛒 SaaS Dashboard
**Best representation of:** full-stack SaaS + business logic

→ **[OPEN SOURCE](https://github.com/ladmrityunjay80-ui/E_Commerce_And_SaaS_Dashboard)**

---

# 🤝 CONTACT

**Mrityunjay Lad**

📍 Pune, Maharashtra, India

📧 **[ladmrityunjay80@gmail.com](mailto:ladmrityunjay80@gmail.com)**

🔗 **[GitHub](https://github.com/ladmrityunjay80-ui)**

🔗 **[LinkedIn](https://www.linkedin.com/)**

---

<div align="center">

### Build systems. Understand failure. Keep learning.

</div>
