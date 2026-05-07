# Paper Digest — 2026-05-07

Search window: 2026-04-30 → 2026-05-07 (web search date filtering is loose; included items are recent but a subset are older foundational works retained for reference).

---

## Recommender Systems

### Engineering the next generation of LinkedIn's Feed
* **Document**: [LinkedIn Engineering blog post](https://www.linkedin.com/blog/engineering/feed/engineering-the-next-generation-of-linkedins-feed)
* **Tags**: Recommender systems, LLMs & Agents, Embeddings
* **Source**: LinkedIn Engineering (industry blog, March 2026)
* **The Core Concept**: Complete rebuild of LinkedIn's Feed recommendation system: a unified LLM-based dual encoder for retrieval plus a transformer-based Generative Recommender (GR) for ranking, replacing the previous multi-source retrieval architecture. User profile + engagement history is converted into a prompt and embedded; posts are encoded in the same space; nearest-content search runs exhaustively on GPU. Directly relevant for any jobboard considering LLM-driven retrieval/ranking architectures, and a useful counterpoint to the two-tower default.

### Meta Adaptive Ranking Model: Bending the Inference Scaling Curve to Serve LLM-Scale Models for Ads
* **Document**: [Engineering at Meta blog post](https://engineering.fb.com/2026/03/31/ml-applications/meta-adaptive-ranking-model-bending-the-inference-scaling-curve-to-serve-llm-scale-models-for-ads/)
* **Tags**: Recommender systems, Marketplaces & Auctions, Production ML
* **Source**: Meta Engineering (industry blog, March 2026)
* **The Core Concept**: How Meta scales LLM-scale ads ranking models in production while keeping inference cost manageable. Highly relevant for anyone running large ranking models at scale on a paid-listing/CPC marketplace where every millisecond and dollar of inference cost compounds.

### RankGR: Rank-Enhanced Generative Retrieval with Listwise Direct Preference Optimization in Recommendation
* **Document**: [arXiv preprint 2602.08575](https://arxiv.org/html/2602.08575)
* **Tags**: Recommender systems, Retrieval, LLMs
* **Source**: arXiv (academic preprint, February 2026)
* **The Core Concept**: Combines generative retrieval with listwise Direct Preference Optimization for ranking quality. Addresses the standard retrieval→ranking pipeline at billion-item scale. Worth reading if generative retrieval is on the roadmap.

### A Learnable Fully Interacted Two-Tower Model for Pre-Ranking System
* **Document**: [arXiv preprint 2509.12948](https://arxiv.org/html/2509.12948v1)
* **Tags**: Recommender systems, Two-tower
* **Source**: arXiv (academic preprint, September 2025)
* **The Core Concept**: Adds learnable cross-tower interactions to two-tower models without breaking decoupled inference, intended for pre-ranking. A pragmatic step between pure two-tower (efficient but limited) and full cross-attention (expensive).

### ContextGNN: Beyond Two-Tower Recommendation Systems
* **Document**: [arXiv preprint 2411.19513](https://arxiv.org/abs/2411.19513)
* **Tags**: Recommender systems, Graph neural networks
* **Source**: arXiv (academic preprint, November 2024)
* **The Core Concept**: Argues that two-tower architectures fail to capture pair-wise signals that matter for fine-grained matching. Proposes a GNN-based alternative. Useful contrarian read when evaluating two-tower limitations on a jobboard's matching problem.

### Suggest, Complement, Inspire: Story of Two Tower Recommendations at Allegro.com
* **Document**: [arXiv preprint 2508.03702](https://arxiv.org/html/2508.03702v1)
* **Tags**: Recommender systems, Marketplaces, Production case study
* **Source**: arXiv (academic preprint, August 2025)
* **The Core Concept**: Production two-tower at Allegro (Polish e-commerce marketplace), with product representation built from textual + structured attributes and ANN retrieval. Useful marketplace-side case study for how to deploy two-tower against heterogeneous catalogs.

---

## Search & Information Retrieval

### LACONIC: Dense-Level Effectiveness for Scalable Sparse Retrieval via a Two-Phase Training Curriculum
* **Document**: [arXiv preprint 2601.01684](https://arxiv.org/html/2601.01684v1)
* **Tags**: Search & IR, Learned sparse retrieval, LLMs
* **Source**: arXiv (academic preprint, January 2026)
* **The Core Concept**: A family of learned sparse retrievers (1B/3B/8B) built on Llama3 with a two-phase curriculum: weakly-supervised pre-finetuning to adapt causal LLMs for bidirectional context, then high-signal finetuning with curated hard negatives. The 8B variant hits 60.2 nDCG on MTEB Retrieval (state-of-the-art for sparse). Suggests sparse retrieval can stay competitive at LLM scale, which is interesting for systems that prefer interpretable inverted-index serving.

### SPLADE-Code: Learned Sparse Retrieval for Code
* **Document**: [arXiv preprint 2603.22008](https://arxiv.org/abs/2603.22008)
* **Tags**: Search & IR, Learned sparse retrieval, Domain specialization
* **Source**: arXiv (academic preprint, March 2026)
* **The Core Concept**: Code-specific learned sparse retrievers (600M-8B). Code is the test domain but the training methodology (specialization at scale) transfers cleanly to any specialized text domain — including jobs and resumes.

### Sparse and Dense Retrievers Learn Better Together: Joint Sparse-Dense Optimization for Text-Image Retrieval
* **Document**: [arXiv preprint 2508.16707](https://arxiv.org/abs/2508.16707)
* **Tags**: Search & IR, Hybrid retrieval, Multi-modal
* **Source**: arXiv (academic preprint, August 2025)
* **The Core Concept**: Joint optimization of dense and sparse retrievers (instead of training separately and combining at inference time). Relevant for any team running a hybrid retrieval stack and wondering whether to co-train.

---

## Embeddings & Representation Learning

### Filtered Approximate Nearest Neighbor Search in Vector Databases: System Design and Performance Analysis
* **Document**: [arXiv preprint 2602.11443](https://arxiv.org/abs/2602.11443)
* **Tags**: Embeddings, ANN, Vector databases
* **Source**: arXiv (academic preprint, February 2026)
* **The Core Concept**: System-level analysis of filtered ANN (FANNS) in production vector databases — how filtering interacts with index structure and query performance. Directly relevant for any vector-search infrastructure decision where filters (e.g., location, recency, employer) are applied alongside semantic search.

### KScaNN: Scalable Approximate Nearest Neighbor Search on Kunpeng
* **Document**: [arXiv preprint 2511.03298](https://arxiv.org/abs/2511.03298)
* **Tags**: Embeddings, ANN, Hardware
* **Source**: arXiv (academic preprint, November 2025)
* **The Core Concept**: New ANN system targeting non-x86 (ARM-based Kunpeng) architecture. Useful comparison point if any infrastructure is on ARM, and a general data point on how hardware-specialized ANN compares to ScaNN/HNSW.

### On the Similarities of Embeddings in Contrastive Learning
* **Document**: [arXiv preprint 2506.09781](https://arxiv.org/html/2506.09781v1)
* **Tags**: Embeddings, Contrastive learning, Theory
* **Source**: arXiv (academic preprint, June 2025)
* **The Core Concept**: Theoretical analysis: in full-batch contrastive learning, perfect alignment of positive pairs is unattainable when negative-pair similarities fall below a threshold; in mini-batch, smaller batches induce stronger separation. Practical implication: batch-size choices in contrastive training have non-obvious effects on representation geometry.

### Vector Search with FAISS: Approximate Nearest Neighbor (ANN) Explained
* **Document**: [PyImageSearch tutorial](https://pyimagesearch.com/2026/02/16/vector-search-with-faiss-approximate-nearest-neighbor-ann-explained/)
* **Tags**: Embeddings, ANN, Tutorial
* **Source**: PyImageSearch (industry tutorial, February 2026)
* **The Core Concept**: Implementation-flavored walkthrough of FAISS ANN. Useful onboarding read for engineers ramping on vector search infra.

---

## LLMs & Agents (for Recruitment / Jobboards)

### AI Hiring with LLMs: A Context-Aware and Explainable Multi-Agent Framework for Resume Screening
* **Document**: [arXiv preprint 2504.02870](https://arxiv.org/abs/2504.02870)
* **Tags**: LLMs & Agents, Resume parsing, Recruitment, Multi-agent
* **Source**: arXiv / CVPR 2025 Workshop (academic preprint, April 2025)
* **The Core Concept**: A four-agent framework (extractor, evaluator, summarizer, score-formatter) with RAG over external knowledge sources (industry expertise, certifications, university rankings). Directly transferable architecture pattern for any LLM-based screening or matching pipeline that needs to incorporate domain priors at evaluation time.

### Zero-Shot Resume-Job Matching with LLMs via Structured Prompting and Semantic Embeddings
* **Document**: [MDPI Electronics article](https://www.mdpi.com/2079-9292/14/24/4960)
* **Tags**: LLMs & Agents, Resume parsing, Job matching
* **Source**: MDPI Electronics (academic, December 2025)
* **The Core Concept**: Chain-of-thought prompted Mistral hitting 87% matching accuracy zero-shot, no fine-tuning. Useful as a cheap baseline before any custom-model investment, and a reference point for what off-the-shelf LLMs deliver on the matching task.

### Application of LLM Agents in Recruitment: A Novel Framework for Resume Screening
* **Document**: [arXiv preprint 2401.08315](https://arxiv.org/abs/2401.08315)
* **Tags**: LLMs & Agents, Resume parsing, Recruitment
* **Source**: arXiv (academic preprint, January 2024)
* **The Core Concept**: Foundational LLM-agent framework for resume screening, claimed 11x faster than manual. Older but worth reading as the prior-art baseline against which 2026 multi-agent frameworks are improving.

---

## Online Marketplaces, Auctions & Bidding

### Double Auctions with Two-sided Bandit Feedback
* **Document**: [OpenReview / NeurIPS 2023](https://openreview.net/forum?id=2nTpPxJ5Bs&noteId=oOZX418zWb)
* **Tags**: Marketplaces & Auctions, Bandits
* **Source**: NeurIPS 2023 (academic, frequently cited in 2026 work)
* **The Core Concept**: Decentralized learning algorithms for double auctions where both buyers and sellers have unknown valuations and learn through repeated interactions. Foundational reference for any value-learning bidding system in a two-sided marketplace.

### Reducing Marketplace Interference Bias via Shadow Prices
* **Document**: [Management Science article](https://doi.org/10.1287/mnsc.2022.01881)
* **Tags**: Marketplaces & Auctions, Causal inference, Experimentation
* **Source**: Management Science (academic journal, recent)
* **The Core Concept**: Method for cleaner causal estimates in marketplace experiments by adjusting outcomes via shadow prices. Bridges marketplace design and experimentation — relevant when running supply-side or demand-side A/B tests and worried about cross-side spillover.

---

## Jobboards, HR Tech & Two-Sided Marketplaces

### Building a Large-Scale Recommendation System: People You May Know
* **Document**: [LinkedIn Engineering blog post](https://www.linkedin.com/blog/engineering/recommendations/building-a-large-scale-recommendation-system-people-you-may-know)
* **Tags**: Jobboards & HR Tech, Recommender systems, Production architecture
* **Source**: LinkedIn Engineering (industry blog, recent)
* **The Core Concept**: PYMK rec system architecture — the canonical "match users with structure on both sides" case study from a direct industry peer. Worth reading not for the algorithms (which are well-known) but for the production-engineering decisions and the way LinkedIn frames their problem.

### AI Behind LinkedIn Recruiter Search and Recommendation Systems
* **Document**: [LinkedIn Engineering blog post](https://www.linkedin.com/blog/engineering/recommendations/ai-behind-linkedin-recruiter-search-and-recommendation-systems)
* **Tags**: Jobboards & HR Tech, Search & IR, Recommender systems
* **Source**: LinkedIn Engineering (industry blog, recent)
* **The Core Concept**: How LinkedIn ranks candidates for recruiters. Direct competitive intelligence for any recruitment platform doing employer-side search/recommendation.

### Reverse-Engineering LinkedIn's 360Brew From Their Engineering Blog
* **Document**: [DEV Community post](https://dev.to/nicolasai/reverse-engineering-linkedins-360brew-from-their-engineering-blog-4jm6)
* **Tags**: Jobboards & HR Tech, LLMs & Agents, Recommender systems
* **Source**: DEV Community / Nicolas AI (third-party analysis, recent)
* **The Core Concept**: Third-party deep-dive synthesizing what's public about LinkedIn's 360Brew unified retrieval/ranking system. Useful as a digested overview if you don't have time to read all the underlying LinkedIn posts.

---

## Causal Inference & Online Experimentation

### The Interplay Between Design and Analysis of Experiments in Complex Environments: Interference and Randomization Tests
* **Document**: [Harvard Data Science Review article](https://hdsr.mitpress.mit.edu/pub/ov1ilnnf/release/1)
* **Tags**: Causal inference, Experimentation, Marketplace
* **Source**: Harvard Data Science Review (academic, Winter 2026)
* **The Core Concept**: Extends randomization-based tests to experiments where time periods serve as experimental units, addressing temporal interference (carryover, anticipation) common in switchback, staggered rollouts, and crossover designs. Directly applicable for any marketplace experiment that violates SUTVA temporally.

### Randomization Tests in Switchback Experiments
* **Document**: [arXiv preprint 2602.23257](https://arxiv.org/html/2602.23257v1)
* **Tags**: Causal inference, Experimentation, Switchback
* **Source**: arXiv (academic preprint, February 2026)
* **The Core Concept**: Randomization-test framework producing finite-sample valid, distribution-free p-values for switchback experiments — without parametric assumptions on the outcome process. Handles serial dependence, seasonality, and heavy-tailed shocks. Practical recipe for marketplace teams that want defensible inference under temporal interference.

### Clustered Switchback Experiments: Near-Optimal Rates Under Spatiotemporal Interference
* **Document**: [arXiv preprint 2312.15574](https://arxiv.org/html/2312.15574v2)
* **Tags**: Causal inference, Experimentation, Switchback
* **Source**: arXiv (academic preprint, recent v2)
* **The Core Concept**: Switchback design when interference operates on both space and time (e.g., metro-area marketplaces). Near-optimal rates with practical clustering schemes. A natural complement to the randomization-test paper above.

---

## LTV, Uplift & Cohort Modeling

### A Large Scale Heterogeneous Treatment Effect Estimation Framework and Its Applications of Users' Journey at Snap
* **Document**: [arXiv preprint 2512.03060](https://arxiv.org/html/2512.03060)
* **Tags**: LTV & Uplift, Causal inference, Production case study
* **Source**: arXiv (academic preprint, December 2025)
* **The Core Concept**: HTE framework deployed at Snap on user-journey data — production-flavored case study of moving from correlation-based to causal/incremental labels for measuring user value. Strong reference for any team building heterogeneous treatment-effect models on top of large logged interaction data.

### Uplift Modeling with Continuous Treatments: A Predict-Then-Optimize Approach
* **Document**: [arXiv preprint 2412.09232](https://arxiv.org/html/2412.09232v1)
* **Tags**: LTV & Uplift, Bidding, Continuous treatments
* **Source**: arXiv (academic preprint, December 2024)
* **The Core Concept**: Uplift typically assumes binary treatments (treat/don't-treat). Real settings — bid amounts, discount sizes, ad spend — are continuous. This paper provides a predict-then-optimize framework for continuous-treatment uplift. Directly applicable to value-based bidding systems.

---

## Job/Resume NLP & Taxonomy

### Job Skill Extraction via LLM-Centric Multi-Module Framework (SRICL)
* **Document**: [arXiv preprint 2604.21525](https://arxiv.org/abs/2604.21525)
* **Tags**: NLP & Taxonomy, Skills extraction, LLMs
* **Source**: arXiv (academic preprint, ~April 2026)
* **The Core Concept**: Combines semantic retrieval, in-context learning, and supervised fine-tuning with a deterministic verifier. Specifically addresses the production pain points: malformed spans, boundary drift, and hallucinated skills. The verifier-in-loop pattern is the most actionable piece.

### Skill-LLM: Repurposing General-Purpose LLMs for Skill Extraction
* **Document**: [arXiv preprint 2410.12052](https://arxiv.org/html/2410.12052v1)
* **Tags**: NLP & Taxonomy, Skills extraction, LLMs
* **Source**: arXiv (academic preprint, October 2024)
* **The Core Concept**: NER-style fine-tuning of general LLMs for skills extraction, beating both traditional supervised methods and zero/few-shot LLM baselines. Useful as the prior-art baseline against which SRICL above is measured.

### Rethinking Skill Extraction in the Job Market Domain using Large Language Models
* **Document**: [arXiv preprint 2402.03832](https://arxiv.org/abs/2402.03832)
* **Tags**: NLP & Taxonomy, Skills extraction, LLMs
* **Source**: arXiv (academic preprint, February 2024)
* **The Core Concept**: Foundational comparison study of LLM approaches to skills extraction in the job-market domain. Sets the framing that more recent papers (Skill-LLM, SRICL) build on.

---

## Contextual Bandits & Online Learning

### Group-Sensitive Offline Contextual Bandits
* **Document**: [arXiv preprint 2510.27123](https://arxiv.org/abs/2510.27123)
* **Tags**: Bandits, Off-policy, Fairness
* **Source**: arXiv (academic preprint, updated January 2026)
* **The Core Concept**: Adds group-wise reward disparity constraints to off-policy gradient optimization, with doubly robust estimators. Strong overlap with the fairness/regulatory topic — practical method for ensuring an off-policy-trained policy doesn't worsen group disparities, which directly maps to AEDT-style audit requirements.

### Calibrated Recommendations with Contextual Bandits
* **Document**: [arXiv preprint 2509.05460](https://arxiv.org/html/2509.05460v1)
* **Tags**: Bandits, Off-policy, Calibration
* **Source**: arXiv (academic preprint, September 2025)
* **The Core Concept**: Off-policy evaluation for calibrated recommendations using IPW with probability-ratio capping to control variance. Practical recipe when you want to evaluate "what would happen if we changed the policy" without running another A/B test.

### Offline Contextual Bandit with Counterfactual Sample Identification (CSI)
* **Document**: [arXiv preprint 2509.10520](https://arxiv.org/html/2509.10520)
* **Tags**: Bandits, Off-policy, Estimators
* **Source**: arXiv (academic preprint, September 2025)
* **The Core Concept**: New off-policy estimator midway between IPS and Direct Method — instead of predicting reward, learns to recognize which action led to a successful binary outcome by comparing to a counterfactual sampled from the logging policy. Useful when reward is binary and noisy.

---

## Trust & Safety / Fairness in Hiring

### EU AI Act AI Hiring Tools Compliance: 6 Critical Steps (2026)
* **Document**: [Intervuebox guide](https://www.intervuebox.ai/eu-ai-act-ai-hiring-tools-compliance-2026/)
* **Tags**: Trust & Safety, Fairness, Regulation
* **Source**: Intervuebox (industry guide, 2026)
* **The Core Concept**: Practical operational guide to the high-risk AI obligations under the EU AI Act, going live August 2, 2026. Covers technical documentation, human oversight mechanisms, transparency disclosures, and the €15M / 3% global turnover penalty exposure. Required reading for any platform that touches EU candidates.

### NYC Local Law 144 Compliance Guide 2026
* **Document**: [Warden AI compliance guide](https://www.warden-ai.com/resources/hr-tech-compliance-nyc-local-law-144)
* **Tags**: Trust & Safety, Fairness, Regulation
* **Source**: Warden AI (industry guide, 2026)
* **The Core Concept**: Up-to-date AEDT (Automated Employment Decision Tool) bias audit requirements: independent annual audits, public disclosure of audit results, coverage of race/ethnicity/sex categories, candidate notice requirements. Maps the practical operational steps for compliance.

### The Fair Game: Auditing & Debiasing AI Algorithms Over Time
* **Document**: [arXiv preprint 2508.06443](https://arxiv.org/html/2508.06443)
* **Tags**: Trust & Safety, Fairness, Auditing
* **Source**: arXiv (academic preprint, August 2025)
* **The Core Concept**: RL-based loop where an Auditor agent estimates a bias report and a Debiaser agent rectifies the underlying ML model in response. Treats long-term fairness as a game-theoretic problem instead of a one-shot audit. Interesting frame for compliance regimes that mandate ongoing audits.

### AI Hiring Bias Audit, Apr 19 2026 Digest
* **Document**: [Asanify digest](https://asanify.com/blog/news/ai-hiring-bias-audit-april-19-2026/)
* **Tags**: Trust & Safety, Fairness, Industry digest
* **Source**: Asanify (industry blog, April 2026)
* **The Core Concept**: Industry roundup on recent AI hiring audit findings and policy movement. Quick-read context on where the regulatory and audit-practice landscape is moving in mid-2026.

### Fairness in AI-Driven Recruitment: Challenges, Metrics, Methods, and Future Directions
* **Document**: [arXiv preprint 2405.19699](https://arxiv.org/html/2405.19699v3)
* **Tags**: Trust & Safety, Fairness, Survey
* **Source**: arXiv (academic survey, recent v3)
* **The Core Concept**: Comprehensive survey of fairness metrics and bias mitigation methods specifically for AI-driven recruitment. Useful as a reference document mapping the methods landscape (demographic parity, equalized odds, individual fairness, etc.) onto the recruitment context.
