# UI Screen Blueprint — Companion Health
Version: v2.0
Status: EXECUTION SPEC

---

# 1. CORE MODEL

Single persistent canvas.

No multi-screen navigation.

No step-based flow.

---

# 2. LAYOUT STRUCTURE

## 2.1 Top Bar

Left:
Companion Health (logo)

Right:
- System Status: Live
- Access Platform

Height:
64px

---

## 2.2 Main Canvas

Centered layout.

Max width: 1280px

---

# 3. PRIMARY FOCUS — RISK STATE

## Placement

Center of screen

---

## Elements

- Pet Name (small)
- Risk Score (dominant)
- Status (below)

---

## Example

Bruno · Age 11

72

Monitored · Elevated

---

## Typography

- Risk: Suisse Intl Medium
- Large scale (48–64px)

---

## Motion

- Pulse once on load (600ms)

---

# 4. SIGNAL FIELD (BACKGROUND LAYER)

## Elements

- Hydration
- Activity
- Sleep

---

## Behavior

- Low opacity
- Subtle drift animation
- Continuous

---

## Placement

Behind main content

---

# 5. SIGNAL DETAILS (FOREGROUND)

## Placement

Below risk

---

## Format

Hydration ↑  
Activity ↓  
Sleep irregular  

---

## Style

- Minimal
- No cards
- Inline or stacked text

---

# 6. PERSPECTIVE SWITCH

## Placement

Top or bottom center

---

## Options

[ Pet Parent ] [ Insurance ] [ Veterinary ]

---

## Behavior

- No reload
- Same data, different UI layers

---

# 7. PERSPECTIVE LAYERS

---

## 7.1 Pet Parent

- Simplified language
- Action suggestions

Example:
“Bruno seems slightly off this week”

---

## 7.2 Insurance

Adds:

- Confidence score
- Risk trajectory
- Portfolio context

---

## 7.3 Veterinary

Adds:

- Clinical interpretation
- Intervention window
- Timeline

---

# 8. SYSTEM REVEAL PANEL

## Trigger

“View System”

---

## Layout

Right-side panel or modal

---

## Tabs

- API
- Architecture
- Integration

---

# 9. MOTION MAPPING

Use ONLY:

- animate-pulse-once → risk
- animate-drift → signals
- animate-emerge → new data
- animate-tick → updates

---

## Forbidden

- Page transitions
- Slide animations
- Bounce effects

---

# 10. COLOR APPLICATION

- Risk → green / risk color
- Signals → muted
- UI → neutral

---

# 11. COMPONENT RULES

Do NOT use:

- Cards
- Heavy containers
- Shadows (unless minimal)

---

Use:

- spacing
- alignment
- hierarchy

---

# 12. ENTRY STATE

On load:

- Risk visible immediately
- Signals already present
- System already active

---

## Remove

- intro text
- onboarding
- explanation

---

# 13. SUCCESS CRITERIA

User must feel:

“This system is already running”

NOT:

“This is a demo”

---

# FINAL RULE

System reveals itself.

User does not navigate it.
