Demo Execution Flow V2 — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v2.0
Status: LOCKED

⸻

1. PURPOSE

Defines the upgraded demo flow that:
	•	Proves the system works (TRW data)
	•	Demonstrates core intelligence
	•	Applies to insurance
	•	Signals platform scalability

⸻

2. DEMO STRUCTURE

The demo is executed in 4 layers:
	1.	System Proof (TRW Data)
	2.	Signal Intelligence
	3.	Insurance Application
	4.	Platform Expansion (Light)

⸻

3. GLOBAL RULES
	•	Strict linear flow
	•	No branching
	•	No feature exploration
	•	Each step must increase conviction

⸻

4. EXECUTION FLOW

⸻

STEP 1 — SYSTEM VALIDATION (TRW DATA)

Input

Dataset: PET_TRW_001

⸻

Purpose

Prove system works on real behavioural data

⸻

UI State

Show:
	•	Pet profile
	•	Stable trends
	•	Baseline signals

⸻

Expected Output
	•	No major risk
	•	System appears stable

⸻

Validation
	•	Data ingestion visible
	•	Graphs render correctly

⸻

⸻

STEP 2 — SIGNAL EMERGENCE

Input

Dataset: PET_TRW_002

⸻

Purpose

Show how signals emerge from behaviour

⸻

UI State

Highlight:
	•	Hydration increase
	•	Weight decline

⸻

Expected Output
	•	Drift detected
	•	Signal cards change state

⸻

Validation
	•	Signal cards reflect deviation
	•	Clear visual change

⸻

⸻

STEP 3 — RISK GENERATION

Action

POST /fetch/ckd-risk

⸻

Input

PET_TRW_002

⸻

Purpose

Convert signals → risk

⸻

UI State

Show:
	•	Risk score
	•	Confidence
	•	Explanation

⸻

Expected Output
	•	Medium / High risk
	•	Explanation present

⸻

Validation
	•	Deterministic output
	•	No missing fields

⸻

⸻

STEP 4 — INSURANCE APPLICATION

Input

PET_TRW_001 vs PET_TRW_002

⸻

Purpose

Show business impact

⸻

UI State

Show:
	•	Side-by-side comparison
	•	Risk difference

⸻

Expected Output

PET_TRW_001:
	•	Low risk

PET_TRW_002:
	•	High risk

⸻

Validation
	•	Clear differentiation
	•	Pricing implication visible

⸻

⸻

STEP 5 — TIMELINE (CAUSAL PROOF)

Input

PET_TRW_TIMELINE

⸻

Purpose

Show early detection window

⸻

UI State

Show:
	•	Timeline progression
	•	Signal → Risk

⸻

Expected Output
	•	Risk appears before diagnosis

⸻

Validation
	•	Timeline is clear
	•	Signal progression visible

⸻

⸻

STEP 6 — PLATFORM EXTENSION (LIGHT ONLY)

Purpose

Show system is not single-use

⸻

Show (DO NOT DEEP DIVE)
	•	Vet view (brief)
	•	App intelligence (brief)

⸻

Expected Outcome
	•	System feels extensible
	•	No additional explanation required

⸻

⸻

5. DATASETS (LOCKED)
	•	PET_TRW_001 → Stable
	•	PET_TRW_002 → Drift
	•	PET_TRW_TIMELINE → Progressive

⸻

6. TRANSITIONS (IMPORTANT)

Each step must:
	•	Build on previous step
	•	Not reset context

⸻

Flow must feel like:

System → Signal → Risk → Money → Platform

⸻

7. FAILURE CONDITIONS

Demo fails if:
	•	Signals unclear
	•	Risk unexplained
	•	Insurance link weak
	•	UI confusing

⸻

8. SUCCESS CONDITION

Demo succeeds when:
	•	System feels real
	•	Risk feels inevitable
	•	Insurance value is obvious
	•	Platform potential is clear

⸻

9. EXECUTION TIME

Target:
	•	Total: 6–8 minutes
	•	No interruptions
	•	No debugging
