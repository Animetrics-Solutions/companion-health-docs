Decision Log — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0
Status: ACTIVE

⸻

1. PURPOSE

This document tracks key architectural, product, and system decisions.

Each entry captures:
	•	Decision made
	•	Context
	•	Alternatives considered
	•	Rationale
	•	Impact

⸻

2. DECISION FRAMEWORK

All decisions are evaluated using:
	•	Impact on core system
	•	Speed to usable output
	•	Dependency unlock
	•	Effort

⸻

3. DECISIONS

⸻

3.1 Signal-Based Model vs ML-First Approach

Decision

Adopt signal-based risk modeling as initial system foundation

⸻

Context
	•	Limited real-world dataset
	•	Need for explainability
	•	Requirement for fast demo readiness

⸻

Alternatives Considered
	1.	Full ML model (supervised learning)
	2.	Hybrid ML + rules system

⸻

Rationale
	•	Signal-based approach is:
	•	Faster to implement
	•	Interpretable
	•	Requires less data
	•	Enables early-stage system validation

⸻

Impact
	•	Faster MVP development
	•	Stronger demo clarity
	•	Easier partner communication

⸻

⸻

3.2 API-First Architecture

Decision

Design system as API-first (headless architecture)

⸻

Context
	•	Multiple integration points (insurance, apps, vets)
	•	Need for flexible consumption

⸻

Alternatives Considered
	1.	UI-first product
	2.	Monolithic system

⸻

Rationale
	•	API-first enables:
	•	Faster integration
	•	Multi-tenant scalability
	•	Product modularity

⸻

Impact
	•	Cleaner system boundaries
	•	Faster partner onboarding

⸻

⸻

3.3 Stateless Service Design

Decision

Keep all services stateless

⸻

Context
	•	Need for scalability
	•	Simplified infrastructure

⸻

Alternatives Considered
	1.	Stateful services
	2.	Session-based architecture

⸻

Rationale
	•	Stateless systems:
	•	Scale horizontally
	•	Simplify deployment
	•	Reduce coupling

⸻

Impact
	•	Easier scaling
	•	Lower operational complexity

⸻

⸻

3.4 Pub/Sub Ingestion Model

Decision

Use asynchronous ingestion via message queues

⸻

Context
	•	IoT and app data may arrive in bursts
	•	Need to decouple ingestion from processing

⸻

Alternatives Considered
	1.	Synchronous ingestion
	2.	Direct processing pipeline

⸻

Rationale
	•	Pub/Sub enables:
	•	Scalability
	•	Fault tolerance
	•	Decoupling

⸻

Impact
	•	More resilient system
	•	Better handling of real-world data flows

⸻

⸻

3.5 Synthetic Data for Initial Development

Decision

Use synthetic datasets for early-stage development and demo

⸻

Context
	•	Limited access to real-world data
	•	Need for rapid prototyping

⸻

Alternatives Considered
	1.	Wait for real data
	2.	Build partial system

⸻

Rationale
	•	Synthetic data allows:
	•	Full system simulation
	•	Faster iteration
	•	Controlled testing

⸻

Impact
	•	Accelerated development
	•	Demo readiness

⸻

⸻

3.6 CKD as Initial Use Case

Decision

Focus on CKD (Chronic Kidney Disease) as first model

⸻

Context
	•	High prevalence in cats
	•	Detectable via behavioural signals

⸻

Alternatives Considered
	1.	Multi-disease model
	2.	Obesity / diabetes first

⸻

Rationale
	•	CKD provides:
	•	Strong signal patterns
	•	Clear demo narrative
	•	Insurance relevance

⸻

Impact
	•	Focused development
	•	Strong initial use case

⸻

⸻

3.7 Multi-Tenant Architecture (Silo Model)

Decision

Adopt strict multi-tenant isolation

⸻

Context
	•	Multiple partners (insurance, apps, vets)
	•	Data privacy requirements

⸻

Alternatives Considered
	1.	Shared data model
	2.	Soft multi-tenancy

⸻

Rationale
	•	Silo model ensures:
	•	Data security
	•	Compliance readiness
	•	Partner trust

⸻

Impact
	•	Increased system complexity
	•	Stronger enterprise positioning

⸻

⸻

3.8 Explainable Output Requirement

Decision

All model outputs must include explanation

⸻

Context
	•	Insurance and medical domains require trust
	•	Black-box models are harder to adopt

⸻

Alternatives Considered
	1.	Pure scoring model
	2.	ML-only output

⸻

Rationale
	•	Explainability:
	•	Improves trust
	•	Enables adoption
	•	Supports compliance

⸻

Impact
	•	Slight increase in complexity
	•	Stronger business acceptance

⸻

⸻

3.9 Demo-First Development Strategy

Decision

Prioritize demo-ready outputs over full system completeness

⸻

Context
	•	Need to validate with partners early
	•	Limited resources

⸻

Alternatives Considered
	1.	Build full system first
	2.	Infrastructure-first approach

⸻

Rationale
	•	Demo-first:
	•	Accelerates feedback
	•	Supports partnerships
	•	Reduces risk

⸻

Impact
	•	Faster validation
	•	Incremental system building

⸻

⸻

4. FUTURE DECISIONS (TO BE TRACKED)
	•	Transition to ML models
	•	Multi-disease expansion
	•	Real-time ingestion architecture
	•	Advanced data partnerships

⸻

5. USAGE RULE
	•	All major decisions must be logged
	•	No undocumented architectural changes
	•	Updates must include rationale
