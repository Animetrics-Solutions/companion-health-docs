Demo Validation & Fallback — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0
Status: CRITICAL

⸻

1. PURPOSE

Defines:
	•	Pre-demo validation checklist
	•	Failure scenarios
	•	Fallback execution paths

Goal:

Ensure demo success regardless of technical issues

⸻

2. PRE-DEMO VALIDATION CHECKLIST

Run this 30–60 minutes before demo

⸻

2.1 DATA VALIDATION
	•	PET_TRW_001 loads correctly
	•	PET_TRW_002 loads correctly
	•	PET_TRW_TIMELINE loads correctly

⸻

2.2 API VALIDATION

Test:

POST /fetch/ckd-risk
	•	Returns response < 1s
	•	No null fields
	•	Explanation present

⸻

2.3 UI VALIDATION
	•	Dashboard loads
	•	Signal cards update
	•	Risk panel displays correctly
	•	Timeline renders

⸻

2.4 FLOW VALIDATION

Run entire flow once:
	•	Step 1 → Step 6 works without interruption
	•	Transitions are smooth
	•	No confusion in UI

⸻

2.5 ENVIRONMENT CHECK
	•	Stable internet
	•	Backup hotspot available
	•	Device fully charged

⸻

3. FAILURE SCENARIOS

⸻

3.1 API FAILURE

Symptom
	•	No response
	•	Delayed response

⸻

Cause
	•	Backend issue
	•	Network issue

⸻

Fallback

Switch to:
	•	Pre-generated JSON output
	•	Static UI state

⸻

3.2 UI FAILURE

Symptom
	•	UI not loading
	•	Broken layout

⸻

Fallback
	•	Use screenshots
	•	Use recorded demo

⸻

3.3 DATA FAILURE

Symptom
	•	Incorrect signals
	•	Missing data

⸻

Fallback
	•	Switch dataset
	•	Use pre-loaded state

⸻

3.4 NETWORK FAILURE

Symptom
	•	Complete loss of connectivity

⸻

Fallback
	•	Offline demo version
	•	Screens + narrative

⸻

4. FALLBACK MODES

⸻

MODE 1 — LIVE (PRIMARY)
	•	Full system
	•	Real API
	•	Interactive UI

⸻

MODE 2 — SEMI-LIVE
	•	UI working
	•	API simulated

⸻

MODE 3 — STATIC
	•	Screenshots
	•	Pre-recorded outputs

⸻

MODE 4 — NARRATIVE (LAST RESORT)
	•	Walkthrough without UI
	•	Use diagrams

⸻

5. FALLBACK RULE

Never say:

❌ “It’s not working”

Always say:

“Let me show you the output directly”

⸻

6. EDGE CASE QUESTIONS (PREP)

⸻

Q1 — “What if signals are wrong?”

Answer:
	•	Signals are probabilistic
	•	Improve with more data
	•	Used for early detection, not diagnosis

⸻

Q2 — “How reliable is this?”

Answer:
	•	Early-stage system
	•	Already validated on behavioural data
	•	Improves with insurance data

⸻

Q3 — “What happens with incomplete data?”

Answer:
	•	System handles partial inputs
	•	Uses defaults
	•	Maintains output consistency

⸻

7. DEMO CONTROL RULES
	•	Never rush
	•	Never over-explain
	•	Never show extra screens

⸻

8. RECOVERY STRATEGY

If something breaks:
	1.	Pause
	2.	Switch mode
	3.	Continue flow

⸻

9. SUCCESS CRITERIA

Demo is successful if:
	•	Signals are clear
	•	Risk is understandable
	•	Insurance impact is obvious
