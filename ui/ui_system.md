UI System — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v1.0
Status: Production-Aligned

⸻

1. PURPOSE

This document defines the visual and interaction system for Companion Health.

The UI is not a consumer interface.

It is:

A clinical intelligence interface designed for decision-making

Primary users:
	•	Insurance analysts
	•	Veterinary professionals
	•	Partner platforms

⸻

2. DESIGN PRINCIPLES

2.1 Clinical First
	•	UI must feel like medical software
	•	No decorative elements
	•	No unnecessary color usage

⸻

2.2 Signal Clarity
	•	Every element must communicate meaning
	•	Avoid visual noise
	•	Prioritize interpretability

⸻

2.3 Minimal Cognitive Load
	•	Maximum 3–5 elements per section
	•	No dense dashboards
	•	Clear hierarchy

⸻

2.4 Explainability
	•	Every output must be explainable
	•	UI must surface reasoning, not just numbers

⸻

3. VISUAL SYSTEM

3.1 Color System

Primary: #0f3e18
Secondary: #b2dbb8
Accent: #b6cdd5

Neutral Base:
	•	Background: #F7F9F8
	•	Surface: #FFFFFF
	•	Border: #E6E5DF

⸻

3.2 Signal Colors (CRITICAL)

Low Risk: Green
Medium Risk: Yellow
High Risk: Red

Rules:
	•	Use only for signals and risk
	•	Never use for decoration

⸻

3.3 Typography

Primary:
	•	Suisse Int’l / Inter Tight

Secondary:
	•	Faire Octave (headers only)

Rules:
	•	No more than 2 font families
	•	Consistent hierarchy

⸻

3.4 Layout System
	•	12-column grid
	•	8px spacing system
	•	Consistent margins

⸻

3.5 Components

Signal Card

Contains:
	•	Signal name
	•	Value
	•	Trend
	•	Status color

⸻

Risk Panel

Contains:
	•	Risk score (large)
	•	Risk band
	•	Confidence

⸻

Graph Component
	•	Line graphs only
	•	Thin stroke
	•	No heavy fills

⸻

Explanation Panel
	•	Bullet points
	•	Plain language
	•	No technical jargon

⸻

4. INTERACTION DESIGN

4.1 Motion
	•	150–300ms transitions
	•	Subtle only
	•	No dramatic animations

⸻

4.2 Feedback
	•	Immediate response to user input
	•	Highlight changes clearly

⸻

4.3 Navigation
	•	Flat structure
	•	No deep nesting

⸻

5. UI CONSTRAINTS
	•	No dark mode (initial)
	•	No complex filters
	•	No feature overload

⸻

6. DESIGN ANTI-PATTERNS

Avoid:
	•	Dashboard clutter
	•	Excessive charts
	•	Bright colors
	•	Gamification elements

⸻

7. SYSTEM ROLE

The UI must:
	•	Translate intelligence into clarity
	•	Support decisions
	•	Build trust
