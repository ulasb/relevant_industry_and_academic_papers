# Paper Digest — 2026-05-15

Search window: 2026-05-08 → 2026-05-15. Light week — the EU AI Act omnibus political agreement, the Workday class-action collective-action certification, and several strong agent-RAG / fairness preprints all landed May 5–7, just outside the window. Topics 1 (Recommender Systems), 4 (LLMs & Agents), and 8 (LTV/Uplift) had no items meet bar.

---

## Search & Information Retrieval

### Test-Time Compute for Dense Retrieval: Agentic Program Generation with Frozen Embedding Models
* **Document**: [arXiv preprint 2605.11374](https://arxiv.org/abs/2605.11374)
* **Tags**: Search & IR, Dense retrieval, Test-time compute
* **Source**: arXiv (academic preprint, May 12, 2026)
* **The Core Concept**: Shows that small embedding models can get a meaningful nDCG@10 lift at retrieval time *without retraining* — an agentic search over 259 candidate inference programs converged on a simple recipe: a softmax-weighted centroid of the top-K documents interpolated with the query. For a job search stack that can't always afford a bigger encoder, this is a cheap drop-in quality bump on top of an existing frozen index, and validates a useful pattern: spend more inference compute on hard queries rather than more training compute on the encoder.

### Rethinking Agentic Search with Pi-Serini: Is Lexical Retrieval Sufficient?
* **Document**: [arXiv preprint 2605.10848](https://arxiv.org/abs/2605.10848)
* **Tags**: Search & IR, Lexical retrieval, Agentic search, LLMs & Agents
* **Source**: arXiv (academic preprint, May 11, 2026; Jimmy Lin group)
* **The Core Concept**: A well-tuned BM25 retriever paired with a strong LLM agent matches or beats dense retrievers on BrowseComp-Plus. A useful counter-narrative for jobboard search architecture: dense retrieval is fashionable and expensive, and short noisy queries (which jobboards have a lot of) may not be where it pays off. Worth reading as a sanity check before committing to a dense-only retrieval re-platforming.

---

## Embeddings & Representation Learning

### ML-Embed: Inclusive and Efficient Embeddings for a Multilingual World
* **Document**: [arXiv preprint 2605.15081](https://arxiv.org/abs/2605.15081)
* **Tags**: Embeddings, Multilingual, Matryoshka representation learning
* **Source**: arXiv (academic preprint, May 14, 2026)
* **The Core Concept**: Introduces "3-Dimensional Matryoshka Learning" — combining Matryoshka representation, layer, *and* embedding learning into one training framework. Model family ranges from 140M to 8B parameters; SOTA on 9/17 MTEB tasks with notably strong low-resource-language results. Weights, data, and code are released. For a jobboard operating across multiple geographies and languages, a compute-tunable multilingual embedding family (smaller = cheaper online, larger = better recall) with open training data is operationally valuable for query/job encoding and for cold-start representation transfer to new locales.

---

## Online Marketplaces, Auctions & Bidding

### Beyond Prediction: Solving the Multiple Knapsack Problem at Scale — How Uber Optimizes Incentives (Tarot)
* **Document**: [Uber Engineering Blog post](https://www.uber.com/us/en/blog/solving-multiple-knapsack/)
* **Tags**: Marketplaces, Optimization, Budget pacing, Uplift modeling
* **Source**: Uber Engineering Blog (industry blog, May 14, 2026)
* **The Core Concept**: Production write-up of Uber's "Tarot" incentive-allocation platform. Treats driver/courier incentives as a multi-budget Multiple Knapsack Problem, scores candidate user-incentive pairs with uplift models across *multiple* marketplace KPIs (not just one), and then applies dynamic strategic weights to combine them into a comparable ROI score. They tried linear programming with HiGHS, hit a wall on combinatorial structure, and switched to OR-Tools CP-SAT — cutting solve time from 24+ hours to minutes for 100k+ users. A budget-pacing feedback loop reconciles configured vs. observed vs. predicted spend to hit near-complete quarterly budget utilization without overspends. Directly applicable to any CPC/CPA jobboard that allocates spend across employer budgets while balancing relevance and revenue.

---

## Jobboards, HR Tech & Two-Sided Marketplaces

### Reel Friends: Building Social Discovery that Scales to Billions
* **Document**: [Engineering at Meta post](https://engineering.fb.com/2026/05/13/ml-applications/reel-friends-building-social-discovery-that-scales-to-billions/)
* **Tags**: Two-sided marketplaces (adjacent), Discovery, ML production
* **Source**: Engineering at Meta (industry blog/podcast, May 13, 2026)
* **The Core Concept**: Meta Tech Podcast on Facebook's "Friend Bubbles" feature — surfacing Reels that friends have watched and engaged with. Covers the recommendation model's evolution and a non-obvious iOS-vs-Android behavioral divergence the team had to solve before the feature could ship at scale. Tangential to recruitment matching, but the *platform-specific behavior debugging* story is exactly the kind of thing that bites recommendation features in production and is rarely written up publicly.

---

## Causal Inference & Online Experimentation

### Real vs. Semi-Simulated: Rethinking Evaluation for Treatment Effect Estimation
* **Document**: [arXiv preprint 2605.10430](https://arxiv.org/abs/2605.10430)
* **Tags**: Causal inference, Uplift, HTE evaluation
* **Source**: arXiv (academic preprint, May 11, 2026)
* **The Core Concept**: Large empirical comparison showing that the semi-simulated benchmarks the HTE/uplift literature relies on do not predict rankings on real data — and that counterfactual metrics don't recover the estimators preferred by observable metrics. Punchline: straightforward meta-learners with strong base learners consistently beat the specialized causal-ML models. For any team picking an uplift/HTE method for a jobboard (acquisition, retention incentives, bid valuation), this is a quiet warning that published rankings are not measuring what you'd actually deploy against.

---

## Job/Resume NLP & Taxonomy

### ConFit v3: Improving Resume-Job Matching with LLM-based Re-Ranking
* **Document**: [arXiv preprint 2605.09760](https://arxiv.org/abs/2605.09760)
* **Tags**: Job/Resume NLP, LLMs & Agents, Ranking
* **Source**: arXiv (academic preprint, May 10, 2026)
* **The Core Concept**: Builds an LLM re-ranker on top of a ConFit v2 bi-encoder retriever. Four practical findings: (a) multi-pass re-ranking, (b) listwise RL objective, (c) noisy-training-data removal, (d) SFT distillation from a stronger LLM *before* RL training. With Qwen3 as the base, the result beats GPT-5 and Claude Opus-4.5 on person-job-fit benchmarks. A useful blueprint for a two-stage retrieve-then-rerank job-matching pipeline that wants to stay on small/open models for cost — and a clean ablation of which training-recipe choices actually move the needle.

---

## Contextual Bandits & Online Learning

### PFN-TS: Thompson Sampling for Contextual Bandits via Prior-Data Fitted Networks
* **Document**: [arXiv preprint 2605.10137](https://arxiv.org/abs/2605.10137)
* **Tags**: Bandits, Thompson sampling, Tabular foundation models
* **Source**: arXiv (academic preprint, May 11, 2026)
* **The Core Concept**: Uses a prior-data fitted network (TabPFN-style) as the posterior model for Thompson sampling, with a subsampled-predictive CLT that turns noisy reward predictions into mean-reward samples. Drops cost from O(n) to O(log n) dataset prefixes. Best average rank across nonlinear synthetic + OpenML classification-to-bandit benchmarks, and highest estimated policy value in an offline mobile-health evaluation. Promising for cold-start bandit problems on jobboards where tabular features dominate and Bayesian uncertainty matters but you don't want to retrain a deep model per arm.

### Sample-Mean Anchored Thompson Sampling for Offline-to-Online Learning with Distribution Shift
* **Document**: [arXiv preprint 2605.10289](https://arxiv.org/abs/2605.10289)
* **Tags**: Bandits, Off-policy / offline-to-online, Distribution shift
* **Source**: arXiv (academic preprint, May 11, 2026; v2 May 14, 2026)
* **The Core Concept**: Anchor-TS combines online posterior samples, hybrid-data samples, and online sample means through a *median*-based anchoring rule. Gracefully degrades when the offline-to-online distribution shift is large, but exploits offline data when shift is small. Directly addresses the marketplace problem of warm-starting a new bandit policy from logged data when both the policy and the marketplace conditions have moved since the logs were collected.

---

## Trust & Safety / Fairness in Hiring

### Characterizing AI-Assisted Bot Traffic in Darknet Data: Implications for ICS and IIoT Security
* **Document**: [arXiv preprint 2605.14209](https://arxiv.org/abs/2605.14209)
* **Tags**: Trust & safety, Bot detection, Adversarial traffic
* **Source**: arXiv (academic preprint, May 14, 2026)
* **The Core Concept**: Analyzes ~192M darknet packets (2021–2025) from the Merit ORION Network Telescope. Modern AI-assisted bots use intentional micro-pacing (1–100ms) to deliberately mask their volume; 97.47% of modern bot traffic now bypasses standard volumetric thresholds, and tightening sensitivity produces a 68% false-positive rate. The paper's framing is ICS/IIoT, but the *traffic-shape evolution* finding generalizes: any jobboard fighting AI-assisted scraping, fake-applicant bots, or LLM-generated apply storms should assume volume-based defenses are increasingly blind, and that the false-positive cost of tightening them is now severe.
