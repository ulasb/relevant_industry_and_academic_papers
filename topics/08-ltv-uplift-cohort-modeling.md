# LTV, Uplift & Cohort Modeling

## Why this topic matters
Lifetime value modeling sits at the heart of acquisition decisions: how much should we spend to acquire a user, given what they'll be worth over time? In a two-sided marketplace, "user value" isn't a single number — it has multiple revenue streams (per-action, per-subscription, etc.), long observation horizons, and depends on marketplace conditions that change over time. Uplift / incrementality modeling is what turns LTV into actionable bid signals. Calibration drift and recalibration cadence are perennial operational problems.

## Tracked sources
- arxiv: cs.LG, stat.ML, econ.EM
- KDD, NeurIPS, ICML
- Industry blogs: Uber Engineering (lots of LTV/uplift), Netflix Tech Blog, Airbnb Engineering, Booking.com, Spotify R&D, Wayfair Tech Blog, DoorDash Engineering, Lyft Engineering
- Marketing measurement: Google (Marketing Mix Modeling), Meta (Robyn), Recast, Northbeam blogs
- Subscription/SaaS LTV literature

## Search query templates
- "customer lifetime value" prediction site:arxiv.org
- "uplift modeling" OR "incrementality"
- "cohort" survival churn LTV
- "marketing mix modeling" OR "MMM"
- "media mix" causal
- "bid optimization" LTV value
- "subscription" churn prediction

## Relevance heuristics
- HIGH: uplift/incrementality methods that handle marketplace causality, LTV for two-sided marketplaces, model drift detection, calibration over long horizons, hierarchical / multi-output value models
- MEDIUM: novel survival models, churn prediction architectures, MMM methods
- LOW: pure subscription-LTV (BG/NBD etc.) without marketplace adaptation, single-value-stream models
