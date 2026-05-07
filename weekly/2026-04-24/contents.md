## Tech Blog: Improving Embedding-Based Candidate Generation with Two-Tower Models & Self-Supervised Learning (SSL)
* **Document**: [Medium article](https://medium.com/glassdoor-engineering/improving-embedding-based-candidate-generation-for-recommender-systems-with-a-two-tower-model-c222123beb7f) 
* **Tags**: Recommender systems
* **Source**: Glassdoor Engineering Blog (Recent Update)
* **The Core Concept**: This post details augmenting a standard Two-Tower recommendation model with Self-Supervised Learning (SSL) and Mixed Negative Sampling. By masking parts of the user and post input vectors, the system learns the intrinsic structure of user behavior independent of straightforward clicks. The model computes similarity scores via a dot product $s(u, p) = \mathbf{u}^\top \mathbf{p}$ and applies a dual contrastive loss function to pull positive augmented pairs closer while pushing apart random negatives.

## Academic Preprint: Recommender Systems Should Now Be Designed Towards Agents (RSTA) ##
* **Document**: [Preprint article](https://www.preprints.org/manuscript/202604.0201)
* **Tags**: Recommender systems
* **Source**: Preprints.org / arXiv (Chaoyue He et al., April 2026)
* **The Core Concept**: The authors propose a paradigm shift from Recommender Systems Towards Humans (RSTH) to RSTA—systems where the immediate consumer is an acting AI agent. In this framework, the ranked objects are not human-viewable UI items (like job cards), but actionable interventions, tool parameters, or workflow branches.

