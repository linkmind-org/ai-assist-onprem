# 🧠 Personal AI Assistant – On-Prem Model & Data Server

This repository contains the **on-premises infrastructure** for hosting AI models and data sources in a distributed, self-contained environment. Designed with cost-effectiveness and privacy in mind, the system runs on repurposed hardware like Intel NUCs, old set-top boxes, and commodity drives connected through local networking gear.

> ⚙️ A personal "AI cluster" built from reused components—empowering local, private intelligence.

---

## 🎯 Purpose

Create a **fully local, offline-capable grid** to host LLMs and personal data sources for an AI assistant. This system supports inference, document ingestion, and vector search—without relying on any external cloud infrastructure unless explicitly configured.

---

## 🛠️ Tech Stack (Planned)

- **Docker + Docker Compose** – Container orchestration
- **Ollama / vLLM / LocalAI** – Lightweight, local LLM runners
- **ChromaDB / Qdrant / Weaviate** – Vector DBs for embeddings
- **FastAPI / Flask** – Gateway APIs for LLM and embedding access
- **Redis / NATS** – Message brokering and distributed task coordination
- **Airflow / Prefect** – Ingestion and data sync pipelines
- **Traefik / NGINX** – Routing and TLS support
- **OpenTelemetry + Grafana** – Monitoring and observability
- **Tailscale / Zerotier** – Optional P2P networking

---

## 🧱 Hardware Architecture

- **Nodes**: Intel NUCs, set-top boxes with at least 4GB RAM & 2-core CPU
- **Storage**: Local HDDs/SSDs (1–4 TB) per node for redundancy
- **Network**: Old consumer-grade switches with static IP or mDNS-based addressing
- **Cooling/Power**: Minimal (passive setups encouraged)

> Power-efficient, self-hosted edge computing for AI workloads.

---

## 🗂️ Project Structure (Planned)

```
onprem/
├── docker/
│   ├── ollama/             # LLM container with models
│   ├── chromadb/           # Vector DB setup
│   ├── ingest/             # File & document pipelines
│   ├── gateway/            # Unified API access layer
│   └── traefik/            # Reverse proxy and routing
├── scripts/                # Setup and dev tooling
├── node-configs/           # Host-specific settings
├── config/                 # Model configs, secrets, etc.
├── .env
├── docker-compose.yml
└── README.md
```

---

## 🔧 Features

| Feature                                | Status  | Notes |
|----------------------------------------|---------|-------|
| Distributed model runner grid          | 🔲 Todo | Multi-node Ollama or vLLM |
| Shared vector DB for knowledge queries | 🔲 Todo | ChromaDB with ingestion |
| File & doc ingestion pipelines         | 🔲 Todo | PDFs, .txt, .md files |
| Private LLM gateway API                | 🔲 Todo | For frontend/backend access |
| P2P node discovery                     | 🔲 Todo | Tailscale, Zerotier optional |
| Monitoring and telemetry               | 🔲 Todo | Resource use, uptime, queue status |
| Offline-first design                   | ✅ Base | Core premise of system |

---

## 🚀 Getting Started

1. **Clone the repo**

```bash
git clone https://github.com/your-username/personal-ai-assistant-onprem.git
cd personal-ai-assistant-onprem
```

2. **Create `.env` file**

```bash
cp .env.example .env
# Edit with model paths, ports, secrets
```

3. **Start the stack**

```bash
docker-compose up --build
```

Each node will run a subset of services and sync to a shared vector or messaging layer.

---

## 🔐 Design Principles

- **Privacy by default** – All inference and data stays local
- **Reuse and recycle** – Built to run on old hardware
- **Modular and maintainable** – Services are containerized
- **Scalable locally** – Add more nodes for redundancy or power

---

## 📅 Roadmap

- [ ] Compose + Swarm-ready service layout
- [ ] Ollama + ChromaDB integration
- [ ] Embedding and QA endpoint
- [ ] Local notes/document indexer
- [ ] Web dashboard for cluster status
- [ ] Offline model auto-download manager
- [ ] External access via private gateway (optional)

---

## 📜 License

MIT License – make it your own and keep it local.

---

> 🧩 Reimagining smart assistants with low-cost edge computing and total control.
