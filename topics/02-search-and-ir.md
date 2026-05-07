# Search & Information Retrieval

## Why this topic matters
Search is the primary discovery surface on most jobboards. Queries are short, noisy, and underspecified (job titles vary wildly, locations have synonyms, skills are implicit). Ranking has to satisfy both relevance for the user and economic objectives for the platform. Advances in dense retrieval, learned sparse retrieval, hybrid methods, query understanding, and neural rankers all matter — especially when they include calibration and production lessons rather than benchmark wins.

## Tracked sources
- arxiv: cs.IR
- SIGIR, CIKM, WWW conference proceedings
- TREC tracks
- Industry blogs: LinkedIn Engineering, Indeed Engineering, Glassdoor Engineering, Pinterest Engineering, Elastic blog, Vespa blog, Weaviate / Pinecone / Qdrant blogs, Algolia blog
- Google Research, Microsoft Research, Meta AI

## Search query templates
- "dense retrieval" OR "learned sparse retrieval" site:arxiv.org
- "query understanding" search
- "neural ranking" OR "learning to rank"
- "vector search" production
- "hybrid retrieval" dense sparse
- "geo search" OR "spatial search" relevance
- "job search" relevance ranking

## Relevance heuristics
- HIGH: production retrieval architectures, ranker calibration, query understanding for noisy queries (jobboards have lots of these), hybrid retrieval lessons
- MEDIUM: novel loss functions / negative mining, evaluation methodology
- LOW: pure benchmark chasing without architectural lessons
