Demo API Flows — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0

1. PURPOSE

Defines API interactions used in demo scenarios

2. FLOW 1 — CKD RISK DETECTION

Endpoint

POST /api/v1/fetch/ckd-risk

Input

pet_id: PET_B_001
age: 5
weight: 4.1
hydration: 180
activity: 55

Expected Output

risk_score: High
confidence: Moderate
explanation: [“Hydration increase”, “Weight decline”]

3. FLOW 2 — COMPARISON (PET A vs PET B)

Endpoint

POST /api/v1/fetch/ckd-risk

Inputs

Pet A → Stable
Pet B → Drift

Expected Output

Pet A:
	•	Low risk

Pet B:
	•	High risk

4. FLOW 3 — INSURANCE OUTPUT

Endpoint

POST /api/v1/fetch/ckd-insurance-risk

Input

PET_B_001

Expected Output

risk_score: High
insurance_risk_level: High
estimated_cost_band: High

5. VALIDATION RULES
   
	•	Outputs must be deterministic
	•	Same input → same output
	•	No null fields
	•	Explanation must always be present
