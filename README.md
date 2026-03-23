# Companion Health — Documentation System

This repository is the source of truth for all system, product, brand, and AI architecture documentation for Companion Health.

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
