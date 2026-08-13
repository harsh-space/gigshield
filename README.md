# Coverent ![Hackathon Project](https://img.shields.io/badge/type-Hackathon%20Project-orange)
## Parametric Income Insurance for Q-Commerce Riders

**Live Demo Links:**
- **Rider PWA:** [coverent.vercel.app/onboarding](https://coverent.vercel.app/onboarding)
- **Insurer Dashboard:** [coverent-insurer-dashboard.vercel.app](https://coverent-insurer-dashboard.vercel.app)

---

> Automated weekly income protection for Zepto / Blinkit / Swiggy Instamart delivery partners. When a disruption is detected, the payout goes out automatically. No claim forms. No waiting.

---

## The Problem

A full-time Blinkit or Zepto rider earns ₹800–₹1,200/day working 9–10 hours out of a single dark store. Their entire income depends on a 1.5–2km delivery radius staying operational.

One flooded road, one severe AQI day, one platform outage during peak hours — and that day's income is gone. No compensation. No safety net. Over a Delhi monsoon season, riders lose 4–6 such days, translating to ₹3,800–₹5,700 in unprotected income loss.

Coverent insures that lost income — automatically, weekly, and built exclusively for Q-Commerce riders.

---

## Persona: The Q-Commerce Rider

- Works out of one fixed dark store (Zepto / Blinkit / Swiggy Instamart)
- Delivers within a 1.5–2km radius, completing 3–5 orders/hour at peak
- Earns ₹20–₹35/order base + distance pay + milestone incentives
- Peak earning window: 6–11 PM (~40% of daily income)
- Weekly earnings: ₹3,000–₹7,200 depending on city and hours worked

The 10-minute delivery promise means even a 45-minute disruption during peak hours causes disproportionate income loss — not just fewer orders, but missed incentive slabs too.

---

## Worker Scenarios

### Scenario 1 — Ravi, Blinkit Rider, Delhi (Monsoon Waterlogging)

Ravi earns ₹950/day from a dark store in Rohini. On August 13, 2024, IMD issues a Red Alert for Delhi-NCR — two roads within 2km of his store are waterlogged by 11 AM. He cannot safely ride.

**Without Coverent:** ₹950 gone. Over 4–6 such days per monsoon season, that's ₹3,800–₹5,700 with zero recourse.

**With Coverent:** IMD Red Alert + maps API confirms flooding within 2km of his dark store. Trigger fires. ₹665 credited to UPI by 2 PM — while the roads are still flooded.

---

### Scenario 2 — Priya, Zepto Rider, Delhi (Severe AQI)

Priya works the 6–11 PM peak slot in Dwarka, earning ₹780/evening. On November 18, 2024, Delhi's AQI hits 491. She logs off after 90 minutes — 6 orders instead of 18–20. Evening earnings: ₹210.

**Without Coverent:** ₹570 lost. Delhi's AQI exceeded 400 for 9 consecutive days in November 2024 with zero recourse.

**With Coverent:** AQI ≥301 confirmed in Dwarka for 3+ consecutive hours during her active shift. Trigger fires. ₹455 to UPI within 2 hours.

---

### Scenario 3 — Arjun, Swiggy Instamart Rider, Mumbai (Platform Outage)

Arjun earns ₹1,050/day in Andheri West. On a Friday at 7:23 PM, Swiggy's order-assignment system goes down for 52 minutes. He 
completes 4 orders instead of his usual 14 and misses his weekly incentive milestone by the exact orders the outage cost him.

**Without Coverent:** ₹280 order loss + ₹300 missed bonus = ₹580 gone on a single Friday night.

**With Coverent:** Downtime >45 minutes during peak detected. GPS confirms Arjun was active in zone. Fraud check clears. ₹385 to UPI before midnight.

---

## Platform Choice: Hybrid (PWA + Web Dashboard)

**Rider Interface — Progressive Web App (PWA)**
Every Q-Commerce rider owns a smartphone — it is a mandatory requirement to join Blinkit, Zepto, or Swiggy Instamart. A PWA is accessible via browser link, installable to home screen, and push-notification capable with zero installation barrier. No Play Store approval, no storage friction, works on any Android device.

**Insurer / Admin Interface — Web Dashboard**
The insurer-side user monitors live triggers, reviews flagged claims, and tracks loss ratios at a desk. This requires data-dense views — maps, charts, claim queues — that are web-only use cases.

**Result:** Two interfaces, one backend, right tool for each user.

---

## Application Workflow

<p align="center">
  <img src="docs/appflowchart.png" width="300" alt="Application Workflow"/>
  <br/>
  <em>Figure 1: Coverent application workflow — rider PWA onboarding through insurer dashboard payout audit</em>
</p>

### Rider PWA (6 Steps)

**Step 1 — Onboarding (one-time, ~3 min)**
Phone login → select platform → platform ID → dark store pincode → UPI ID → income tier (Low/Mid/High) → shift window.

**Step 2 — AI Risk Profiling (automatic, ~60 sec)**
No rider action. Zone scored (0–100) from historical weather + AQI data. Rider sees: *"Zone risk: 74/100. 
Recommended: Suraksha Plus."*

**Step 3 — Weekly Policy Purchase**
Select plan → pay via UPI → active Monday to Sunday → auto-renewal prompt every Sunday.

**Step 4 — Trigger Monitoring (continuous, no rider action)**
System polls weather, AQI, and platform APIs automatically. Trigger fires only if policy is active and rider was online.

**Step 5 — Auto Claim + Fraud Check (<2 min)**
3 checks run simultaneously: GPS validation, duplicate check, anomaly detection. All pass → approved. Any flag → manual review.

**Step 6 — Payout**
Amount calculated → sent to UPI → push notification to rider. Target: within 2 hours of trigger.

---

### Insurer Web Dashboard

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">View</th>
      <th style="padding: 10px;">What It Shows</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Live Trigger Map</td>
      <td style="padding: 10px;">Active events (Rain/Heat/AQI) with zone overlays.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Claims/Payouts Queue</td>
      <td style="padding: 10px;">Audit log of all auto-approved payouts with fraud details.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Analytics Dashboard</td>
      <td style="padding: 10px;">Loss ratio, zone-wise claims, and fund disbursement.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Mock Trigger Dispatch</td>
      <td style="padding: 10px;">Manual simulation for demo triggers and stress tests.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Policy Management</td>
      <td style="padding: 10px;">Active policies, tier distribution, and pool limits.</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 1. Insurer web dashboard views and contents.</b></p>

</div>

---

## Weekly Premium Model

### Why Weekly?

77.6% of gig workers in India earn ₹2.5 lakh or less per year. Zepto and Blinkit both run weekly payout cycles (Monday–Sunday, credited by Tuesday). Coverent's premium deducts from that payout automatically — the rider never needs to actively pay. Zero friction, zero defaults.

### Income Tiers

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Tier</th>
      <th style="padding: 10px;">Weekly Earnings</th>
      <th style="padding: 10px;">Monthly Equivalent</th>
      <th style="padding: 10px;">Profile</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Low</td>
      <td style="padding: 10px;">₹3,000–₹4,200</td>
      <td style="padding: 10px;">₹12,000–₹15,000</td>
      <td style="padding: 10px;">Part-time / Tier-2 city</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Mid</td>
      <td style="padding: 10px;">₹4,800–₹6,000</td>
      <td style="padding: 10px;">₹25,000–₹30,000</td>
      <td style="padding: 10px;">Full-time / Metro</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">High</td>
      <td style="padding: 10px;">₹6,600–₹7,200</td>
      <td style="padding: 10px;">₹30,000–₹40,000</td>
      <td style="padding: 10px;">High-performer / Metro</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 2. Rider income tiers — weekly earnings and profile.</b></p>

</div>

*Source: Blinkit/Zepto official partner earnings data, Invezz gig worker survey 2025*

### Premium Formula

```
Weekly Premium = (Base Premium + AI Risk Loading) × Plan Multiplier
```

**Base Premium — 2.5% of weekly income (parametric microinsurance benchmark)**

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Tier</th>
      <th style="padding: 10px;">Base Premium</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Low</td>
      <td style="padding: 10px;">₹89/week</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Mid</td>
      <td style="padding: 10px;">₹139/week</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">High</td>
      <td style="padding: 10px;">₹179/week</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 3. Base premium by income tier.</b></p>

</div>

**AI Risk Loading — XGBoost model, range: -₹20 to +₹30**
Calculated at onboarding based on zone history. Neutral score = 74.

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Input Feature</th>
      <th style="padding: 10px;">Source</th>
      <th style="padding: 10px;">Weight</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">3-year waterlogging frequency (pincode)</td>
      <td style="padding: 10px;">IMD historical</td>
      <td style="padding: 10px;">High</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Seasonal AQI severity score</td>
      <td style="padding: 10px;">CPCB / AQICN historical</td>
      <td style="padding: 10px;">High</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">City tier (metro / Tier-2 / Tier-3)</td>
      <td style="padding: 10px;">Registration data</td>
      <td style="padding: 10px;">Medium</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Dark store zone composite risk score</td>
      <td style="padding: 10px;">City flood + OSM maps</td>
      <td style="padding: 10px;">Medium</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Rider's active shift window</td>
      <td style="padding: 10px;">Platform API (simulated)</td>
      <td style="padding: 10px;">Low</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Rider's prior claim count</td>
      <td style="padding: 10px;">Internal DB</td>
      <td style="padding: 10px;">Low</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 4. AI risk loading — input features and weights.</b></p>

</div>

*Example: Mid-tier rider in Rohini, Delhi pays ₹169/week. Same tier in Kharadi, Pune pays ₹119/week.*

### Coverage Plans (Mid-Tier Benchmark)

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Plan</th>
      <th style="padding: 10px;">Max Covered Days/Week</th>
      <th style="padding: 10px;">Max Payout/Week</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Suraksha Lite</td>
      <td style="padding: 10px;">1 day</td>
      <td style="padding: 10px;">₹630</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Suraksha Plus</td>
      <td style="padding: 10px;">2 days</td>
      <td style="padding: 10px;">₹1,260</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Suraksha Max</td>
      <td style="padding: 10px;">3 days</td>
      <td style="padding: 10px;">₹1,890</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 5. Coverage plans — Mid-tier benchmark.</b></p>

</div>

### Payout Formula

```
Payout = Base Daily Payout × Severity Multiplier
```
*Where Base Daily Payout = (Weekly Income ÷ 6) × 0.70*

The 0.70 factor prevents over-insurance moral hazard.

**Severity Multiplier (Based on API Trigger Intensity)**
- **Moderate (≤ 5.0):** 30% Payout
- **High (≤ 8.0):** 60% Payout
- **Severe (> 8.0):** 100% Payout

**Example:** Mid-tier rider earning ₹5,400/week during a "Severe" Rainfall trigger (Intensity 9.2) receives `(₹5,400 ÷ 6) × 0.70 × 1.0 = ₹630 → UPI within 2 hours`.

**Loss ratio estimate** (10,000 riders, Delhi-NCR + Mumbai):
- Peak monsoon (1.2 disrupted days/rider/week): ~45%
- Off-season (0.3 days/week): ~11%
- **Blended annual: ~28%** — commercially sustainable

### Hyperlocal Pool Protection
**Coverent** implements a safety valve at the pincode level. If a specific zone's loss ratio exceeds **85%**, new policy enrollments are paused to guarantee full payouts for existing members.

---

## Parametric Triggers

Five triggers. All objective, all API-verifiable, all tied directly to income loss within a rider's 2km zone. Trigger fires → payout initiates. No claim filing.

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">#</th>
      <th style="padding: 10px;">Trigger</th>
      <th style="padding: 10px;">Exact Threshold</th>
      <th style="padding: 10px;">Income Loss Mechanism</th>
      <th style="padding: 10px;">Data Source</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">1</td>
      <td style="padding: 10px;">Hyperlocal Waterlogging</td>
      <td style="padding: 10px;">IMD Red Alert (≥64.5mm/day) AND ≥1 road within 2km of dark store flooded</td>
      <td style="padding: 10px;">Zone completion collapses; rider cannot operate</td>
      <td style="padding: 10px;">OpenWeatherMap + Google Maps</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">2</td>
      <td style="padding: 10px;">Extreme Heat</td>
      <td style="padding: 10px;">IMD Heat Wave (≥45°C) AND platform completion rate &lt;40% for ≥2 hrs</td>
      <td style="padding: 10px;">Riders log off; cannot sustain peak delivery pace</td>
      <td style="padding: 10px;">OpenWeatherMap + Simulated platform API</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">3</td>
      <td style="padding: 10px;">Severe AQI</td>
      <td style="padding: 10px;">CPCB AQI ≥301 in rider's pincode for ≥3 consecutive hours during shift</td>
      <td style="padding: 10px;">Respiratory stress forces early log-off; 6–10 delivery cycles lost</td>
      <td style="padding: 10px;">AQICN API</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">4</td>
      <td style="padding: 10px;">Zone / Market Closure</td>
      <td style="padding: 10px;">Municipal/police order closing dark store zone or delivery zone</td>
      <td style="padding: 10px;">Dark store shuts; riders cannot enter/exit zone</td>
      <td style="padding: 10px;">Simulated municipal alert API</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">5</td>
      <td style="padding: 10px;">Platform Outage</td>
      <td style="padding: 10px;">Order-assignment system down ≥45 mins during 6–10 PM peak</td>
      <td style="padding: 10px;">Rider active but receives zero orders; peak = ~40% of daily earnings</td>
      <td style="padding: 10px;">Simulated platform status API</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 6. Parametric triggers, thresholds, and data sources.</b></p>

</div>

---

## AI/ML Integration Plan

### Model 1 — Zone Risk Scoring Engine

**Job:** Score a rider's zone at onboarding → determine AI risk loading on weekly premium.
**Algorithm:** XGBoost Regressor trained on **1,500+ samples** derived from **3-year historical IMD and CPCB records**.
**Inputs (6):** `zone_flood_score`, `zone_aqi_score`, `shift_pattern_score`, `city_tier`, `historical_claim_rate`, `zone_composite_score`.
**Output:** Risk score (0–100) → premium adjustment (-₹20 to +₹30).

#### XGBoost Model Architecture & Approach

**1. Model Objective & Hyperparameters**
The engine uses an `XGBRegressor` with a `reg:squarederror` objective to predict a continuous risk score.
- **n_estimators:** 100 | **max_depth:** 5 | **learning_rate:** 0.1 | **Target**: Disruption probability.

**2. Feature Engineering Logic**
- **Hyperlocal Baselines**: `zone_flood_score` (0-10) uses **3-year historical IMD archives** to weight pincodes by flooding frequency.
- **Environmental Risk**: `zone_aqi_score` (0-10) reflects seasonal **CPCB pollution peaks** around the dark store.
- **Operational Exposure**: `shift_pattern_score` account for the specific vulnerability of the rider's shift window.

**3. Our Approach: Hyperlocal & Data-Driven**
- **Precision**: Unlike city-wide insurance, we operate at **pincode-level granularity**, matching the 2km Q-Commerce delivery radius.
- **Project Status**: The full pipeline—from data generation (`ml/generate_risk_data.py`) to the trained model (`risk_score_model.pkl`) and PWA integration—is **fully built and functional**.

**4. Core Assumptions**
- **Centricity**: The model assumes the rider spends >80% of their shift within the 2km radius of their dark store.
- **Stationarity**: Historical risk remains a valid predictive baseline for the 1-week policy window.

---

### Model 2 — Fraud Detection Engine

**Job:** Validate every auto-triggered claim before payout releases. CLEAR → instant payout. FLAG → manual review.
**Algorithm:** Isolation Forest (unsupervised anomaly detection) — requires no labeled fraud data at launch. Learns normal claim behavior and flags deviations.

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Check</th>
      <th style="padding: 10px;">Flag Condition</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">GPS zone validation</td>
      <td style="padding: 10px;">Last ping outside 2km of registered dark store</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Activity validation</td>
      <td style="padding: 10px;">Rider logged off &gt;30 min before trigger fired</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Duplicate claim check</td>
      <td style="padding: 10px;">Same trigger type claimed twice in 7-day window</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Velocity anomaly</td>
      <td style="padding: 10px;">GPS jump &gt;5km in &lt;3 minutes</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Historical pattern check</td>
      <td style="padding: 10px;">Claim in zone with no prior disruption history for this trigger</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 7. Fraud detection checks and flag conditions.</b></p>

</div>

**Output:** CLEAR or FLAG (review target: 4 hours).

---

### Model 3 — Predictive Disruption Forecaster

**Job:** Power the insurer dashboard's 7-day payout liability forecast.
**Algorithm:** LSTM — chosen for modeling seasonal patterns like monsoon cycles and AQI spikes. Falls back to XGBoost regressor if not completed in time.
**Inputs:** 7-day weather + AQI forecast, historical trigger frequency by zone, active enrolled riders per zone.
**Output:** Estimated claims + payout liability per zone for the next 7 days. Runs every Sunday night.

*All models trained on synthetic data generated from real IMD/CPCB historical records. In production, Models 1 and 3 retrain quarterly. Model 2 updates its anomaly baseline continuously.*

---

## Adversarial Defense & Anti-Spoofing Strategy

> **Context:** A coordinated ring of 500 riders using GPS spoofing
> apps can fake their location into a Red Alert zone and trigger
> mass auto-payouts. Simple GPS verification is insufficient.
> Coverent defends at three layers.

---

### Layer 1 — Differentiating a Genuine Worker from a Spoofer

A real stranded rider leaves a physical trail a spoofing app
cannot replicate. Isolation Forest cross-checks 5 signals:

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Signal</th>
      <th style="padding: 10px;">Genuine Worker</th>
      <th style="padding: 10px;">Spoofer</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Location history</td>
      <td style="padding: 10px;">Gradual movement toward dark store, then stops</td>
      <td style="padding: 10px;">Teleports into zone at trigger time</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Accelerometer + battery</td>
      <td style="padding: 10px;">Shows bike motion, normal drain</td>
      <td style="padding: 10px;">Flat — stationary device</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Platform activity</td>
      <td style="padding: 10px;">Online and accepting orders before trigger</td>
      <td style="padding: 10px;">Login spike exactly at trigger, no prior activity</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Cell tower vs GPS</td>
      <td style="padding: 10px;">Tower pings match dark store vicinity</td>
      <td style="padding: 10px;">Tower pings contradict GPS coordinates</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Zone order history</td>
      <td style="padding: 10px;">4-week delivery pattern in this zone</td>
      <td style="padding: 10px;">No prior history in this zone</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 8. Genuine-worker vs. spoofer signal comparison.</b></p>

</div>

**Flag condition:** Any 2 of 5 signals contradict GPS claim →
held for review. All 5 consistent → auto-approved.

---

### Layer 2 — Catching a Coordinated Ring (Population-Level Checks)

Individual checks catch solo spoofers. A ring of 500 needs
zone-level detection:

- **Claim velocity:** If claims in a zone spike >3 standard
  deviations above historical baseline within 15 minutes →
  entire zone's auto-approval paused.
- **Payout-to-active ratio:** Claims exceeding 140% of riders
  verified active in the 2 hours pre-trigger → excess flagged.
  Real disruptions only affect riders who were working.
- **Coordination fingerprint:** 10+ riders in the same zone
  showing GPS jumps within a 60-second window → coordinated
  spoofing escalated to insurer review.

---

### Layer 3 — Protecting Honest Workers from False Positives

A rider with a genuine network drop should never lose their payout.

- Flagged claims are **held, not rejected** — payout is reserved.
- Rider notified immediately: *"Claim under review — resolved
  within 4 hours. Payout protected if disruption is confirmed."*
- A rider failing only the GPS check (network drop) but passing
  the other 4 signals → **auto-approved.**
- System tuned to **95% recall on genuine claims** — fewer than
  5% of legitimate claims are incorrectly flagged.

---

### Defense Summary

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Attack</th>
      <th style="padding: 10px;">Defense</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Solo GPS spoof</td>
      <td style="padding: 10px;">5-signal Isolation Forest check</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Ring of 500 claiming at once</td>
      <td style="padding: 10px;">Claim velocity + active-rider ratio</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Coordinated spoofing app</td>
      <td style="padding: 10px;">Cross-zone fingerprint detection</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Honest rider with network drop</td>
      <td style="padding: 10px;">4-signal fallback + grace hold</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 9. Adversarial defense summary.</b></p>

</div>

---

## Tech Stack

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Layer</th>
      <th style="padding: 10px;">Technology</th>
      <th style="padding: 10px;">Reason</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Frontend</td>
      <td style="padding: 10px;">React.js (PWA + Web Dashboard)</td>
      <td style="padding: 10px;">One codebase for both interfaces; largest community; CRA sets up PWA in one command</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Backend</td>
      <td style="padding: 10px;">Python + FastAPI</td>
      <td style="padding: 10px;">Beginner-friendly, auto Swagger docs at /docs, async support for trigger polling</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Database</td>
      <td style="padding: 10px;">Firebase Firestore</td>
      <td style="padding: 10px;">Zero setup, real-time sync, free tier (50k reads/day), no SQL required</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Auth</td>
      <td style="padding: 10px;">Firebase Auth</td>
      <td style="padding: 10px;">OTP-based mobile login, free</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">ML</td>
      <td style="padding: 10px;">scikit-learn + xgboost</td>
      <td style="padding: 10px;">Industry standard, best documentation, beginner accessible</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Payments</td>
      <td style="padding: 10px;">Razorpay (test mode)</td>
      <td style="padding: 10px;">Free sandbox, UPI support</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Hosting</td>
      <td style="padding: 10px;">Vercel (frontend) + Render.com (backend)</td>
      <td style="padding: 10px;">Both free tier, zero DevOps overhead</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 10. Technology stack and rationale.</b></p>

</div>

**Total infrastructure cost: ₹0**

### Integrations

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Tool</th>
      <th style="padding: 10px;">Purpose</th>
      <th style="padding: 10px;">Cost</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">OpenWeatherMap</td>
      <td style="padding: 10px;">Rainfall, temperature, weather alerts</td>
      <td style="padding: 10px;">Free</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">AQICN</td>
      <td style="padding: 10px;">Real-time AQI by city/pincode</td>
      <td style="padding: 10px;">Free</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Google Maps / OpenStreetMap</td>
      <td style="padding: 10px;">2km radius zone check, flood layer</td>
      <td style="padding: 10px;">Free</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Razorpay</td>
      <td style="padding: 10px;">Payout sandbox</td>
      <td style="padding: 10px;">Free</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">React Router</td>
      <td style="padding: 10px;">PWA and Dashboard navigation</td>
      <td style="padding: 10px;">—</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Recharts</td>
      <td style="padding: 10px;">Insurer dashboard analytics charts</td>
      <td style="padding: 10px;">—</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Lucide React</td>
      <td style="padding: 10px;">High-fidelity iconography</td>
      <td style="padding: 10px;">—</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Firebase Cloud Messaging</td>
      <td style="padding: 10px;">Push notifications to rider PWA</td>
      <td style="padding: 10px;">—</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 11. Third-party integrations and cost.</b></p>

</div>

**Simulated in-house (mock FastAPI endpoints):**
- Platform order completion rate by zone
- Platform outage status feed
- Municipal zone closure alert feed

---

## Local Development Setup

To run **Coverent** locally on your workstation, follow these steps in order.

### 1. Prerequisites
- **Python 3.9+**
- **Node.js (v18+) & npm**
- **Firebase Account** (Firestore & Auth enabled)
- **Git** (for cloning)

### 2. Backend Environment (FastAPI)
The backend manages rider registration, ML pricing logic, and payout logs.

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   # On Windows:
   .\venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. **Firebase Configuration:**
   - Go to the [Firebase Console](https://console.firebase.google.com/).
   - Click the gear icon (Project Settings) > **Service Accounts**.
   - Click **Generate new private key**.
   - Save the JSON file as `serviceAccountKey.json` and place it in the `backend/` root directory.
   - Create a `.env` file in the `backend/` directory (copying from `.env.example`).
   - Ensure the `.env` file contains: `FIREBASE_CREDENTIALS_PATH=serviceAccountKey.json` and your `PROJECT_ID`.
5. **Initialize Database (Example Data):**
   Run the seeding script to set up mock riders, platform activity, and historical payout logs needed for the demo:
   ```bash
   python seed_db.py
   ```
6. Launch the API:
   ```bash
   python -m uvicorn app.main:app --reload
   ```
   *The API will be live at `http://localhost:8000`. Test via `/docs` (Swagger). Ensure `ENVIRONMENT=development` is set in your `.env` to enable the bypass of real Firebase token checks for mock login.*

### 3. ML Model Initialization
The risk scoring system requires the XGBoost model to be trained on historical benchmarks before it can provide pricing.

```bash
# From the project root (with venv activated):
python ml/generate_risk_data.py
python ml/train_risk_model.py
```
*This generates a `risk_score_model.pkl` in `ml/models/` which the backend loads on startup.*

### 4. Trigger Engine (Background Polling)
This process simulates the continuous monitoring of weather, AQI, and platform status.

```bash
# In a NEW terminal (with backend venv activated):
cd trigger-engine
python main.py
```
*The engine polls every 30 seconds and POSTS threshold breaches to the backend.*

### 5. Frontend Dashboards

#### Rider PWA (Mobile Experience)
```bash
cd frontend/rider-pwa
npm install
npm run dev
```
*Open `http://localhost:5173`. Use mobile view in DevTools for the best experience.*

#### Insurer Dashboard (Admin/Analytical View)
```bash
cd frontend/insurer-dashboard
npm install
npm run dev
```
*Open `http://localhost:5173` (or the next available port).*

---

## Demo Flow

Follow this 5-minute walkthrough to experience the full **Coverent** parametric lifecycle across all three interfaces.

### 1. Rider Onboarding (PWA)
- Open the **Rider PWA** (`http://localhost:5173`).
- Select **"Create New Account"**.
- Fill in details. **Critically, remember the Pincode you use (e.g., 400053).**
- Click **"Generate AI Risk Profile"**. Watch the XGBoost model calculate your zone-specific risk loading in real-time.
- Select **"Suraksha Plus"** and click **"Setup Auto-Mandate"**. Your policy is now active for the current week.

### 2. Monitor Coverage (PWA Dashboard)
- You are now on the **Rider Dashboard**.
- Note the status: **"Active Protection"**.
- Payout History will be empty.

### 3. Simulate a Disruption (Insurer Dashboard)
- Open the **Insurer Dashboard** (`http://localhost:5174`).
- Navigate to the **"Mock Triggers"** tab on the sidebar.
- **Manual Trigger:** 
    - Select a trigger type (e.g., **Heavy Rainfall**).
    - Select the **Zone/Pincode** you used in Step 1.
    - Set Intensity to **"Severe"**.
    - Click **"Authorize Manual Trigger"**.

### 4. Instant Payout Verification (PWA)
- Switch back to the **Rider PWA**.
- The Dashboard will update automatically (via Firebase sync).
- A **"New Payout"** alert will appear with the calculated amount (e.g., ₹630).
- Check the **"Transaction History"** at the bottom to see the completed UPI transfer log.

### 5. Audit & Global Analytics (Insurer)
- Switch back to the **Insurer Dashboard**.
- Go to the **"Claims Audit"** tab to see the rider's fraud-verified claim log.
- Go to **"Analytics"** to see the Pincode's Loss Ratio and the total disbursed funds update on the live charts.

---

## Assumptions & Scope

### Assumptions

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Assumption</th>
      <th style="padding: 10px;">Detail</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Income verification</td>
      <td style="padding: 10px;">Self-declared, cross-checked against earnings screenshot.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Platform Data Sync</td>
      <td style="padding: 10px;">Rider eligibility is synced with a mock platform database; 7 active days required for claim activation.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Fraud Verification</td>
      <td style="padding: 10px;">Simulated GPS &amp; activity cross-check ensures rider was active in zone during trigger event.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Idempotency</td>
      <td style="padding: 10px;">System prevents duplicate payouts for the same trigger event type within a 24-hour window.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Geographic scope</td>
      <td style="padding: 10px;">Delhi-NCR, Mumbai, Bengaluru. Tier-2 expansion supported but not demoed.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Platform data</td>
      <td style="padding: 10px;">Simulated via mock endpoints for completion rates and outage status.</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Payout timeline</td>
      <td style="padding: 10px;">Target: within 2 hours of trigger (sandbox mode).</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 12. Project assumptions.</b></p>

</div>

### Out of Scope

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Excluded</th>
      <th style="padding: 10px;">Reason</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Vehicle repair / health / accident coverage</td>
      <td style="padding: 10px;">Violates constraint — income loss only</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Monthly or annual pricing</td>
      <td style="padding: 10px;">Violates constraint — weekly only</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Food delivery / e-commerce riders</td>
      <td style="padding: 10px;">Outside Q-Commerce persona scope</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Manual claim filing</td>
      <td style="padding: 10px;">Defeats parametric insurance design</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Continuous GPS tracking</td>
      <td style="padding: 10px;">Privacy concern — last-ping validation only</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 13. Out-of-scope items and rationale.</b></p>

</div>

### Future Scope

<div align="center">

<table width="100%" style="text-align: center; border-collapse: collapse;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 10px;">Area</th>
      <th style="padding: 10px;">Detail</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Platform APIs</td>
      <td style="padding: 10px;">Direct integration replacing all mock endpoints</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Compliance</td>
      <td style="padding: 10px;">IRDAI regulatory framework for commercial launch</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Persona Expansion</td>
      <td style="padding: 10px;">Food delivery and e-commerce rider coverage</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Language Support</td>
      <td style="padding: 10px;">Hindi, Tamil, Telugu on rider PWA</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;">
      <td style="padding: 10px;">Income Verification</td>
      <td style="padding: 10px;">Aadhaar-based verification via DigiLocker API</td>
    </tr>
  </tbody>
</table>

<p style="margin-top: 10px;"><b>Table 14. Future scope items.</b></p>

</div>