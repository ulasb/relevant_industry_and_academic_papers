# Paper Digest — 2026-04-24

---

## Recommender Systems

### Improving Embedding-Based Candidate Generation with Two-Tower Models & Self-Supervised Learning (SSL)
* **Document**: [Glassdoor Engineering blog post](https://medium.com/glassdoor-engineering/improving-embedding-based-candidate-generation-for-recommender-systems-with-a-two-tower-model-c222123beb7f)
* **Tags**: Recommender systems, Embeddings, Contrastive learning
* **Source**: Glassdoor Engineering Blog (industry blog, 2026)
* **The Core Concept**: Augments a standard Two-Tower recommendation model with Self-Supervised Learning and Mixed Negative Sampling. By masking parts of the user and post input vectors, the system learns the intrinsic structure of user behavior independent of straightforward clicks. Computes similarity via dot product $s(u, p) = \mathbf{u}^\top \mathbf{p}$ and applies a dual contrastive loss to pull positive augmented pairs closer while pushing apart random negatives. Directly applicable as an architecture pattern for any jobboard candidate-generation system.

### Recommender Systems Should Now Be Designed Towards Agents (RSTA)
* **Document**: [Preprints.org / arXiv preprint](https://www.preprints.org/manuscript/202604.0201)
* **Tags**: Recommender systems, LLMs & Agents
* **Source**: Preprints.org / arXiv (Chaoyue He et al., academic preprint, April 2026)
* **The Core Concept**: Proposes a paradigm shift from Recommender Systems Towards Humans (RSTH) to RSTA — systems where the immediate consumer is an acting AI agent. The ranked objects are not human-viewable UI items (like job cards) but actionable interventions, tool parameters, or workflow branches. Worth tracking as agentic flows enter recruitment surfaces.
