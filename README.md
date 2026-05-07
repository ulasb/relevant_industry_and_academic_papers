# Relevant Industry & Academic Papers

A curated, topic-organized digest of industry blog posts and academic papers worth reading to keep up with the cutting edge — scoped to topics relevant to a recruitment / two-sided jobboard marketplace. Run ad-hoc, as often or as rarely as you like.

## How it works

A custom skill (`paper-watch`, defined in [`.claude/skills/paper-watch/SKILL.md`](./.claude/skills/paper-watch/SKILL.md)) does the heavy lifting:

1. Run `/paper-watch` from inside this repo.
2. The skill searches the web for recent content across the **11 topics** below (default window: last 7 days, customizable).
3. It presents up to 10 candidates per topic with a relevance pitch.
4. You prune interactively to a top set per topic.
5. The skill writes a digest to `runs/<today>/contents.md` and appends accepted items to per-topic ledgers in `findings/`.
6. You review the diff and push.

Manually triggered, not scheduled — so accept/reject can happen interactively.

## Topics

Each topic file (in `topics/`) has: why the topic matters, tracked sources, search query templates, and relevance heuristics. The skill reads these to drive its searches.

| # | Topic | File |
|---|---|---|
| 1 | Recommender Systems | [topics/01-recommender-systems.md](topics/01-recommender-systems.md) |
| 2 | Search & Information Retrieval | [topics/02-search-and-ir.md](topics/02-search-and-ir.md) |
| 3 | Embeddings & Representation Learning | [topics/03-embeddings-and-representation-learning.md](topics/03-embeddings-and-representation-learning.md) |
| 4 | LLMs & Agents (for Recruitment / Jobboards) | [topics/04-llms-and-agents-for-recruitment.md](topics/04-llms-and-agents-for-recruitment.md) |
| 5 | Online Marketplaces, Auctions & Bidding | [topics/05-marketplaces-auctions-bidding.md](topics/05-marketplaces-auctions-bidding.md) |
| 6 | Jobboards, HR Tech & Two-Sided Marketplaces | [topics/06-jobboards-and-hr-tech.md](topics/06-jobboards-and-hr-tech.md) |
| 7 | Causal Inference & Online Experimentation | [topics/07-causal-inference-and-experimentation.md](topics/07-causal-inference-and-experimentation.md) |
| 8 | LTV, Uplift & Cohort Modeling | [topics/08-ltv-uplift-cohort-modeling.md](topics/08-ltv-uplift-cohort-modeling.md) |
| 9 | Job/Resume NLP & Taxonomy | [topics/09-job-resume-nlp-taxonomy.md](topics/09-job-resume-nlp-taxonomy.md) |
| 10 | Contextual Bandits & Online Learning | [topics/10-bandits-and-online-learning.md](topics/10-bandits-and-online-learning.md) |
| 11 | Trust & Safety / Fairness in Hiring | [topics/11-trust-safety-fairness.md](topics/11-trust-safety-fairness.md) |

To add, edit, or remove a topic: edit `topics/` directly. The skill picks up changes on next run.

## Repo layout

```
.
├── README.md                       This file
├── .claude/skills/paper-watch/
│   └── SKILL.md                    The paper-watch skill (project-scoped)
├── topics/                         Topic definitions (relevance, search strategy, sources)
├── runs/                           One folder per run (date of the run)
│   └── YYYY-MM-DD/
│       ├── contents.md             The accepted picks, organized by topic
│       └── rejected.md             What was surfaced but rejected (for dedupe)
├── findings/                       One file per topic — chronological ledger of every
│   ├── 01-recommender-systems.md     accepted resource ever surfaced for that topic.
│   ├── 02-search-and-ir.md           Use this to scan a topic's full history quickly.
│   └── ...
├── learnings/                      Post-read notes & takeaways
│   ├── README.md                   Format guide
│   └── <paper-slug>.md             One per paper you took notes on
└── seen.json                       URL dedupe across runs
```

## Adding a learning

After reading a paper, capture takeaways in `learnings/<paper-slug>.md`. See [learnings/README.md](learnings/README.md) for the format.

## Using the skill

The skill is project-scoped (lives at `.claude/skills/paper-watch/SKILL.md`), so it's auto-discovered when Claude Code runs from inside this repo. Just `cd` here and invoke `/paper-watch`.
