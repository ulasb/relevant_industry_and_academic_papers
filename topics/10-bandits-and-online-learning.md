# Contextual Bandits & Online Learning

## Why this topic matters
Bid optimization, ranking calibration, and content exploration all have an explore/exploit structure that contextual bandits address well. Off-policy evaluation is especially valuable: we have lots of logged interaction data and want to know what would happen under a different policy without running another A/B test. Slate / list-wise bandits, cold-start exploration, and continual online learning systems are all directly relevant.

## Tracked sources
- arxiv: cs.LG, stat.ML
- NeurIPS, ICML, COLT, AISTATS
- Industry blogs: Microsoft Research (Decision Service), Spotify R&D, Netflix Tech Blog, LinkedIn Engineering, Stitch Fix Algorithms, Yahoo Research (historical), Deezer R&D
- RecSys + IR conferences for bandit-flavored work

## Search query templates
- "contextual bandit" production site:arxiv.org
- "off-policy evaluation" OR "counterfactual evaluation"
- "Thompson sampling" online
- "explore exploit" recommendation
- "slate bandit" OR "ranking bandit"
- "online learning" marketplace OR auction

## Relevance heuristics
- HIGH: off-policy evaluation methods for marketplaces, slate / list-wise bandits with practical recipes, cold-start exploration for new items, real-time learning systems
- MEDIUM: novel bandit algorithms with regret bounds + practical applicability
- LOW: pure regret-bound theory, single-arm bandit toy problems
