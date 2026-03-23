# Companion Health — Brand Architecture Blueprint
**Classification:** INTERNAL — CONFIDENTIAL  
**Version:** v1.0  
**Owner:** Companion Health / Animetric  
**Last Updated:** [Add Date]

---

# 1. CONTEXT

## 1.1 Problem Space

Pet healthcare today is:
- Reactive (diagnosis after symptoms)
- Fragmented (data across apps, vets, devices)
- Non-standardized (no unified intelligence layer)

Chronic diseases such as CKD (Chronic Kidney Disease) in cats:
- Are detected late
- Lack continuous monitoring
- Result in high treatment cost and low survival extension

---

## 1.2 Strategic Opportunity

Companion Health exists to:

> Shift pet healthcare from **episodic treatment → continuous intelligence**

This is achieved by:

- Aggregating multi-source pet data
- Converting raw data into behavioral and health signals
- Providing predictive risk scoring via API

---

# 2. BRAND ARCHITECTURE

## 2.1 Structural Model

```mermaid
graph TD
A[Animetric] --> B[Companion Health]
B --> C[Fetch API]
C --> D[Applications / Partners]
