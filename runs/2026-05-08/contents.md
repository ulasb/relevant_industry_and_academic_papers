# Paper Digest — 2026-05-08

Search window: 2026-05-01 → 2026-05-08. Thin run — last digest was 2026-05-07 so most of the window was already deduped against `seen.json`.

---

## Recommender Systems

### Recommender Systems as Control Systems
* **Document**: [arXiv preprint 2605.01503](https://arxiv.org/abs/2605.01503)
* **Tags**: Recommender systems, Control theory, Fairness
* **Source**: arXiv (academic preprint, ~May 1, 2026)
* **The Core Concept**: Proposes a control-theoretic interpretation of recommender systems and analyzes how fairness interventions shape long-term system behavior. Useful framing for any team thinking about how matching decisions feed back into supply-demand dynamics over time, and a different lens on the long-term-effect questions usually approached via causal inference.

### Rethinking Recommendation Paradigms: From Pipelines to Agentic Recommender Systems (AgenticRS)
* **Document**: [arXiv preprint 2603.26100](https://arxiv.org/html/2603.26100v1)
* **Tags**: Recommender systems, LLMs & Agents, Architecture
* **Source**: arXiv (academic preprint, March 2026)
* **The Core Concept**: Argues recommender systems should be reframed as multi-agent decision systems rather than static model pipelines. Proposes a conceptual framework for moving from manually tuned architectures toward self-evolving ecosystems. Companion piece to the RSTA preprint from the 2026-04-24 digest — together they sketch where "agentic recommender systems" is heading conceptually.

### Deep Research for Recommender Systems
* **Document**: [arXiv preprint 2603.07605](https://arxiv.org/html/2603.07605)
* **Tags**: Recommender systems, LLMs & Agents
* **Source**: arXiv (academic preprint, March 2026)
* **The Core Concept**: Examines the prevailing recsys interaction paradigm focused on item exposure, and argues current systems function more as tools than as assistants. Proposes a more research-assistant-like paradigm. Worth reading alongside the AgenticRS paper for a fuller picture of the LLM-era recsys reframe.

---

## Causal Inference & Online Experimentation

### InferenceEvolve: Towards Automated Causal Effect Estimators through Self-Evolving AI
* **Document**: [arXiv preprint 2604.04274](https://arxiv.org/abs/2604.04274)
* **Tags**: Causal inference, LLMs & Agents, AutoML
* **Source**: arXiv (academic preprint, April 2026)
* **The Core Concept**: An evolutionary framework that uses LLMs to discover and iteratively refine causal effect estimators automatically. Interesting as a methodological direction — could lower the bar for teams that need treatment-effect estimates but don't have a dedicated causal-inference person to hand-pick estimators.

---

## Job/Resume NLP & Taxonomy

### Standard Occupation Classifier — A Natural Language Processing Approach
* **Document**: [arXiv preprint 2511.23057](https://arxiv.org/html/2511.23057v1)
* **Tags**: NLP & Taxonomy, Occupation classification, SOC
* **Source**: arXiv (academic preprint, November 2025)
* **The Core Concept**: NLP approach to mapping free-text job content to Standard Occupational Classification (SOC) codes. Directly on-point for any taxonomy-mapping work — SOC is one of the canonical occupation taxonomies and a frequent normalization target for jobboards. Older paper but missed in prior runs.

---

## Contextual Bandits & Online Learning

### Bandit Learning in General Open Multi-agent Systems
* **Document**: [arXiv preprint 2605.06202](https://arxiv.org/abs/2605.06202)
* **Tags**: Bandits, Multi-agent, Marketplace dynamics
* **Source**: arXiv (academic preprint, May 2026)
* **The Core Concept**: Bandits in open systems where agents arrive and depart over time, with heterogeneous rewards and general entry/exit dynamics. Marketplace-flavored: directly applicable to environments where the population of users or items is non-stationary, which describes most jobboard settings (job postings come and go, jobseekers arrive and disengage).

### Vanishing L2 Regularization for the Softmax Multi-Armed Bandit
* **Document**: [arXiv preprint 2605.03752](https://arxiv.org/html/2605.03752)
* **Tags**: Bandits, Theory
* **Source**: arXiv (academic preprint, May 2026)
* **The Core Concept**: Theoretical / algorithmic improvement to the softmax MAB. Smaller-bore than the open multi-agent paper but worth the tag for anyone running softmax-style action selection in production.

---

## Trust & Safety / Fairness in Hiring

### Algorithmic Bias Audit Compliance: Navigating the 2026 Frontier
* **Document**: [Bochner PLLC publication](https://www.bochner.law/news/publications/2026-04-30-algorithmic-bias-audit-compliance-navigating-the-2026-frontier)
* **Tags**: Trust & Safety, Fairness, Regulation, Legal
* **Source**: Bochner PLLC (law firm publication, April 30, 2026)
* **The Core Concept**: Legal-perspective compliance guide for the 2026 wave of AEDT and AI-Act-style regulations. Complements the regulatory tracking from the 2026-05-07 digest with a legal-counsel framing — useful for anyone needing to translate regulatory text into concrete operational requirements.

### AI Bias in Job Search Apps: Exposing Algorithmic Discrimination and Proven Fixes for 2026 Hiring
* **Document**: [Best Job Search Apps article](https://bestjobsearchapps.com/articles/en/ai-bias-in-job-search-apps-exposing-algorithmic-discrimination-and-proven-fixes-for-2026-hiring)
* **Tags**: Trust & Safety, Fairness, Jobboards & HR Tech
* **Source**: Best Job Search Apps (industry analysis, 2026)
* **The Core Concept**: Jobboard-specific framing on bias in job search apps and proposed fixes. Direct industry coverage of the kind of consumer-facing bias discussion that drives regulatory attention.

### AI Hiring Discrimination Lawsuits: EEOC Enforcement 2026
* **Document**: [Reddock-Wright Law analysis](https://angelareddock-wright.com/ai-driven-hiring-bias-the-next-frontier-of-eeoc-enforcement/)
* **Tags**: Trust & Safety, Fairness, Legal
* **Source**: Reddock-Wright Law (law firm analysis, 2026)
* **The Core Concept**: EEOC enforcement-trend tracking on AI hiring discrimination. Useful for legal exposure analysis — what kinds of cases are actually being pursued and what theories of liability are gaining traction.

### Algorithmic Fairness Audits: A Step-by-Step Compliance Guide for 2026
* **Document**: [RiskTemplates compliance guide](https://risktemplate.com/blog/2026-04-01-algorithmic-fairness-audit-compliance-guide/)
* **Tags**: Trust & Safety, Fairness, Compliance playbook
* **Source**: RiskTemplates (industry guide, April 2026)
* **The Core Concept**: Operational audit playbook with step-by-step compliance procedures. Practical reading if you're standing up an internal audit process or reviewing a third-party auditor's methodology.
