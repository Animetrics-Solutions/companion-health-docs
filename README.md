# Companion Health — Documentation System

Companion Health — Intelligence Layer for Pet Health

Companion Health is a multi-tenant, API-first intelligence platform that transforms pet behavioural and telemetry data into predictive health signals.

Core System
	•	Signal Engine (behaviour → signal transformation)
	•	Risk Models (CKD → multi-condition roadmap)
	•	Fetch API (intelligence delivery layer)
	•	Insurance Intelligence (underwriting + claims optimization)

System Components
	•	Data Ingestion Engine
	•	Signal Processing Layer
	•	Risk Modeling Layer
	•	API Layer (Fetch)

Use Cases
	•	Early disease detection (CKD)
	•	Dynamic insurance underwriting
	•	Claim prevention


---

## Structure

- `/brand` → Brand architecture and design system  
- `/product` → Product modules (Fetch API, CKD model)  
- `/architecture` → System architecture and data flows  
- `/ai-system` → Claude skill system (Ulysses, Atlas, Forge)  
- `/diagrams` → Mermaid diagram source files  
- `/exports` → Generated documents for sharing  

---

## Principles

- Markdown is the source of truth  
- Mermaid is used for all diagrams  
- Documents are build-ready (not summaries)  
- No duplication — update existing files only  

---

## Documentation Standard

Every document must include:

1. Context  
2. System Overview  
3. Architecture (with diagrams)  
4. Components  
5. Technical Specification  
6. Design Impact  
7. Technical Impact  
8. Change Management  
9. Execution Notes  

---

## Diagram Standard (Mermaid)

All diagrams must be written in Mermaid.

Example:

```mermaid
graph TD
A[Pet Data] --> B[Signal Processing]
B --> C[CKD Engine]
C --> D[Fetch API]
D --> E[Insurance Layer]
