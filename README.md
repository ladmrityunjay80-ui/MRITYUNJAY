# Hi, I'm Mrityunjay Lad 👋

### Software Engineer | Python Backend | FastAPI | PostgreSQL

I'm a self-taught software engineer transitioning from 5+ years in B2B SaaS and enterprise technology.

I learned software development by building things from scratch - starting with business applications and gradually moving into APIs, databases, background processing, real-time systems, distributed services, and automation.

I enjoy understanding how a system works end-to-end, finding where it breaks, and then fixing it.

---

## 🧑‍💻 What I Work With

### Backend
- Python
- FastAPI
- SQLAlchemy
- Pydantic
- REST APIs
- Celery
- Uvicorn
- JWT / OAuth2
- WebSockets

### Databases & Data
- PostgreSQL
- Redis
- ClickHouse
- SQLAlchemy Async
- Alembic
- Data reconciliation
- Analytics pipelines

### Frontend
- React
- TypeScript
- Vite
- Zustand
- Tailwind CSS
- shadcn/ui
- Recharts

### Distributed Systems & Infrastructure
- Docker
- RabbitMQ
- Redis Streams / Pub/Sub
- Microservices
- Background workers
- API gateways
- Rate limiting
- Circuit breakers
- Distributed locks
- AWS S3 / MinIO
- GitHub Actions

---

## 🚀 Things I've Built

### 🏢 MJ ERP — Multi-Tenant SaaS ERP

A large multi-tenant ERP system covering business operations across:

**Sales · CRM · Inventory · Procurement · Accounting · HR · Production · Subscriptions · Audit · Integrations**

Built around FastAPI, PostgreSQL, Redis and Celery with:

- Multi-tenant architecture
- RBAC
- JWT authentication
- Async SQLAlchemy
- Background task processing
- Payment integrations
- Audit logging
- Rate limiting
- Database migrations
- Transaction-boundary protection

One of the main engineering concerns was keeping external API calls outside database transactions and pushing them into background workers.

---

### ⚡ ScrapeMesh — Distributed Web Scraping System

A microservices-based scraping and parsing engine.

**FastAPI · Celery · RabbitMQ · Redis · PostgreSQL · MinIO**

It includes:

- Distributed scraping workers
- Multi-domain adapters
- Proxy rotation
- `robots.txt` compliance
- Per-domain concurrency limits
- Randomized request delays
- Redis-backed counters
- Dead-letter queues
- Raw HTML archival
- Sentiment analysis
- Flower monitoring

The system processes URLs asynchronously and uses Celery chords to finalize batch-level results.

---

### 🎨 SyncCanvas — Real-Time Collaborative Canvas

A high-concurrency collaborative drawing application.

**FastAPI · WebSockets · Redis Pub/Sub · Redis Streams · PostgreSQL · React · TypeScript**

Built with:

- Real-time multi-user collaboration
- Presence cursors
- WebSocket message validation
- Redis Streams replay
- Reconnection support
- JWT authentication
- Editor / viewer permissions
- Rate limiting
- Quotas
- Leader-elected background workers
- Undo / redo
- PNG / SVG export

---

### 🚪 GateFlow — API Gateway & Rate Limiter

A developer-focused API gateway built with FastAPI and Redis.

It handles:

- API-key authentication
- HMAC-SHA256 key storage
- Token-bucket rate limiting
- Atomic Redis Lua scripts
- Circuit breaking
- Dynamic routing
- Streaming proxying
- Redis Sentinel / HA support
- Prometheus metrics
- Structured logging
- Audit streams

The goal was to understand what happens between a client request and the actual backend services.

---

### 🤖 AI Workflow Automation

A multi-tenant workflow automation platform using AI for business processes.

**FastAPI · PostgreSQL · Celery · Redis · React · OpenAI · Anthropic**

Features include:

- AI-powered workflow execution
- PDF/document processing
- Resume matching
- Invoice processing
- Email triage
- Workflow versioning
- Rollback
- RBAC
- WebSocket execution updates
- S3 document storage
- Email / Slack / webhook notifications

