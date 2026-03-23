Insurance Intelligence Layer — Execution Playbook
Project: Companion Health
Version: v1.0
Owner: Companion Health

⸻

1. OBJECTIVE

Build an intelligence layer that enables insurance companies to:
	•	Assess pet health risk
	•	Price policies more accurately
	•	Detect early-stage chronic conditions

⸻

2. WHY THIS MATTERS

Insurance is:
	•	The fastest monetisation path
	•	Data-hungry
	•	Risk-driven

Your system becomes:

An actuarial intelligence engine for pet health

⸻

3. CORE USE CASES
	1.	Underwriting
	2.	Risk-based pricing
	3.	Early risk detection
	4.	Claims optimisation

⸻

4. EXECUTION FLOW

Pet Data → Fetch API → Risk Models → Insurance Output

⸻

5. ULYSSES (TASK DEFINITION)

Objective:

Build insurance-ready risk output using CKD model

⸻

Top Tasks:
	1.	Map CKD output to insurance use
	2.	Create insurance-friendly output
	3.	Simulate policy scenarios

⸻

Definition of DONE:
	•	Output usable by insurer
	•	Clear risk categorisation
	•	Demo-ready

⸻

6. ATLAS (SYSTEM DESIGN)

6.1 Insurance Output Layer

Extend Fetch output to include:
	•	Risk category
	•	Expected cost band
	•	Risk explanation

⸻

6.2 Output Structure

risk_score
risk_band
insurance_risk_level
estimated_cost_band
explanation

⸻

6.3 Risk Mapping

Low risk → Standard premium
Medium risk → Adjusted premium
High risk → High premium / flagged

⸻

6.4 Cost Band Logic (Simulated)

Low → ₹ / AED low range
Medium → mid range
High → high range

⸻

6.5 Data Flow

Fetch API → Insurance Layer → Output

⸻

7. FORGE (BUILD)

7.1 Extend API

Add:

/fetch/ckd-insurance-risk

⸻

7.2 Logic
	•	Use CKD score
	•	Map to insurance categories
	•	Generate cost band

⸻

7.3 Example Output

risk_score: 72
risk_band: High
insurance_risk_level: High
estimated_cost_band: High
explanation: [“Weight decline”, “Hydration increase”]

⸻

7.4 Simulation

Since real insurance data not available:
	•	Create synthetic cost mapping
	•	Keep logic explainable

⸻

8. DEMO SCENARIO

Show:

Pet data → Risk output → Insurance interpretation

⸻

Demo Narrative

“This pet has a high CKD risk, which translates to a higher expected treatment cost, impacting premium pricing.”

⸻

9. VALIDATION

Output must:
	•	Be understandable by non-technical audience
	•	Map clearly to pricing logic
	•	Be explainable

⸻

10. STRATEGIC POSITIONING

You are NOT:
	•	An insurance platform

You are:

The intelligence layer that improves insurance decisions

⸻

11. EXTENSION

Future:
	•	Multi-condition risk
	•	Claims prediction
	•	Policy optimization
