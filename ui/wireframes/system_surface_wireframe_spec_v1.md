# Companion Health — System Surface Wireframe Specification
Version: v1.0
Status: IMPLEMENTATION READY
Audience: UI Engineering, Frontend, Product, Design Systems

---

# 0. PURPOSE

This document defines the exact structure, behavior, layout logic, and rendering rules for the Companion Health system surface.

This is NOT a page.
This is NOT a dashboard.
This is NOT a UI composition.

This is a real-time system state surface.

---

# 1. CORE PRINCIPLE

The interface represents:

A continuously running system exposing its current state

NOT:

A user navigating an interface

---

# 2. CANVAS DEFINITION

## 2.1 Canvas Type

- Single persistent surface
- No pagination
- No scroll dependency for core state

---

## 2.2 Dimensions

- Responsive layout
- Desktop baseline: 1440 × 900
- Primary working field: centered, max-width 560px

---

## 2.3 Grid System

- 12-column grid
- Columns 5–8 = primary system field
- Outer columns reserved for future passive layers

---

## 2.4 Spacing System (STRICT)

Only allowed spacing values:

- 24px
- 40px
- 64px

No deviation permitted.

---

# 3. LAYOUT MODEL (NON-LINEAR)

Elements do NOT stack like a webpage.

They coexist within a single spatial field.

---

# 4. ELEMENT SPECIFICATION

---

## 4.1 SYSTEM STATUS INDICATOR

Position:
- Top-right (fixed)

Content:
- "● SYSTEM LIVE"

Behavior:
- Subtle pulse every 6–8 seconds
- No interaction
- Always visible

---

## 4.2 PET META

Position:
- Centered above risk
- 40px above risk

Format:
BRUNO · AGE 11 · DOMESTIC SHORTHAIR

Typography:
- Suisse Intl Regular
- 12–14px
- Increased letter spacing

Behavior:
- Static
- No animation

---

## 4.3 RISK (PRIMARY ELEMENT)

Position:
- Absolute center of canvas

Content:
72

Typography:
- Suisse Intl Medium
- 120–160px

Behavior:
- Passive updates (no jumps)
- One-time pulse ONLY when:
  - threshold crossed
  - new signal materially impacts risk

Constraints:
- Must remain dominant
- No competing visual elements

---

## 4.4 STATUS

Position:
- 24px below risk

Format:
MONITORED · ELEVATED

Behavior:
- Derived from score + trajectory + confidence
- Updates silently

Visual:
- Low contrast
- Secondary to risk

---

## 4.5 SIGNALS

Position:
- 40px below status

Structure:
Hydration ↓
Weight ↓
Activity stable

Rules:

1. Max 3 signals (ideal: 2)
2. Only include signals where:
   - contribution to risk > threshold
   - deviation is meaningful
3. Sort by contribution DESC
4. Signals must feel causally linked to risk
5. No decorative styling

Motion:
- Subtle drift (1–2px)
- No looping animation

---

## 4.6 PERSPECTIVE LENS

Position:
- 64px below signals

Options:
Pet Parent   Insurance   Veterinary

Behavior:
- Inline toggle
- No navigation
- No layout shift

On switch:
- Risk unchanged
- Signals unchanged
- Context changes
- Interpretation changes

Visual:
- Active: subtle emphasis
- Inactive: muted

---

## 4.7 CONTEXT LAYER

Position:
- 40px below perspective

Structure (STRICT):

Hydration ↓ 14d
Weight ↓ 9%
Activity stable

Pattern: localized decline

Rules:

- Max 4 lines
- No full sentences
- No narrative language
- No recommendation

Forbidden:
- paragraphs
- explanations
- storytelling

---

## 4.8 SYSTEM PANEL (OPTIONAL)

Trigger:
- "System" control (top-right)

Content:
- API
- Architecture
- Integration

Behavior:
- Overlay only
- No navigation

---

# 5. MOTION SYSTEM

Allowed:

- Risk pulse (single event)
- Signal drift (subtle)
- Silent data updates

Forbidden:

- Page transitions
- Sliding UI
- Looping animations
- Attention-grabbing motion

---

# 6. COLOR SYSTEM

Rules:

- 85–90% neutral palette

Usage:

- Green → system active
- Amber → elevated risk

Forbidden:

- decorative color usage
- gradients for aesthetics

---

# 7. TYPOGRAPHY

- Risk → Suisse Intl Medium
- System text → Suisse Intl Regular
- Labels (optional) → Suisse Intl Mono
- No serif in system UI

---

# 8. DISALLOWED ELEMENTS

Must NOT exist:

- Cards
- Panels
- Boxes
- Shadows
- Hero layouts
- Onboarding UI
- Explanatory paragraphs
- Recommendations
- CTA buttons (e.g., "View System")

---

# 9. RENDERING LOGIC

## Load State

- System already active
- Risk immediately visible
- Signals already present

---

## Update Behavior

- Risk updates gradually
- Signals update silently
- No visual re-render or flashing

---

# 10. FAILURE CONDITIONS

If UI resembles:

- dashboard
- SaaS interface
- landing page

→ FAIL

---

# 11. SUCCESS CONDITION

User perception:

"This system exists independently of me"

---

# FINAL PRINCIPLE

This is not a UI.

This is a system made visible.
