System Architecture — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v2.0
Status: Production-Aligned Draft

⸻

1. SYSTEM OVERVIEW

1.1 System Role in Business Model

Companion Health operates as:

A multi-tenant intelligence middleware that transforms raw pet telemetry into predictive health signals consumable by insurers, veterinary systems, and partner platforms.

This system sits between data generation and decision-making, enabling:
	•	Insurance underwriting optimization
	•	Early disease detection
	•	Veterinary decision support
	•	Future pharmaceutical research

It is not a frontend product.
It is a data intelligence infrastructure layer.

⸻

1.2 Core Objective

To bridge the Detection Gap:
	•	Identify sub-clinical health deviations
	•	Convert behavioural data into predictive signals
	•	Deliver explainable risk intelligence via API

⸻

1.3 High-Level Architecture

The system operates as a decoupled, event-driven pipeline:

Data Sources
→ Ingestion Layer (Async Queue / Pub-Sub)
→ Adapter & Normalization Layer
→ Signal Engine (Baseline + Drift Detection)
→ Risk Models
→ Fetch API
→ External Consumers

⸻

1.4 Architectural Principles

API-First (Headless System)
	•	No UI dependency
	•	All functionality exposed via REST
	•	Enables B2B integrations

⸻

Multi-Tenancy (Silo Pattern)
	•	Each partner operates in isolation
	•	Data separation at:
	•	Database level
	•	Compute level

⸻

Temporal Integrity
	•	All data is treated as time-series
	•	Timestamps are primary index
	•	No aggregation without temporal context

⸻

Stateless Compute
	•	FastAPI services remain stateless
	•	State stored in:
	•	Redis (cache)
	•	PostgreSQL / TimescaleDB (persistence)

⸻

Explainable Intelligence (XAI)
	•	No black-box outputs
	•	Every risk score must include:
	•	Signal attribution
	•	Reasoning trace

⸻

2. SYSTEM COMPONENTS

2.1 Data Sources (Ingress Layer)

The system ingests four categories:

IoT Telemetry
	•	Accelerometry
	•	Hydration
	•	Weight
	•	Temperature

Connected Environment
	•	Smart bowls
	•	Smart litter
	•	Activity trackers

Clinical Systems
	•	Lab results (SDMA, Creatinine)
	•	Diagnosis history
	•	Medication logs

Owner Input
	•	Behavioural logs
	•	Appetite changes
	•	Observational inputs

⸻

2.2 Ingestion Layer (Entry Node)

Responsibilities
	•	Authentication (API keys / JWT)
	•	Rate limiting (multi-tenant fairness)
	•	Schema validation

⸻

Engineering Decision

Use asynchronous ingestion (Pub/Sub) to:
	•	Decouple ingestion from processing
	•	Handle burst traffic from IoT devices
	•	Prevent system bottlenecks

⸻

Failure Handling
	•	Invalid payload → Dead Letter Queue
	•	Retry logic for transient failures

⸻

2.3 Adapter & Normalization Layer

Purpose

Convert heterogeneous external data into a unified internal schema

⸻

Transformations
	1.	Unit Standardization
	•	Weight → kg
	•	Volume → ml
	2.	Temporal Alignment
	•	Resampling to fixed intervals
	3.	Missing Data Handling
	•	Forward fill
	•	Mean imputation

⸻

Engineering Constraint

No data proceeds to Signal Engine without normalization

⸻

2.4 Signal Engine (Core Intelligence Layer)

Purpose

Convert raw telemetry into behavioural health signals

⸻

Key Functions

Baseline Modeling
	•	Establish pet-specific baseline (rolling 30-day window)

Drift Detection
	•	Identify deviations using statistical methods (e.g., EWMA)

⸻

Example

Baseline hydration: 120ml
Current hydration: 200ml

Signal:

Hydration Drift = +66%

⸻

Business Impact

This is the first layer of intelligence
Without this, models are blind

⸻

2.5 Risk Model Layer

Purpose

Convert signals into disease-aware risk scores

⸻

Architecture

Modular design:
	•	CKD Model (active)
	•	Future models:
	•	Cardiac
	•	Obesity
	•	Diabetes

⸻

Implementation

Weighted scoring system:

Risk Score = Σ (Signal × Weight)

⸻

Constraint

Models must remain:
	•	Interpretable
	•	Explainable
	•	Modular

⸻

2.6 Fetch API (Interface Layer)

Role
	•	External interface
	•	Product layer
	•	Revenue layer

⸻

Responsibilities
	•	Receive structured requests
	•	Call model layer
	•	Return standardized JSON

⸻

Constraint
	•	Stateless
	•	Deterministic
	•	Fast (<300ms target)

⸻

2.7 Output Layer

Consumers:
	•	Insurance systems
	•	Vet platforms
	•	Partner apps

⸻

Output Requirements

Must include:
	•	Risk score
	•	Explanation
	•	Confidence

⸻

3. DATA STORAGE STRATEGY

3.1 Storage Types

Telemetry → Time-series DB (TimescaleDB / Bigtable)
Metadata → PostgreSQL
Session/Auth → Redis

⸻

3.2 Multi-Tenant Enforcement

Every query must include:

tenant_id

Example:

SELECT * FROM telemetry
WHERE pet_id = X AND tenant_id = Y

⸻

3.3 Engineering Constraint

No cross-tenant access allowed

⸻

4. PRODUCTION CONSIDERATIONS

4.1 Scalability
	•	Horizontal scaling for API layer
	•	Queue-based ingestion
	•	Distributed storage

⸻

4.2 Reliability
	•	Dead Letter Queues
	•	Retry mechanisms
	•	Graceful degradation

⸻

4.3 Observability
	•	End-to-end tracing (OpenTelemetry)
	•	Input → Output tracking
	•	Latency monitoring

⸻

4.4 Security
	•	No PII in signal engine
	•	Use anonymized pet_uuid
	•	Encrypted data transport

⸻

5. ENGINEERING CHECKLIST
	•	Idempotent ingestion
	•	Deterministic outputs
	•	Schema validation
	•	Full observability
