# Triage-Plus-Plus
Triage++ SOC Automation Project
#  Triage++ – SOC Automation Platform

Triage++ is a Security Operations Center (SOC) Automation Platform designed to intelligently score, classify, and route security alerts using rule-based logic and machine learning.

It reduces analyst fatigue, minimizes false positives, and enables faster incident response.

---

##  Core Capabilities

-  ML-based Risk Scoring Engine
-  Automated Decision Logic (Suppress / Queue / Escalate)
-  Real-time Elastic + Kibana Integration
-  Risk Threshold Visualization Dashboard
-  Dockerized Deployment
-  PostgreSQL Support
-  Elastic Bulk Alert Injection
-  Alert Explainability Layer

---
```

---

##  Architecture Overview

Elastic Alerts
      ↓
Triage++ Engine
      ↓
Risk Scoring + Normalization
      ↓
Decision Layer (Suppress / Queue / Escalate)
      ↓
Elastic Writer
      ↓
Kibana Dashboard


---
```

---

##  Decision Logic

| Risk Score | Decision   |
|------------|------------|
| ≤ 35       | SUPPRESS   |
| 36 – 50    | QUEUE      |
| > 50       | ESCALATE   |
```

---

##  Dashboard Highlights

- Executive KPIs (Escalation Rate / Queue Rate / Suppress Rate)
- Risk Distribution Histogram
- Decision Alignment Chart
- Alert Trend Over Time
- Investigation Queue Table
- Global Risk Health Indicator

---

##  Machine Learning Layer

- Feature normalization
- Customer risk profiling
- Model training via scikit-learn
- Serialized model inference (model.pkl)

---

```
##  Tech Stack

- Python (FastAPI)
- Elasticsearch
- Kibana
- PostgreSQL
- SQLAlchemy
- scikit-learn
- Docker
- PowerShell (bulk alert simulation)


---
## 🏗 Triage++ Project Structure

```
Triage-Plus-Plus/
│
├── app/                         # 🔹 Application Source Code
│   │
│   ├── main.py                  # FastAPI entry point
│   ├── config.py                # Central configuration loader
│   │
│   ├── api/                     # 🌐 API Layer (Presentation)
│   │   ├── routes.py            # HTTP endpoints
│   │   ├── schemas.py           # Request/Response models
│   │   └── dependencies.py      # Dependency injection
│   │
│   ├── core/                    # 🧠 Decision Engine (Business Logic)
│   │   ├── engine.py            # Triage decision pipeline
│   │   ├── normalizer.py        # Alert normalization
│   │   ├── scoring.py           # Risk aggregation logic
│   │   ├── explainer.py         # Decision explainability
│   │   └── customer_profiles.py # Risk profiling logic
│   │
│   ├── analyzers/               # 🔎 Pluggable Scoring Modules
│   │   ├── base_analyzer.py
│   │   ├── repetition.py
│   │   ├── behavior.py
│   │   └── threat_intel.py
│   │
│   ├── integrations/            # 🔗 External Systems Integration
│   │   ├── elastic_writer.py
│   │   ├── elastic_reader.py
│   │   ├── webhook_handler.py
│   │   └── virustotal_client.py
│   │
│   ├── data/                    # 🗄 Persistence Layer
│   │   ├── models.py
│   │   ├── postgres.py
│   │   └── repositories.py
│   │
│   ├── metrics/                 # 📊 Observability
│   │   ├── collector.py
│   │   ├── prometheus.py
│   │   └── logging_config.py
│   │
│   ├── ml/                      # 🤖 Machine Learning Layer
│   │   ├── model_loader.py
│   │   ├── feature_engineering.py
│   │   └── training_pipeline.py
│   │
│   └── utils/                   # 🛠 Shared Utilities
│       ├── helpers.py
│       ├── validators.py
│       └── constants.py
│
├── docker/                      # 🐳 Containerization
│   ├── docker-compose.yml
│   └── nginx.conf
│
├── scripts/                     # ⚙ Operational Scripts
│   ├── seed_data.py
│   ├── generate_alerts.py
│   └── load_test.py
│
├── tests/                       # 🧪 Test Suite
│   ├── test_engine.py
│   ├── test_api.py
│   └── test_integrations.py
│
├── docs/                        # 📚 Documentation
│   ├── architecture.md
│   ├── scoring_logic.md
│   ├── elastic_integration.md
│   ├── api_reference.md
│   └── diagrams/
│       ├── triagepp-architecture.png
│       ├── elastic-flow.png
│       └── decision-pipeline.png
│
├── model.pkl                    # Trained ML model
├── triagepp.db                  # SQLite (dev only)
├── alembic/                     # Database migrations
├── alembic.ini
│
├── .env                         # Environment variables
├── requirements.txt             # Dependencies
├── Dockerfile
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🎯 Architecture Philosophy

- **Layered Architecture**
- **Pluggable Analyzer Design**
- **Elastic-first Observability**
- **ML-assisted Decision Engine**
- **Production-ready Docker Setup**

```

---
.....
Processing Flow

Elastic Rule
      ↓
Webhook Action
      ↓
Triage++ Intake Layer
      ↓
Normalization
      ↓
Behavior + Repetition + Threat Intel
      ↓
Risk Aggregation Engine
      ↓
Decision (ESCALATE / QUEUE / SUPPRESS)
      ↓
Indexed into triagepp-results
      ↓
Kibana Dashboard Visualization
......
```

---

```

---
##  Setup

### 1️ Clone the repository

```bash
git clone git@github.com:Ibrahem86/Triage-Plus-Plus.git
cd Triage-Plus-Plus

2️⃣ Create virtual environment
python -m venv venv
venv\Scripts\activate

3️⃣ Install dependencies
pip install -r requirements.txt

Run the application
uvicorn app.main:app --reload

🧪 Alert Simulation

PowerShell bulk script available to generate:

False positive waves

Escalation spikes

Queue overload scenarios

🧩 Future Enhancements

Adaptive thresholding

Behavior-based anomaly scoring

SOAR integration

Multi-tenant support

Cloud-native deployment
```

---

