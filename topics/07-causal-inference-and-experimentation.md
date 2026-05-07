# Causal Inference & Online Experimentation

## Why this topic matters
A/B testing is how product decisions get validated, but two-sided marketplaces violate the standard assumptions in interesting ways: jobseeker-side and employer-side experiments contaminate each other, treatment effects are heterogeneous, and the metrics that matter (long-term value, retention, lifetime revenue) are observed weeks or months after the experiment ends. Variance reduction, switchback designs, uplift modeling, and long-term value inference from short-term proxies are all active research areas with clear marketplace applications.

## Tracked sources
- arxiv: stat.ME, stat.ML, cs.LG, econ.EM
- KDD, NeurIPS (causal track), ICML, JSM
- Industry blogs: Netflix Tech Blog, LinkedIn Engineering, Airbnb Engineering, Uber Engineering, DoorDash, Booking.com, eBay Tech, Microsoft Experimentation (Ron Kohavi's group), StatSig blog, Eppo blog, Optimizely blog
- Academic: Susan Athey, Guido Imbens, Stefan Wager, Microsoft / Facebook Core Data Science

## Search query templates
- "marketplace experimentation" OR "two-sided experiments"
- "interference" causal site:arxiv.org
- "CUPED" OR "variance reduction" experimentation
- "switchback" experiment design
- "uplift modeling" OR "heterogeneous treatment effects"
- "long-term value" causal proxy
- "synthetic control" online

## Relevance heuristics
- HIGH: marketplace-specific experimentation (interference, switchback, supply-demand contamination), variance reduction with practical recipes, long-term LTV inference from short observations, sequential testing
- MEDIUM: heterogeneous treatment effect methods, observational causal methods for non-experimentable interventions
- LOW: pure theory without an applied path, methods requiring assumptions that don't fit a marketplace context
