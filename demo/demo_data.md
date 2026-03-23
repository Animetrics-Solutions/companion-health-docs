Demo Data — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0

⸻

1. PURPOSE

Defines synthetic datasets used for:
	•	Demo scenarios
	•	API testing
	•	UI rendering

⸻

2. PET A — BASELINE STABLE

pet_id: PET_A_001
age: 5

weight:
	•	Day 1: 4.5
	•	Day 15: 4.5
	•	Day 30: 4.4

hydration:
	•	Day 1: 120
	•	Day 15: 125
	•	Day 30: 122

activity:
	•	Stable

⸻

3. PET B — CKD SIGNAL DRIFT

pet_id: PET_B_001
age: 5

weight:
	•	Day 1: 4.5
	•	Day 15: 4.3
	•	Day 30: 4.1

hydration:
	•	Day 1: 120
	•	Day 15: 150
	•	Day 30: 180

activity:
	•	Slight decline

⸻

4. TIMELINE DATA (SCENARIO 3)

pet_id: PET_T_001

Day 0: Stable
Day 10: Hydration ↑
Day 20: Weight ↓
Day 30: Risk increases
Day 40: Diagnosis

⸻

5. DATA RULES
	•	All values are synthetic
	•	Must remain realistic
	•	Must trigger expected signals
