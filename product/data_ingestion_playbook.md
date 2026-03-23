Data Ingestion Engine — Execution Playbook
Project: Companion Health
Version: v1.0
Owner: Companion Health

⸻

1. OBJECTIVE

Build a system that can:
	•	Ingest pet data from multiple sources
	•	Normalize it into a unified format
	•	Feed it into the signal engine

⸻

2. WHY THIS MATTERS

This layer:
	•	Creates defensibility
	•	Enables better models
	•	Differentiates you from competitors

⸻

3. DATA SOURCES

Initial sources:
	•	Pet apps (HappyPet, Vetic, Wiggles)
	•	IoT devices (Catit, Moggie)
	•	Vet records
	•	Synthetic datasets

⸻

4. EXECUTION FLOW

External Data → Ingestion Layer → Normalization → Signal Engine

⸻

5. ULYSSES (TASK DEFINITION)

Objective:

Build ingestion pipeline for synthetic + app-based data

⸻

Top Tasks:
	1.	Define data schema
	2.	Build ingestion handlers
	3.	Normalize data

⸻

Definition of DONE:
	•	Data can be ingested
	•	Data is structured
	•	Data feeds signal engine

⸻

6. ATLAS (SYSTEM DESIGN)

6.1 Data Schema (Unified)

pet_id
timestamp
age
weight
hydration
activity
source

⸻

6.2 Data Types

Structured
Semi-structured
Unstructured (future)

⸻

6.3 Normalization Rules
	•	Convert units to standard
	•	Handle missing fields
	•	Align timestamps

⸻

6.4 Source Adapters

Each data source must have:

Adapter layer

Example:

HappyPet Adapter
Moggie Adapter

⸻

6.5 Data Flow

Source → Adapter → Normalizer → Signal Engine

⸻

6.6 Storage Strategy (Initial)
	•	Lightweight storage (JSON / DB)
	•	Not heavy infra

⸻

7. FORGE (BUILD)

7.1 Ingestion Handlers

Create:
	•	API ingestion endpoint
	•	File ingestion (CSV / JSON)

⸻

7.2 Adapter Logic

Map source data → internal schema

⸻

7.3 Normalization Logic
	•	Fill missing values
	•	Standardize units
	•	Clean data

⸻

7.4 Example Flow

Raw Data → Adapter → Cleaned Data → Signal Input

⸻

7.5 Synthetic Data Engine

Generate:
	•	Pet profiles
	•	Time-series data
	•	Variations for testing

⸻

8. VALIDATION

Data must be:
	•	Consistent
	•	Structured
	•	Usable by model

⸻

9. DEMO SCENARIO

Show:

Data ingestion → Processing → Risk output

⸻

10. SCALING PATH

Future:
	•	Real-time ingestion
	•	Streaming data
	•	Larger datasets

⸻

11. DEFENSIBILITY

This layer creates:
	•	Proprietary datasets
	•	Better models over time
	•	Competitive advantage
