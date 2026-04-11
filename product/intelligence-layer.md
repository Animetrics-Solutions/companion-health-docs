# Companion Health — Signal Detection System (SDS) Specification
Version: v1.0
Status: PRODUCTION / INSTITUTIONAL GRADE
Owners: Data Science, Platform, Product

# 0. SYSTEM OVERVIEW

The Signal Detection System (SDS) is the foundational intelligence layer responsible for transforming raw time-series pet data into validated, structured signals that feed the Risk Engine.

Pipeline:

Raw Observations → Baseline Engine → Deviation Engine → Signal Formation → Signal Scoring → Output to Risk Engine


# 1. OBJECTIVE

The SDS must:

- Detect meaningful deviations from individual baseline behavior
- Suppress noise and transient anomalies
- Produce stable, explainable signals
- Operate deterministically under incomplete data conditions

The SDS must NOT:

- Diagnose medical conditions
- Generate recommendations
- React to single-point anomalies


# 2. CORE DEFINITIONS

## 2.1 Observation

A raw, timestamped measurement:

O_m(t) = value of metric m at time t

2.2 Time Series

For each metric:

X_m = {x_1, x_2, ..., x_t}
2.3 Baseline Distribution

Baseline is modeled as:

B_m ~ N(μ_m, σ_m)

Where:

μ_m = weighted rolling mean
σ_m = weighted rolling standard deviation

2.4 Deviation

Deviation is defined as standardized distance from baseline:

D_m(t) = (x_t - μ_m) / σ_m

2.5 Signal

A signal is a validated deviation that satisfies:

statistical significance
temporal persistence
directional relevance
2.6 Signal Magnitude

Normalized severity of deviation:

S_m = min(|D_m| / z_max, 1)

z_max = 3

3. METRIC CONFIGURATION

Each metric is configured as follows:

Metric	Threshold θ	Weight	Direction	Criticality
Hydration	1.0	0.35	Negative	High
Weight	1.5	0.25	Negative	High
Activity	1.2	0.20	Both	Medium
Sleep	1.2	0.20	Both	Medium

Direction Rules
Negative → decrease indicates risk
Positive → increase indicates risk
Both → deviation in either direction

4. BASELINE ENGINE
4.1 Rolling Window
W = 21 days
4.2 Weight Function
w_i = exp(-λ × age_i)
λ = 0.1
4.3 Mean
μ = Σ(x_i × w_i) / Σ(w_i)
4.4 Variance
σ² = Σ(w_i × (x_i - μ)²) / Σ(w_i)
4.5 Minimum Data Condition
n ≥ 30 observations required

If not satisfied:

degrade confidence
suppress signal formation

5. DEVIATION ENGINE
5.1 Z-Score
z = (x_t - μ) / σ
5.2 Clipping
z_clipped = max(min(z, 4), -4)
5.3 Direction Filter
if direction = negative and z > 0 → discard
if direction = positive and z < 0 → discard

6. TEMPORAL MODEL
6.1 Duration
duration = consecutive time steps where |z| ≥ θ
6.2 Velocity
v = (z_t - z_t-1) / Δt
6.3 Acceleration
a = (v_t - v_t-1) / Δt
6.4 Persistence
P = min(duration / τ, 1)
τ = 3 days

7. SIGNAL FORMATION PIPELINE

8. SIGNAL SCORING
8.1 Base Score
S_base = min(|z| / 3, 1)
8.2 Temporal Adjustment
S_temp = S_base × (0.5 + 0.5 × P)
8.3 Velocity Adjustment
if v > 0 → factor = 1.1
if v < 0 → factor = 0.9
8.4 Final Score
S_final = S_temp × velocity_factor

9. SIGNAL OBJECT
{
  "metric": "hydration",
  "z_score": -2.17,
  "z_clipped": -2.17,
  "signal_score": 0.72,
  "duration_days": 4,
  "velocity": -0.3,
  "acceleration": -0.1,
  "persistence": 1.0,
  "confidence": 0.9,
  "timestamp": "2026-01-12T10:00:00Z"}

10. SIGNAL INTERACTION
10.1 Correlation Matrix
	Hydration	Weight	Activity
Hydration	1	0.6	0.3
Weight	0.6	1	0.4
Activity	0.3	0.4	1

10.2 Interaction Formula
interaction_factor = 1 + (correlation × overlap)
10.3 Overlap
overlap = min(duration_i, duration_j) / τ

11. CONFIDENCE MODEL
Inputs
data completeness
signal consistency
cross-signal agreement
Formula
confidence = 0.4×completeness + 0.3×consistency + 0.3×agreement

12. EDGE CASE HANDLING
Missing Data
reduce confidence
do not spike signal
Sensor Failure
if missing > 24h → suppress signal
Outliers
cap z-score at ±4
require persistence
13. TEST CASES
Case A

z = 0.8 → no signal

Case B

z = -2.5 for 3 days → valid signal

Case C

z spike for 1 datapoint → ignore

14. OBSERVABILITY

System must log:

signal creation rate
z-score distribution
false positive rate
duration distribution
15. SYSTEM GUARANTEES

The SDS guarantees:

noise suppression
stability of outputs
deterministic behavior
graceful degradation
FINAL PRINCIPLE

A signal is not a datapoint.

It is a statistically validated, temporally consistent deviation that contributes to risk.
