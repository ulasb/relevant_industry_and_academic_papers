# Recommender Systems

## Why this topic matters
Recommender systems are central to any two-sided marketplace: they decide who sees what, balance supply and demand, and shape both engagement and revenue. For a recruitment / jobboard platform specifically, the matching problem (jobseeker ↔ job) has unusual properties — items have short lifetimes, both sides are heterogeneous, and the "right answer" depends on multiple stakeholders' utilities at once. New retrieval/ranking architectures, calibration techniques, and multi-stakeholder methods all transfer.

## Tracked sources
- arxiv: cs.IR, cs.LG (filter for "recommender")
- RecSys conference proceedings
- KDD, WWW, SIGIR proceedings
- Industry blogs: Netflix Tech Blog, LinkedIn Engineering, Pinterest Engineering, Spotify R&D, Etsy Engineering, Meta Research, Amazon Science, Glassdoor Engineering, Indeed Engineering

## Search query templates
- "recommender system" site:arxiv.org
- "two-tower" OR "two tower" recommender
- "sequential recommendation" OR "session-based recommendation"
- "candidate generation" recommendation
- "calibrated ranking" OR "ranking calibration"
- "cold start" recommendation
- "two-sided marketplace" recommender

## Relevance heuristics
- HIGH: production-scale lessons, marketplace-specific architectures, retrieval+ranking systems with deployment lessons, calibration, multi-stakeholder utility
- MEDIUM: academic methods with a clear path to deployment, novel loss functions, negative sampling
- LOW: pure theory, single-domain (movies/music) papers without a transfer story
