CKD Risk Engine — Execution Playbook
Project: Companion Health
Version: v1.0
Owner: Companion Health

⸻

1. OBJECTIVE

Build a working CKD (Chronic Kidney Disease) risk prediction system for felines that:
	•	Accepts pet data
	•	Processes signals
	•	Outputs a risk score
	•	Can be exposed via API

⸻

2. SYSTEM SCOPE

IN SCOPE:
	•	Signal-based risk scoring
	•	Synthetic + real data ingestion
	•	API output

OUT OF SCOPE:
	•	Clinical-grade ML models
	•	Full diagnostic system
	•	Real-time monitoring

⸻

3. EXECUTION FLOW

Ulysses → Atlas → Forge

⸻

4. ULYSSES (TASK DEFINITION)

Objective:

Build CKD risk engine MVP usable for demo and pilot

⸻

Top Tasks:
	1.	Define signal model
	2.	Build risk scoring logic
	3.	Expose via API

⸻

Definition of DONE:
	•	API returns CKD risk score
	•	Output includes explanation
	•	Demo-ready

⸻

5. ATLAS (SYSTEM DESIGN)

5.1 Data Model

Inputs:
	•	Age
	•	Weight trend
	•	Hydration level
	•	Activity level

⸻

5.2 Signal Mapping

Weight decline → Risk increase
High hydration → Risk increase
Low activity → Risk increase

⸻

5.3 Architecture

Input Data → Signal Engine → Risk Model → API

⸻

5.4 Output Schema

risk_score
risk_band
explanation
confidence

⸻

6. FORGE (BUILD)

6.1 Backend Setup
	•	Python
	•	FastAPI

⸻

6.2 Endpoint

POST /fetch/ckd-risk

⸻

6.3 Logic (Simplified)
	•	Normalize inputs
	•	Apply weighted scoring
	•	Generate output

⸻

6.4 Example Output

risk_score: 72
risk_band: High
explanation: Weight decline, Hydration increase
confidence: 0.78

⸻

6.5 Simulation

If real data unavailable:
	•	Generate synthetic pet dataset
	•	Simulate realistic distributions

⸻

7. VALIDATION

System must:
	•	Return consistent output
	•	Be explainable
	•	Work with incomplete inputs

⸻

8. DEMO READINESS

Demo must show:
	•	Input → Output flow
	•	Risk explanation
	•	API response

⸻

9. EXTENSION PATH
	•	Add more signals
	•	Add ML model
	•	Add longitudinal tracking

FAILURE SCENARIOS
	•	Missing data
	•	Incorrect signals
	•	API latency

⸻

SYSTEM RESPONSE
	•	Fallback defaults
	•	Graceful degradation
	•	Logging

