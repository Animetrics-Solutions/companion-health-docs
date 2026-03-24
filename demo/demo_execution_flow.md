Demo Execution Flow — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0
Status: LOCKED

⸻

1. PURPOSE

Defines the exact execution sequence of the demo.

This ensures:
	•	Consistency
	•	Reproducibility
	•	Controlled output

⸻

2. DEMO STRUCTURE

The demo is executed in 3 layers:
	1.	TRW System Validation (Proof)
	2.	Risk Engine Output (Core Intelligence)
	3.	Insurance Application (Monetisation Layer)

⸻

3. GLOBAL RULES
	•	No deviation from flow
	•	No additional screens
	•	No dynamic exploration
	•	Predefined datasets only

⸻

4. STEP-BY-STEP EXECUTION

⸻

STEP 1 — LOAD TRW DATA (SYSTEM PROOF)

Input

Dataset: PET_TRW_001

⸻

Expected Behaviour
	•	Data is ingested
	•	Signals are generated

⸻

UI State

Show:
	•	Pet profile
	•	Baseline metrics
	•	Trend graphs

⸻

Expected Output
	•	Stable system
	•	No risk spike yet

⸻

⸻

STEP 2 — SIGNAL EMERGENCE

Input

Dataset: PET_TRW_002 (drift scenario)

⸻

Expected Behaviour

System detects:
	•	Hydration increase
	•	Weight decline

⸻

UI State

Highlight:
	•	Signal cards
	•	Drift indicators

⸻

Expected Output
	•	Hydration Drift → Elevated
	•	Weight Velocity → Negative

⸻

⸻

STEP 3 — RISK GENERATION

Action

Call:

POST /fetch/ckd-risk

⸻

Input

pet_id: PET_TRW_002
age: 5
weight: 4.1
hydration: 180
activity: 55

⸻

Expected Output
	•	Risk Score: Medium / High
	•	Confidence: Moderate
	•	Explanation present

⸻

UI State

Show:
	•	Risk panel
	•	Explanation

⸻

⸻

STEP 4 — INSURANCE APPLICATION

Input

Compare:

PET_TRW_001 vs PET_TRW_002

⸻

Expected Behaviour

System differentiates:
	•	Stable vs unstable signals

⸻

UI State

Show:
	•	Side-by-side comparison

⸻

Expected Output

PET_TRW_001:
	•	Low risk
	•	Standard premium

PET_TRW_002:
	•	High risk
	•	Adjusted premium

⸻

⸻

STEP 5 — TIMELINE VALIDATION

Input

Dataset: PET_TRW_TIMELINE

⸻

Expected Behaviour

System shows:
	•	Signal drift progression
	•	Risk escalation

⸻

UI State

Show:
	•	Timeline view

⸻

Expected Output
	•	Early signal detection
	•	Risk before diagnosis

⸻

⸻

5. DATASETS (LOCKED)

The following datasets must be used:
	•	PET_TRW_001 → Stable
	•	PET_TRW_002 → Drift
	•	PET_TRW_TIMELINE → Progressive

⸻

6. OUTPUT VALIDATION

Each step must satisfy:
	•	Output is deterministic
	•	No missing fields
	•	Explanation always present

⸻

7. FAILURE CONDITIONS

Demo is considered failed if:
	•	Risk score not generated
	•	Signals not visible
	•	UI unclear
	•	Output inconsistent

⸻

8. SUCCESS CONDITION

Demo is successful when:
	•	Signals are visible
	•	Risk is understandable
	•	Insurance impact is clear

⸻

9. EXECUTION TIME

Target:
	•	Full demo: 5–7 minutes
	•	No pauses
	•	No debugging during demo
