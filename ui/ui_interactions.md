# Companion Health — UI Interactions Specification (System-Driven)
Version: v2.0
Status: IMPLEMENTATION READY
Replaces: v1.0 entirely

---

# 0. PURPOSE

This document defines how the system surface behaves over time.

This is NOT an animation guide.

This is a specification of:
- system-triggered state changes
- data-driven visual updates
- deterministic interaction rules

---

# 1. CORE PRINCIPLE

All interaction is driven by system state changes.

User interaction does NOT drive the system.

User interaction only:
- reveals
- focuses
- reinterprets

---

# 2. INTERACTION TYPES

There are only 3 interaction classes:

1. System-driven (primary)
2. Focus-driven (secondary)
3. Lens-driven (interpretation)

No other interaction types are allowed.

---

# 3. SYSTEM-DRIVEN INTERACTIONS

These are triggered by SDS or Risk Engine outputs.

---

## 3.1 Risk Update

Trigger:
- change in signal composition OR magnitude

Behavior:
- risk value transitions smoothly (no jumps)
- interpolation duration: 300–600ms

Constraints:
- no overshoot
- no oscillation
- no flicker

---

## 3.2 Risk Threshold Crossing

Trigger:
- risk crosses defined boundary

Boundaries:
- 30, 60, 80

Behavior:
- single pulse (scale 1.0 → 1.05 → 1.0)
- duration: 400ms
- no repetition

---

## 3.3 Signal Emergence

Trigger:
- new signal enters top contributing set

Behavior:
- signal appears with subtle opacity fade (200ms)
- no movement from off-screen
- no slide-in

---

## 3.4 Signal Exit

Trigger:
- signal drops below threshold

Behavior:
- fade out (200ms)
- no collapse animation
- no layout shift

---

## 3.5 Signal Reordering

Trigger:
- change in contribution ranking

Behavior:
- instant reorder OR minimal positional shift (<150ms)
- no animated sorting

---

## 3.6 Context Update

Trigger:
- change in signals OR perspective

Behavior:
- immediate replacement
- no typing effect
- no fade sequencing

---

---

# 4. FOCUS-DRIVEN INTERACTIONS

These allow inspection of system components.

---

## 4.1 Signal Focus

Trigger:
- click / tap on signal

Behavior:
- opens Signal Detail Overlay

Overlay characteristics:
- layered on top of system surface
- base surface remains visible
- no navigation

---

## 4.2 Overlay Close

Trigger:
- click outside OR close action

Behavior:
- overlay disappears instantly OR fades (150–200ms)
- no reverse animation complexity

---

---

# 5. LENS-DRIVEN INTERACTIONS

Perspective switching.

---

## 5.1 Perspective Switch

Trigger:
- user selects:
  - Pet Parent
  - Insurance
  - Veterinary

---

## 5.2 Behavior

Changes:
- context layer
- interpretation
- secondary metrics

Does NOT change:
- risk
- signals
- layout

---

## 5.3 Transition Rules

- no page transition
- no fade between “screens”
- instantaneous state reinterpretation

---

---

# 6. OVERLAY INTERACTIONS

---

## 6.1 System Overlay

Trigger:
- system control activation

Behavior:
- overlay appears on top of surface
- shows:
  - pipeline
  - API output
  - system metrics

Rules:
- no navigation
- no context loss

---

## 6.2 Timeline Overlay

Trigger:
- timeline activation

Behavior:
- reveals temporal structure
- maintains system context

---

## 6.3 Insurance Overlay

Trigger:
- insurance context selection

Behavior:
- shows comparative state
- maintains dominant subject focus

---

---

# 7. MOTION SYSTEM (STRICT)

---

## Allowed Motion Types

1. Pulse (risk)
2. Fade (signals)
3. Subtle drift (ambient)
4. Numeric interpolation (risk updates)

---

## Forbidden Motion Types

- slide-in / slide-out
- bounce
- hover animation
- looping decorative motion
- page transitions

---

---

# 8. TIMING SPECIFICATION

| Interaction | Duration |
|------------|---------|
| Risk interpolation | 300–600ms |
| Risk pulse | 400ms |
| Signal fade in/out | 200ms |
| Overlay open/close | 150–250ms |

---

---

# 9. INTERACTION PRIORITY

If multiple events occur:

Priority order:

1. Risk change
2. Signal change
3. Context update
4. Lens update

Lower priority updates must NOT interrupt higher ones.

---

---

# 10. NOISE SUPPRESSION RULE

System must avoid:

- rapid flickering signals
- jittery risk updates
- frequent UI changes

---

## Implementation

- apply smoothing (EMA)
- debounce signal changes (min 1–2 cycles)

---

---

# 11. FAILURE CONDITIONS

System fails if:

- UI reacts without data change
- animations draw attention
- transitions feel like navigation
- interaction feels “app-like”

---

---

# 12. SUCCESS CONDITION

User perception:

“The system is updating itself. I am only observing it.”

---

---

# FINAL PRINCIPLE

Interaction does not drive the system.

The system drives interaction.
