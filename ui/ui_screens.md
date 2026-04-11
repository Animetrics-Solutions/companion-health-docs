# Companion Health — System Surface Wireframe Specification
Version: v2.2
Status: IMPLEMENTATION READY 

---

# 0. SYSTEM MODEL OVERVIEW

SYSTEM PIPELINE

[ Raw Data ]
      ↓
[ Signal Detection System (SDS) ]
      ↓
[ Signals ]
      ↓
[ Risk Engine ]
      ↓
[ Risk Score ]
      ↓
[ System Surface (UI) ]

---

# 1. CORE PRINCIPLE

This is NOT a page.

This is a SYSTEM SURFACE.

The UI represents:
A continuously running system exposing its current state.

---

# 2. CANVAS MODEL

Viewport (Desktop reference):

+------------------------------------------------------+
|                                                      |
|              SYSTEM SURFACE FIELD                     |
|        (center-aligned working region ~560px)         |
|                                                      |
+------------------------------------------------------+

No header / footer / page structure.

---

# 3. SPATIAL LAYOUT MODEL

Elements are NOT stacked like a webpage.

They exist relative to the system center (risk).

                [ SYSTEM STATUS ]

                    [ META ]

                     [72]

                  [ STATUS ]

                [ SIGNALS ]

            [ PERSPECTIVE LENS ]

               [ CONTEXT ]

---

# 4. ELEMENT BREAKDOWN

---

## 4.1 RISK CORE (PRIMARY NODE)

Represents:
- Risk Engine output

                ┌────────────┐
                │     72     │
                └────────────┘

Rules:
- Always central
- Largest element
- No competing visual weight

Behavior:
- Updates only on real data change
- Smooth transitions (no jumps)

---

## 4.2 STATUS LAYER

Derived from risk + trajectory

                    MONITORED · ELEVATED

Mapping:

0–30 → Stable  
31–60 → Monitored  
61–80 → Elevated  
81–100 → Critical  

---

## 4.3 SIGNALS (CAUSAL STRUCTURE)

Signals must feel like inputs to risk.

        Hydration ↓
        Weight ↓
        Activity stable

Causality model:

[ Hydration ↓ ]
        \
         → contributes to → [ RISK 72 ]
        /
[ Weight ↓ ]

Rules:
- Max 3 signals
- Sorted by contribution
- Must not appear as UI list

---

## 4.4 PERSPECTIVE LENS

Inline interpretation layer

Pet Parent   Insurance   Veterinary

Behavior:

          SAME SYSTEM STATE
                  │
    ┌─────────────┼─────────────┐
    │             │             │
Pet Parent   Insurance   Veterinary
(view)        (view)        (view)

Changes:
- context
- metrics

Does NOT change:
- risk
- signals

---

## 4.5 CONTEXT LAYER

Structured interpretation (NOT narrative)

Example:

Hydration ↓ 14d  
Weight ↓ 9%  
Activity stable  

Pattern: localized decline  

Rules:
- Max 4 lines
- No sentences
- No explanation tone

---

## 4.6 PET META

BRUNO · AGE 11 · DOMESTIC SHORTHAIR

Rules:
- Low emphasis
- Above risk
- Non-interactive

---

## 4.7 SYSTEM STATUS

● SYSTEM LIVE

Rules:
- Top-right
- Minimal motion
- No interaction

---

# 5. STATE OVERLAY MODEL

Overlays extend the system.
They DO NOT replace it.

---

## 5.1 SIGNAL DETAIL OVERLAY

Trigger:
- signal focus

Structure:

[ Signal: Hydration ↓ ]

Baseline: 450ml  
Current: 320ml  
Z-score: -2.17  
Duration: 4d  

Graph (conceptual):

Baseline -----
             \
              \____ Current

---

## 5.2 INSURANCE OVERLAY

Comparison model:

[ PET_TRW_001 ]      [ PET_TRW_002 ]
       34                     72

                  ↓

           Risk Difference

                  ↓

           Premium Impact

Rules:
- PET_TRW_002 dominant
- PET_TRW_001 background reference

---

## 5.3 TIMELINE OVERLAY

Time-based causality:

Day 0      Day 7      Day 14      Day 21
  |          |          |           |
Hydration ↓  Weight ↓   Risk ↑    Diagnosis

Rules:
- Only critical points
- No dense charting

---

## 5.4 SYSTEM / TECH OVERLAY

System visibility:

[ Data Sources ]
        ↓
[ Ingestion ]
        ↓
[ SDS ]
        ↓
[ Risk Engine ]
        ↓
[ API Output ]

Example Output:

{
  "risk_score": 72,
  "confidence": 0.87,
  "signals": ["hydration", "weight"]
}

---

# 6. STATE TRANSITIONS

SYSTEM STATE MODEL

[ System Surface ]
        │
        ├── Signal Detail Overlay
        ├── Insurance Overlay
        ├── Timeline Overlay
        └── System Overlay

Rules:
- No navigation
- No page reload
- Overlay only

---

# 7. MOTION MODEL

Triggered ONLY by data change.

Allowed:
- risk pulse (threshold change)
- signal emergence
- subtle ambient drift

Forbidden:
- hover animations
- decorative motion
- looping effects

---

# 8. COLOR SYSTEM

Neutral dominant

Green → active  
Amber → elevated  
Red → critical  

Rules:
- color = meaning only
- no decoration

---

# 9. TYPOGRAPHY

Risk → dominant  
System text → minimal  
No expressive styling  

---

# 10. FAILURE CONDITIONS

System fails if it becomes:

- dashboard
- SaaS UI
- card-based layout
- explanation-heavy

---

# 11. SUCCESS CONDITION

User perception:

"I am observing a system, not using an interface."

---

# FINAL PRINCIPLE

The UI does not explain the system.

The UI IS the system.
