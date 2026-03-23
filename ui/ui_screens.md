UI Screens — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0
Status: Production-Aligned

⸻

1. PURPOSE

Defines all core UI screens required for:
	•	Demo
	•	MVP
	•	Partner presentations

⸻

2. SCREEN 1 — PET OVERVIEW DASHBOARD

Purpose

Provide a summary of pet health status and risk

⸻

Layout

Top Section:
	•	Pet profile (name, age, breed)
	•	Risk score (primary focus)
	•	Confidence indicator

⸻

Middle Section:
	•	Signal Cards:
	•	Hydration Drift
	•	Weight Velocity
	•	Activity Change

⸻

Bottom Section:
	•	Graphs:
	•	Weight trend
	•	Hydration trend

⸻

Side Panel:
	•	Explanation of risk

⸻

Output
	•	Immediate understanding of health status
	•	Clear risk visibility

⸻

3. SCREEN 2 — SIGNAL DETAIL VIEW

Purpose

Deep dive into individual signal

⸻

Layout

Top:
	•	Signal name
	•	Current value
	•	Baseline

⸻

Middle:
	•	Time-series graph

⸻

Bottom:
	•	Interpretation panel

⸻

Side:
	•	Related signals

⸻

Output
	•	Understanding of signal behaviour
	•	Contextual interpretation

⸻

4. SCREEN 3 — INSURANCE VIEW

Purpose

Enable underwriting decision-making

⸻

Layout

Top:
	•	Two pets comparison

⸻

Middle:
	•	Risk score comparison
	•	Signal stability

⸻

Bottom:
	•	Insurance output:
	•	Risk level
	•	Cost band
	•	Premium implication

⸻

Output
	•	Immediate risk differentiation
	•	Pricing decision support

⸻

5. SCREEN 4 — TIMELINE VIEW

Purpose

Show progression of risk over time

⸻

Layout

Horizontal timeline:
	•	Day 0 → Day 40

⸻

Markers:
	•	Signal drift
	•	Risk increase
	•	Diagnosis

⸻

Bottom:
	•	Insight panel

⸻

Output
	•	Clear understanding of early detection window

⸻

6. SCREEN 5 — API / TECH VIEW

Purpose

Expose system output for technical stakeholders

⸻

Layout

Left:
	•	JSON response

Right:
	•	Human-readable explanation

⸻

Output
	•	Transparency
	•	Trust

⸻

7. SCREEN RELATIONSHIP

Overview → Signal → Risk → Insurance → Timeline

⸻

🧱 FILE 3 — /ui/ui_prompts.md (OPTIONAL BUT CLEAN)

Paste this:

⸻

UI Prompts — Companion Health
Purpose: Generate UI using Lovable / Claude

⸻

Dashboard Prompt

[Use structured prompt from system]

⸻

Signal View Prompt

[Use structured prompt]

⸻

Insurance View Prompt

[Use structured prompt]

⸻

Timeline Prompt

[Use structured prompt]
