Demo Scenarios — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0

⸻

1. PURPOSE

This document defines structured demo scenarios used to:
	•	Demonstrate system capabilities
	•	Validate API outputs
	•	Drive UI development
	•	Support partner demos (insurance, vet platforms)

⸻

2. SCENARIO 1 — EARLY CKD DETECTION

Objective

Demonstrate transformation from behavioural data → signals → risk score

⸻

Input Conditions
	•	Pet with stable historical baseline
	•	Gradual increase in hydration
	•	Gradual decrease in weight

⸻

System Processing

Telemetry → Signal Engine → CKD Model

⸻

Expected Signals
	•	Hydration Drift: Positive
	•	Weight Velocity: Negative

⸻

Expected Output
	•	CKD Risk Score: Medium to High
	•	Confidence Score: Moderate
	•	Explanation: Hydration increase + weight decline

⸻

UI Requirements
	•	Trend graphs (weight, hydration)
	•	Signal indicators (drift visualization)
	•	Risk panel (score + explanation)

⸻

Business Outcome
	•	Early detection before clinical diagnosis
	•	Enables proactive intervention

⸻

3. SCENARIO 2 — INSURANCE RISK DIFFERENTIATION

Objective

Demonstrate risk-based differentiation between similar pets

⸻

Input Conditions

Two pets:

Pet A:
	•	Stable signals

Pet B:
	•	Hydration increase
	•	Weight decline

⸻

System Processing

Each pet processed independently

⸻

Expected Output

Pet A:
	•	Risk Score: Low
	•	Stable signals

Pet B:
	•	Risk Score: High
	•	Signal instability

⸻

UI Requirements
	•	Side-by-side comparison view
	•	Risk scoring panel
	•	Signal comparison indicators

⸻

Business Outcome
	•	Enables dynamic underwriting
	•	Differentiates risk beyond demographics

⸻

4. SCENARIO 3 — CLAIM PREVENTION WINDOW

Objective

Demonstrate early signal detection before diagnosis

⸻

Input Conditions

Time-series data:

Day 0 → Stable
Day 10 → Signal drift begins
Day 20 → Risk increases
Day 40 → Clinical diagnosis

⸻

System Processing

Continuous ingestion → signal tracking → risk escalation

⸻

Expected Output
	•	Risk increase detected at Day 10–20
	•	Diagnosis occurs later

⸻

UI Requirements
	•	Timeline visualization
	•	Signal progression graph
	•	Risk escalation curve

⸻

Business Outcome
	•	Early intervention window
	•	Reduced claims cost
	•	Improved loss ratio
