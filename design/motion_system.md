Motion System — Companion Health
Version: v1.1
Status: CRITICAL

---

# 1. PRINCIPLE

Motion must represent causality.

If nothing changes → nothing moves.

---

# 2. MOTION TYPES

---

## 2.1 State Emergence

Used for:
- Signals appearing
- Data forming

Behavior:
- Fade: 0 → 100%
- Scale: 0.98 → 1
- Duration: 200–400ms

---

## 2.2 Focus Shift

Used for:
- Zoom into case
- Layer transitions

Behavior:
- Scale + opacity shift
- No slide transitions
- Duration: 250–350ms

---

## 2.3 Computation Pulse

Used for:
- Risk values (e.g., 72)

Behavior:
- Scale: 1 → 1.05 → 1
- Duration: 600ms
- Occurrence: once only

---

## 2.4 Background Drift

Used for:
- Signals
- Data fields

Behavior:
- Subtle movement
- Low opacity
- Continuous but minimal

---

## 2.5 Data Update Tick

Used for:
- Real-time feel

Behavior:
- Micro changes (±1 value)
- No animation exaggeration

---

# 3. TIMING SYSTEM

Fast: 150–200ms  
Default: 200–300ms  
Slow: 300–500ms  

---

# 4. EASING

Use:
- ease-out
- linear (for system changes)

Avoid:
- bounce
- elastic
- exaggerated curves

---

# 5. WHAT NOT TO DO

- No decorative animation
- No looping highlights
- No motion without meaning

---

# 6. MOTION HIERARCHY

Priority:
1. Risk value
2. Signal changes
3. Contextual UI

---

# 7. SUCCESS CRITERIA

- Motion feels inevitable
- No distraction
- Reinforces system intelligence
