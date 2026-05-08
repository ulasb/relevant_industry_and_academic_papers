# Search & Information Retrieval

## Why this topic matters
Search is the primary discovery surface on most jobboards. Queries are short, noisy, and underspecified (job titles vary wildly, locations have synonyms, skills are implicit). Ranking has to satisfy both relevance for the user and economic objectives for the platform. The focus of this topic is **semantic search and embedding-based retrieval** — i.e., systems that learn shared representations of queries and items so that similarity in vector space approximates relevance — along with the surrounding ranking, query understanding, and hybrid sparse-dense techniques that production search stacks rely on.

## In scope
- Dense retrieval (bi-encoders, dual encoders, two-tower retrieval)
- Learned sparse retrieval (SPLADE-style methods)
- Hybrid sparse + dense retrieval
- Embedding-based / semantic search architectures
- Neural rankers and learning-to-rank
- Query understanding (synonyms, intent, geo, taxonomy mapping)
- Calibration of search rankers
- ANN-index / vector-search infrastructure (where the focus is on retrieval quality / latency rather than the index itself — pure index work belongs in topic 03)

## Out of scope (covered by other topics)
- LLM agents that perform multi-turn tool-using search → topic 04 (LLMs & Agents)
- LLMs as the primary retrieval engine via prompting / generative retrieval without a learned embedding component → topic 04
- Pure embedding model training without a search application → topic 03 (Embeddings)

## Tracked sources
- arxiv: cs.IR
- SIGIR, CIKM, WWW conference proceedings
- TREC tracks
- Industry blogs: LinkedIn Engineering, Indeed Engineering, Glassdoor Engineering, Pinterest Engineering, Elastic blog, Vespa blog, Weaviate / Pinecone / Qdrant blogs, Algolia blog
- Google Research, Microsoft Research, Meta AI

## Search query templates
- "dense retrieval" OR "learned sparse retrieval" site:arxiv.org
- "semantic search" OR "embedding search" production
- "two-tower" retrieval OR "dual encoder" retrieval
- "query understanding" search
- "neural ranking" OR "learning to rank"
- "hybrid retrieval" dense sparse
- "geo search" OR "spatial search" relevance
- "job search" relevance ranking

## Relevance heuristics
- HIGH: production retrieval architectures (dense / sparse / hybrid), ranker calibration, query understanding for noisy queries (jobboards have lots of these), hybrid retrieval lessons, embedding-based search quality work
- MEDIUM: novel loss functions / negative mining, evaluation methodology
- LOW: pure benchmark chasing without architectural lessons; LLM-as-search-engine papers (those belong in topic 04)
