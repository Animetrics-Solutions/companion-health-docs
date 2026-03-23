Document: Brand Architecture Blueprint
Project: Companion Health
Parent: Animetric
Classification: INTERNAL — CONFIDENTIAL
Version: v2.1
Owner: Companion Health
Status: ACTIVE
Last Updated: [DATE]

⸻

	1.	CONTEXT

1.1 Problem Space

Pet healthcare today suffers from three fundamental structural failures:

A. Temporal Fragmentation
Health data is episodic, not continuous. Diagnosis occurs after symptoms appear. There is no longitudinal baseline tracking.

B. Data Fragmentation
Pet applications, veterinary systems, and IoT devices operate independently. There is no unified dataset combining behavioural and clinical signals. Data formats are inconsistent.

C. Intelligence Gap
There is no signal processing layer. No predictive risk modelling exists. No actuarial intelligence is available for insurers or research.

⸻

1.2 Strategic Opportunity

Companion Health establishes a continuous intelligence layer for pet health.

This transforms the system from reactive care to predictive intelligence, from static data storage to signal processing, and from isolated clinical events to continuous monitoring.

⸻

1.3 System Thesis

Health is not an event.
Health is a continuous signal system.

⸻

	2.	BRAND ARCHITECTURE

2.1 Structural Model

Animetric → Companion Health → Fetch API → Partners / Applications

⸻

2.2 Layer Definitions

Animetric (Parent Layer)
The intelligence infrastructure layer. It is abstracted from end users and designed for long-term scalability across multiple domains including livestock, pharma, and research.

Companion Health (Platform Layer)
The external-facing platform responsible for trust, healthcare positioning, and ecosystem integration. It translates intelligence into usable outputs.

Fetch API (Product Layer)
The delivery layer of the system. It exposes signal intelligence via structured APIs and enables integration with external systems.

2.3 Naming Logic

Animetric represents analytical scale and abstraction.
Companion Health represents trust, care, and healthcare alignment.
Fetch represents action, retrieval, and immediacy.

⸻

2.4 Usage Rules

External communication uses Companion Health.
Product references use Fetch.
Internal and investor narratives use Animetric.

⸻

2.5 Brand Hierarchy Rationale

This layered structure enables separation of trust and technology, ensures clear product abstraction, and allows future expansion without requiring rebranding.

Without this structure:
	•	Brand becomes constrained
	•	Product positioning becomes unclear
	•	Expansion becomes difficult

⸻

	3.	BRAND PHILOSOPHY

3.1 Core Principle

Health is a continuous signal, not a discrete event.

⸻

3.2 Experience Model

Data → Signal → Insight → Decision → Outcome

⸻

3.3 Design Philosophy
	•	Clinical, not playful
	•	Intelligent, not decorative
	•	Minimal, not empty
	•	Calm, not sterile

⸻

	4.	VISUAL SYSTEM

4.1 Color System

Primary: #0f3e18
Secondary: #b2dbb8
Accent: #b6cdd5
Neutral: #E6E5DF

⸻

4.2 Typography

Primary: Suisse Int’l
Secondary: Faire Octave
Fallback: Inter Tight

⸻

4.3 Layout System
	•	12-column responsive grid
	•	8pt spacing system
	•	Technical blueprint-style overlays

⸻

	5.	UI / UX SYSTEM

5.1 Component Architecture

Dashboard → Signal Cards / API Panel / Trend Graphs

⸻

5.2 Core Components

Signal Card
Displays risk score, contributing signals, and confidence level

API Panel
Displays structured JSON output for developers and integrations

Trend Graph
Displays longitudinal patterns and highlights anomalies

⸻

5.3 Interaction Principles
	•	Motion duration: 150–300ms
	•	Smooth transitions only
	•	No aggressive animation
	•	Focus on readability and clarity

	6.	PRODUCT ARCHITECTURE

6.1 System Overview

Data Sources → Ingestion Layer → Signal Engine → Risk Model → Fetch API → External Systems

⸻

6.2 Data Sources
	•	Pet applications
	•	IoT devices (wearables, feeders, trackers)
	•	Veterinary records
	•	Insurance datasets

⸻

6.3 Processing Layers

Ingestion Layer
Normalizes incoming data from multiple sources

Signal Engine
Transforms raw data into behavioural and health signals

Risk Model
Calculates disease risk based on signal combinations

API Layer
Delivers structured output to external systems

⸻

	7.	SIGNAL INTELLIGENCE FRAMEWORK

7.1 Core Signals
	•	Hydration patterns
	•	Weight drift
	•	Activity levels
	•	Behavioural anomalies

⸻

7.2 CKD Risk Model

Inputs: Age, Weight trend, Hydration, Activity
Output: Risk score + explanation + confidence

⸻

7.3 Output Structure

risk_score: numerical value (0–100)
risk_band: Low / Medium / High
explanation: list of contributing factors
confidence: probability score (0–1)

⸻

	8.	API CONTRACT

8.1 Endpoint

POST /fetch/ckd-risk

⸻

8.2 Request Schema

pet_id: string
age: number
weight: number
hydration: number
activity: number

⸻

8.3 Response Schema

risk_score: number
risk_band: string
explanation: array
confidence: number

⸻

8.4 Rules
	•	Explanation is mandatory
	•	No null fields allowed
	•	Confidence must be between 0 and 1
	•	Response must be deterministic for same input

⸻

	9.	DESIGN ↔ TECH MAPPING

9.1 Component Mapping

Signal Card → /fetch/ckd-risk
Trend Graph → /fetch/history
API Panel → Raw API output

⸻

9.2 Data Flow

Data → Signal Engine → API → UI → User Insight

⸻

9.3 Rendering Rules
	•	Risk score must be visible immediately
	•	Explanations must be human-readable
	•	Confidence must be both visual and numeric

⸻

	10.	DESIGN IMPACT ASSESSMENT

All UI changes must:
	•	Preserve clarity of signals
	•	Maintain layout grid integrity
	•	Avoid visual noise

⸻

	11.	TECHNICAL IMPACT ASSESSMENT

Changes impact:
	•	API contracts
	•	Data models
	•	Service dependencies

Risks:
	•	Backward compatibility issues
	•	Performance degradation

⸻

	12.	CHANGE MANAGEMENT

12.1 Rules
	•	All changes must be versioned
	•	No breaking changes without version increment
	•	Rollback strategy must be defined

⸻

12.2 Version History

v1.0 → Initial
v1.1 → Structured
v2.0 → Compiled
v2.1 → Full system

⸻

	13.	SCOPE CONTROL

13.1 Out of Scope
	•	Multi-disease modelling
	•	Full veterinary EMR systems
	•	Real-time streaming pipelines
	•	Advanced ML pipelines

⸻

13.2 Rule

If it does not improve CKD prediction or pilot validation, it is not built

⸻

	14.	EXECUTION NOTES

14.1 Build Order
	1.	Fetch API
	2.	CKD Model
	3.	UI Layer
	4.	Data ingestion

⸻

14.2 Expansion Path
	•	Multi-disease support
	•	Multi-species intelligence
	•	Insurance integration
	•	Research data platform

⸻

FINAL NOTE

This document defines the foundational system of Companion Health.

All product, design, and technical decisions must align with this structure
