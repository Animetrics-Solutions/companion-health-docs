UI Build System — Companion Health
Version: v1.0
Status: CRITICAL

---

# 1. PURPOSE

Define how the Companion Health interface is built.

This is NOT a demo UI.
This is NOT a marketing interface.

This is a system surface.

---

# 2. CORE PRINCIPLE

The system is already running.

The user enters mid-state.

---

# 3. EXPERIENCE MODEL

The interface must feel like:

- live
- deterministic
- already in use

NOT:

- guided
- step-based
- explanatory

---

# 4. INTERFACE STRUCTURE

Single persistent canvas.

No multi-screen navigation.

---

## 4.1 TOP BAR

Left:
Companion Health

Right:
- Access Platform
- System Status: Live

---

## 4.2 MAIN CANVAS

Center:

- Pet identity
- Risk score (primary anchor)
- Status

Risk must be:
- dominant
- visible immediately
- pulsed once on load

---

## 4.3 BACKGROUND LAYER

Signals:

- hydration
- activity
- sleep

Behavior:

- subtle drift
- low opacity
- continuous

---

## 4.4 PERSPECTIVE SWITCH

[ Pet Parent ] [ Insurance ] [ Veterinary ]

Rules:

- No reload
- No transition break
- Same data, different interpretation

---

# 5. SYSTEM REVEAL

Hidden panel.

Triggered by:

- View System
- Icon

---

## Tabs

- API
- Architecture
- Integration

---

## Purpose

Expose depth ONLY when needed.

---

# 6. INTERACTION MODEL

User:

- explores

System:

- drives change

---

# 7. MOTION RULES

Follow motion_system.md

---

# 8. DESIGN RULES

Follow design_system.md + grid_system.md

---

# 9. WHAT TO AVOID

- Step indicators
- Next buttons
- Demo narration UI
- Screen-based flows

---

# 10. SUCCESS CRITERIA

- Feels like a real system
- No demo perception
- Immediate credibility

---

# FINAL RULE

Do not design screens.

Design system behavior.
