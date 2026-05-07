# Trust & Safety / Fairness in Hiring

## Why this topic matters
Hiring is regulated and high-stakes. A jobboard has to defend against bots and scrapers, detect and remove fraudulent listings and registrations, and (increasingly) demonstrate that its matching and ranking systems don't produce illegal disparate impact. Regulatory pressure is rising fast: NYC Local Law 144 (AEDT audits), EU AI Act high-risk classification of hiring AI, Illinois AI Video Interview Act, California ADMT, ongoing EEOC guidance. Adversarial scenarios are also evolving — resume-stuffing attacks against LLM-based filters, prompt injection in candidate-facing chat.

## Tracked sources
- arxiv: cs.CY, cs.LG, cs.CR, cs.HC
- FAccT, AIES, NeurIPS (fairness/safety tracks)
- Industry blogs: Google Responsible AI, Anthropic safety, Microsoft RAI, Meta Responsible AI, LinkedIn fairness, DeepMind safety
- Policy: EEOC, NYC DCWP, EU AI Act updates, California Civil Rights Department
- Bot/fraud: Cloudflare blog, Akamai security blog, Imperva, DataDome
- Academic: Solon Barocas, Arvind Narayanan, Moritz Hardt, Latanya Sweeney

## Search query templates
- "fairness" hiring OR recruitment site:arxiv.org
- "bias audit" AI hiring
- "adverse impact" machine learning
- "AEDT" OR "Local Law 144"
- "EU AI Act" hiring
- "prompt injection" OR "jailbreak" production
- "bot detection" OR "fraud detection" production
- "differential privacy" production

## Relevance heuristics
- HIGH: fairness methods with audit-trail outputs (regulatory-relevant), bot/fraud production systems, prompt-injection defenses for candidate-facing LLM features, regulatory updates that change legal exposure for hiring platforms
- MEDIUM: general adversarial-ML defenses, privacy-preserving ML for HR
- LOW: pure fairness theory without operationalization, security topics far from the web/ML attack surface
