UI Interactions & Motion — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0

⸻

1. PURPOSE

Defines how the interface behaves.

The goal is not animation.

The goal is:

Reinforcing trust, clarity, and signal interpretation

⸻

2. MOTION PRINCIPLES
	•	Subtle
	•	Functional
	•	Predictable

⸻

2.1 Timing
	•	Fast interactions: 150ms
	•	Transitions: 200–300ms
	•	No delays

⸻

2.2 Motion Rules
	•	No bounce effects
	•	No elastic animations
	•	No playful motion

⸻

3. COMPONENT INTERACTIONS

3.1 Signal Cards

On load:
	•	Fade in sequentially (left → right)

On change:
	•	Value updates with slight highlight
	•	Color transition (green → yellow → red)

⸻

3.2 Risk Score Panel

On load:
	•	Number fades in (no counting animation)

On update:
	•	Smooth transition
	•	Confidence updates with subtle opacity change

⸻

3.3 Graphs

On load:
	•	Line draws in (very subtle)

On hover:
	•	Show data point
	•	No heavy tooltips

⸻

3.4 Timeline View
	•	Marker appears progressively
	•	Risk escalation shown via color transition

⸻

4. FEEDBACK SYSTEM
	•	Immediate visual response
	•	No lag
	•	No loading spinners unless necessary

⸻

5. ERROR STATES
	•	Minimal
	•	Clear message
	•	No technical jargon

⸻

6. INTERACTION ANTI-PATTERNS

Avoid:
	•	Flashy transitions
	•	Heavy hover effects
	•	Over-animation

