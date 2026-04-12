# Companion Health — System Demo V1 Specification
Version: v1.0
Status: BUILD READY

---

# 0. PURPOSE

Build a LIVE SYSTEM INTERFACE that:

- consumes real/simulated pet data (TRW dataset)
- processes via SDS + Risk Engine
- generates UI_STATE
- renders deterministically

This is NOT a demo.
This is the system running in a controlled environment.

---

# 1. SYSTEM ARCHITECTURE

DATA LAYER → PROCESSING LAYER → UI_STATE → UI RENDER

---

## 1.1 DATA LAYER

Source:
- TRW dataset (~10,000 entries)

Structure (per pet):

{
  pet_id,
  timestamp,
  hydration,
  weight,
  activity,
  vitals[],
  metadata
}

---

## 1.2 TIME ENGINE

Purpose:
Simulate temporal progression

State:

current_time: timestamp
mode: "live" | "replay"

Controls:

- timeline slider (Day -30 → Today)
- play/pause
- speed (1x, 2x, 5x)

---

## 1.3 PROCESSING PIPELINE

For each time step:

1. Extract historical window (W = 30 days)
2. Compute baseline (DBE)
3. Generate signals
4. Compute signal strength
5. Pass to Risk Engine
6. Generate UI_STATE

---

# 2. CORE FUNCTION

## 2.1 UI_STATE GENERATOR (MANDATORY)

Function:

generateUIState(pet_id, current_time, perspective) → UI_STATE

---

## 2.2 UI_STATE STRUCTURE

UI_STATE {

  header: {
    pet_name,
    age,
    breed
  }

  risk: {
    value: number,
    status: string,
    band: number,
    pulse: "none" | "light" | "medium" | "strong"
  }

  signals: [
    {
      id,
      label,
      trend: "up" | "down" | "stable",
      strength: number,
      prominence: "low" | "medium" | "high",
      confidence: number,
      persistence_days: number,
      visible: boolean
    }
  ]

  timeline: [
    {
      timestamp,
      event_type,
      description
    }
  ]

  factors: [
    {
      label,
      contribution_score
    }
  ]

  system: {
    confidence_level,
    cold_start,
    data_latency
  }

  perspective: {
    mode: "pet_parent" | "insurance" | "veterinary"
  }

}
3. FRONTEND SYSTEM INTERFACE
3.1 GLOBAL LAYOUT

3-column system layout:

LEFT PANEL → ENTITY + SYSTEM NAV
CENTER → PRIMARY SYSTEM SURFACE
RIGHT PANEL → INTELLIGENCE + TIMELINE

3.2 LEFT PANEL (CONTROL LAYER)
Components:
Pet Selector
list of pets
status indicator (risk color)
search
System Mode
LIVE / REPLAY toggle
Time Control
slider (Day -30 → Today)
play/pause

3.3 CENTER PANEL (DECISION ENGINE SURFACE)

A. Risk Core (DOMINANT)
large numeric display
updates via interpolation
pulse on threshold crossing

B. Signal Strip
top 3 signals
horizontal layout

Each signal:

[ICON] Hydration ↓

Interaction:

click → expand inline

C. Expanded Signal View

On click:

micro trend chart (last 14 days)
contribution score
persistence
confidence
D. Perspective Switch

Toggle:

[ Pet Parent ] [ Insurance ] [ Veterinary ]

Effect: modifies UI_STATE interpretation

E. Action Block
primary recommendation
confidence indicator

3.4 RIGHT PANEL (INTELLIGENCE)

Tabs:

1. Timeline
chronological events
signal emergence
risk transitions

2. Risk Factors
contribution blocks

Example:

Hydration: +24
Weight: +18

3. Data Sources
source status (live/delayed)
ingestion health

4. INTERACTION MODEL
4.1 SYSTEM-DRIVEN
risk updates automatically
signals update based on SDS
4.2 USER-DRIVEN

User can:

change time
switch perspective
expand signals
switch pet

User CANNOT:

modify system logic
override signals

5. STATE FLOW
Default State
risk visible
signals visible
On Time Change
recompute UI_STATE
update UI instantly
On Signal Click
expand detail view
On Perspective Change
update interpretation only

6. MOTION RULES

Allowed:

risk interpolation
signal fade
subtle transitions (<300ms)

Forbidden:

page transitions
heavy animations
decorative motion

7. DEMO SCENARIOS (BUILT-IN)

Scenario 1: Early Risk Emergence
hydration drops
signal appears
risk increases

Scenario 2: Insurance View
show lead time
show risk trajectory

Scenario 3: Veterinary View
show signal depth
show clinical indicators

8. SUCCESS CRITERIA

System must:

feel live
respond to time changes instantly
show causality clearly
require no explanation
FINAL PRINCIPLE

The demo is not a walkthrough.

The demo is the system running.
