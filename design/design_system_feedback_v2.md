# Design System V2 — Audit Feedback
Version: v2.1 Feedback Layer
Status: ACTION REQUIRED

---

# 1. OVERALL ASSESSMENT

The current design system (CSS v2.0) successfully enforces:

- Typography discipline
- Color token structure
- Grid and spacing system
- Motion primitives
- Component standardisation

This represents a strong foundation.

However:

The system currently governs visual consistency, not experiential behavior.

Result:
UI can still appear as a “designed demo” instead of a “running system”.

---

# 2. CORE GAP

## Problem

The system defines:
- how elements look

But does not fully define:
- how the system behaves
- how states evolve
- how users experience transitions

---

## Required Shift

From:
Visual Design System

To:
System Behavior Framework

---

# 3. TYPOGRAPHY ENFORCEMENT (REFINEMENT)

## Issue

Serif usage still risks bleeding into system UI.

---

## Enforcement Update

- Faire Octave → ONLY:
  - Hero headline
  - Section anchor (max 1 per section)

- Suisse Intl → ALL system UI

- Suisse Intl Mono → ALL:
  - API
  - Labels
  - Metadata

---

## New Rule

Numeric values (risk, metrics) MUST use Suisse Intl Medium.

Never serif.

---

# 4. COMPONENT SYSTEM CORRECTION

## Issue

Residual “card UI” patterns still exist.

---

## Required Enforcement

Remove:
- Box containers
- Elevated cards
- Decorative sections

Replace with:
- Spatial grouping
- Grid alignment
- Minimal separators

---

## Rule

If a container is not functionally required → remove it.

---

# 5. COLOR SYSTEM CORRECTION

## Issue

Primary green used decoratively.

---

## Enforcement

Green may ONLY represent:
- Risk
- Active state
- Primary action

Everything else:
- Neutral palette

---

## Rule

Color must communicate meaning, never decoration.

---

# 6. MOTION SYSTEM (CRITICAL EXTENSION)

## Issue

Motion primitives exist but are not tied to system causality.

---

## Required Addition

Define:

### 6.1 System State Motion

- Data drift → continuous
- Signal emergence → event-driven
- Risk recalculation → discrete

---

### 6.2 Motion Logic Rule

Motion must answer:

“What changed?”

If no answer → no motion.

---

## Forbidden

- Page transitions
- Slide animations
- Decorative looping

---

# 7. DEMO EXPERIENCE CORRECTION

## Issue

UI still reflects step-based demo sequencing.

---

## Required Update

Replace:

Step flow → State evolution

---

## Remove

- Step indicators
- “Next” dependency
- Guided narration UI

---

## Replace With

- Passive updates
- Perspective switching
- System-driven transitions

---

# 8. SYSTEM CANVAS MODEL (NEW REQUIREMENT)

## Add Requirement

All demo UI must be built on:

Single persistent canvas

---

## Behavior

- No full screen changes
- No page resets
- No navigation jumps

---

## Rule

System evolves in place.

---

# 9. ENTRY STATE REQUIREMENT

## Issue

No strong system entry moment

---

## Required Behavior

On load:

- Risk score visible immediately
- One-time pulse (600ms)
- Signals present (low opacity)
- Status visible

---

## Remove

- Intro text
- Explanation layers

---

## Outcome

User perceives:

“The system is already running”

---

# 10. PERSPECTIVE SYSTEM (MANDATORY)

## Add

[ Pet Parent ] [ Insurance ] [ Veterinary ]

---

## Rules

- No reload on switch
- Same data, different interpretation

---

## Outcome

Demonstrates system depth without changing UI

---

# 11. SYSTEM REVEAL LAYER

## Add

Optional panel:

- API
- Architecture
- Integration

---

## Rule

System depth must be:
- accessible
- not primary

---

# 12. LOGO SYSTEM ENFORCEMENT

## Clarification

- Companion = system identity
- Fetch = product layer

---

## Rules

- Fetch only inside API / dev context
- Never above Companion
- No decorative usage of logos

---

# 13. GRID ENFORCEMENT

## Issue

Minor alignment inconsistencies

---

## Required

- All elements snap to grid
- Spacing strictly 8px multiples
- No visual drift

---

# 14. FINAL SYSTEM PRINCIPLE

The interface must feel:

- live
- deterministic
- already in use

NOT:

- designed
- guided
- narrated

---

# FINAL RULE

Do not design screens.

Design system behavior.
