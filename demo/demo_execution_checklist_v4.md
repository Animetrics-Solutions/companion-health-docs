# Demo UI Correction — Companion Health V4
Status: IMMEDIATE REWORK REQUIRED

---

# 1. TOPBAR — IDENTITY BREAK

## Problem
- Brandmark + reconstructed text = cheap
- Hierarchy unclear
- Looks like a template header

## Fix
- Use ONLY full Companion logo SVG (wordmark + mark)
- Remove custom text stacking (“companion / Health”)
- Reduce visual weight of right side

## Layout
[LOGO] --------------------------- [● System Live] [System]

---

# 2. BACKGROUND — DEAD CANVAS

## Problem
- Flat dark background - Change to the similar color usage as in the homepage, more white spaces and typography should be as per brand guide. 
- Signal field looks decorative, not structural

## Fix
- Reduce number of floating signals by 40–60%
- Lower opacity further (0.04–0.08)
- Anchor 2–3 signals closer to center (relevance hint)

## Add
- very subtle radial gradient behind risk (5–8% opacity)

---

# 3. RISK NUMBER — NOT DOMINANT ENOUGH

## Problem
- Big, but not authoritative
- Feels like typography, not output

## Fix
- Increase size by ~10–15%
- Increase vertical whitespace around it
- Reduce brightness of surrounding elements

## Add
- 1-time pulse ONLY (already exists → good)
- slight “settling” effect (scale 1.02 → 1.0)

---

# 4. RISK COLOR SYSTEM — WRONG

## Problem
- Everything white → no semantic meaning

## Fix
- Risk color must reflect state:

Elevated → muted amber (not bright)
Stable → neutral
High → controlled red (later)

## Current state label:
“MONITORED · ELEVATED” → good, but:

- tighten tracking
- reduce opacity slightly

---

# 5. SIGNAL ROW — CLUTTERED + WEAK

## Problem
- Feels like random labels
- No hierarchy

## Fix
- Increase spacing between signal groups
- Reduce separators (·)
- Align baselines perfectly

## Add hierarchy:
Hydration ↓ (primary)
Weight ↓ (secondary)
Activity (neutral)

---

# 6. PERSPECTIVE TABS — AMATEUR FEEL

## Problem
- Looks like toggle buttons
- Heavy borders
- Green fill is loud and cheap

## Fix

### Style:
- Remove boxy container
- Tabs should be text-first

Example:

Pet Parent   Insurance   Veterinary

Active state:
- subtle underline OR
- soft glow, not filled button

---

# 7. CONTENT BLOCKS — TOO “APP-LIKE”

## Problem
- Feels like dashboard cards
- Not system output

---

## PET PARENT

Fix:
- Remove quotation marks
- Reduce emotional tone
- Make it observational

---

## INSURANCE

Fix:
- Align numbers on a strict grid
- Increase spacing between metrics
- Remove visual boxing

---

## VET

Fix:
- tighten paragraph width
- increase line spacing slightly
- reduce visual noise around timeline

---

# 8. SYSTEM PANEL — GOOD IDEA, BAD EXECUTION

## Problem
- Feels like a slide-in feature
- Not a system layer

## Fix

### Motion
- Add 120–180ms delay before open
- Slight background dim BEFORE panel slides

### Layout
- Increase padding inside panel
- Align code blocks to grid

### Tabs
- Reduce spacing
- remove heavy borders

---

# 9. GRID SYSTEM — NON-EXISTENT

## Problem
Everything feels “placed”

---

## Fix

### Enforce:

- Center column width (max 560px) → already exists but not felt
- Align:
  - pet ID
  - risk
  - signals
  - tabs
  - content

### Spacing system:
Use ONLY:
24 / 40 / 64

No random margins

---

# 10. TYPOGRAPHY — INCONSISTENT TONE

## Problem
- Mix of expressive + system tone

---

## Fix

- Faire Octave → ONLY brand / hero (minimal)
- Everything else → Suisse Intl

---

## Critical:
Risk number = Suisse Intl Medium ONLY

---

# 11. COLOR DISCIPLINE — BROKEN

## Problem
Green is everywhere

---

## Fix

Green ONLY for:
- active tab
- system indicators
- positive state

Everything else:
→ neutral / white / amber

---

# 12. MOTION SYSTEM — TOO MANY INDEPENDENT LOOPS

## Problem
- feels artificial

---

## Fix

Reduce:
- ticker frequency (way too chatty)

Tie motion to:
- actual state changes

---

# 13. REMOVE “DESIGNED” FEEL

## Remove:
- unnecessary borders
- decorative lines
- extra UI chrome

---

## Keep:
- data
- spacing
- hierarchy

---

# FINAL TARGET

UI should feel:

- inevitable
- quiet
- precise

NOT:

- designed
- decorated
- assembled

---

# SUCCESS CHECK

If someone sees this for 5 seconds:

They should think:
“This is a system already running”

NOT:
“This is a demo interface”
