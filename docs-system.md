# Documentation System — Companion Health

## Purpose

Define a repeatable, low-effort, high-quality documentation system.

---

## Format Standard

Every document must include:

1. Context
2. System Overview
3. Architecture (Mermaid diagrams)
4. Components
5. Technical Specification
6. Design Impact
7. Technical Impact
8. Change Management
9. Execution Notes

---

## Diagram Standard

All diagrams must be written in Mermaid.

### Example:

```mermaid
graph TD
A[Pet Data] --> B[Signal Processing]
B --> C[CKD Engine]
C --> D[Fetch API]
