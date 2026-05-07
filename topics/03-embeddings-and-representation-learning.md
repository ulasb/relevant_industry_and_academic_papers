# Embeddings & Representation Learning

## Why this topic matters
Embeddings are how modern recommendation, search, and matching systems compress messy real-world entities (jobs, jobseekers, queries) into a space where similarity is computable. Vector indexing infrastructure has changed rapidly in the last few years (IVF, HNSW, ScaNN, DiskANN, etc.), and the methods used to train embeddings (contrastive, self-supervised, multi-modal) are evolving fast. Strong representations enable everything downstream — better recall, better cold-start, better personalization.

## Tracked sources
- arxiv: cs.LG, cs.CL, cs.IR (filter for embedding / representation / contrastive)
- ICLR, NeurIPS, ICML
- Industry blogs: Pinterest Engineering, Spotify R&D, Airbnb Engineering, Meta AI, Google Research, Anthropic, Cohere, OpenAI, Hugging Face blog
- Vector DB blogs: Pinecone, Weaviate, Qdrant, Milvus

## Search query templates
- "contrastive learning" representation site:arxiv.org
- "self-supervised" embedding
- "two-tower" OR "dual encoder"
- "approximate nearest neighbor" production
- "vector index" OR "ANN index"
- "user representation" OR "user embedding"
- "job embedding" OR "resume embedding"

## Relevance heuristics
- HIGH: production-scale ANN systems, contrastive learning recipes that transfer to noisy text+behavior data, embedding compression / quantization, multi-modal fusion for marketplace items
- MEDIUM: novel pretraining objectives, transfer learning across marketplaces
- LOW: SOTA-chasing on academic benchmarks without a deployment lens