---

### 📊 Analytics & Operations Tool

A financial analytics and payment reconciliation system.

**FastAPI · PostgreSQL · SQLAlchemy Async · Celery · Redis**

The system works with data from multiple sources and focuses on:

- Payment reconciliation
- Revenue analytics
- MRR / ARPU
- Transaction matching
- Operational metrics
- Forecasting
- Alerts
- Audit logs
- Distributed tracing
- Health checks

I'm particularly interested in the engineering problems around reliable data processing and reconciliation.

---

### 🛒 E-Commerce & SaaS Admin Dashboard

A full-stack business management dashboard.

**React · TypeScript · FastAPI · PostgreSQL · SQLAlchemy · Zustand · Recharts**

Includes:

- Customer management
- Products
- Orders
- Subscriptions
- Invoices
- Payments
- Analytics
- RBAC
- Real-time updates
- Background jobs
- OAuth
- Webhook verification

---

### 💼 CRM — Full-Stack CRM Application

One of my first major projects and especially relevant to my previous career in B2B sales.

**Python · FastAPI · PostgreSQL · SQLAlchemy · Pydantic · JWT · Alembic**

Built from scratch with:

- Leads
- Contacts
- Deals
- Authentication
- Authorization
- Relational data modelling
- REST APIs
- Database migrations
- OpenAPI documentation

My previous experience working with CRM and sales workflows directly influenced how I designed this system.

---

### 💰 ArbitrageX — Distributed Price Arbitrage Pipeline

An experimental distributed pipeline for finding price differences across e-commerce sources.

**Redis Streams · ClickHouse · PostgreSQL · FastAPI · RabbitMQ · Docker**

The architecture separates:

`Gateway → Scraping → Scheduling → Streaming → Arbitrage Engine → Analytics → Actions`

It uses PostgreSQL for transactional data and ClickHouse for analytical workloads.

---

## 🧠 How I Like to Build

I tend to learn by building.

Instead of stopping at:

> "I know FastAPI."

I prefer getting to:

> "I built an API with FastAPI, connected it to PostgreSQL, added authentication, put background work behind Celery, introduced Redis, tested failure cases, and then figured out what broke when the pieces interacted."

That's where most of my learning happens.

I'm particularly interested in:

- Backend engineering
- API design
- PostgreSQL and data modelling
- Distributed systems
- Async processing
- Real-time applications
- System reliability
- Performance and debugging
- Automation
- AI-powered applications

---

## 🔧 Current Focus

Right now I'm focusing on becoming a stronger backend engineer, particularly around:

**Python → FastAPI → PostgreSQL → Redis → Distributed Systems → Production Engineering**

I'm also continuing to improve my understanding of system design, testing, observability, performance, and deployment.

---

## 📚 Background

Before moving into software development, I spent 5+ years working in B2B SaaS and enterprise technology.

That experience taught me something I still find useful when building software:

**understand the business problem before trying to solve the technical problem.**

I've worked with customers, enterprise environments, sales cycles, product demonstrations and business requirements.

Now I'm bringing that understanding into software development.

---

## 📌 A Few Things About Me

- I prefer building over following tutorials.
- I enjoy debugging problems that don't have an obvious answer.
- I like understanding systems end-to-end.
- I'm comfortable learning unfamiliar technologies when the problem requires them.
- I care about how software behaves under failure, not just when everything works.
- I'm currently looking for opportunities to grow as a software/backend engineer.

---

## 🤝 Let's Connect

If you're working on backend systems, distributed applications, SaaS products, automation, or just like building interesting things, feel free to connect.

**Mrityunjay Lad**

📍 Pune, Maharashtra  
📧 ladmrityunjay80@gmail.com

[LinkedIn](https://www.linkedin.com/in/mrityunjay-lad-5b901b179/) · [GitHub](https://github.com/ladmrityunjay80-ui)
