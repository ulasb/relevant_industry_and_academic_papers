# Job/Resume NLP & Taxonomy

## Why this topic matters
Job and resume text is uniquely messy: free-form titles, implicit skills, education and work-history conventions that vary across regions, multilingual content. Mapping this content to canonical taxonomies (O*NET, ESCO, SOC) and extracting structured signals (skills, seniority, location, comp) underpins almost every downstream system on a jobboard — search, matching, deduping, quality scoring, fraud detection. Methods range from classical NER and ontology alignment to weak-supervision pipelines and domain-pretrained / fine-tuned LMs.

## Tracked sources
- arxiv: cs.CL, cs.IR (filter for HR / employment / occupation / skills)
- ACL, EMNLP, NAACL
- Industry blogs: LinkedIn Engineering (skills graph posts), Indeed Engineering, Lightcast (formerly Burning Glass), Eightfold AI, Workday research
- Standards bodies: O*NET / ETA, ESCO (EU), SOC codes
- Hugging Face hub for HR-domain LMs

## Search query templates
- "skills extraction" OR "skill extraction" resume
- "job title normalization" OR "occupation classification"
- "named entity recognition" resume
- "ontology alignment" jobs OR skills
- "ESCO" OR "O*NET" mapping
- "job description" quality OR classification
- "resume parsing" OR "CV parsing"

## Relevance heuristics
- HIGH: production resume/job parsing systems, skills ontology work that could plug into existing taxonomies, weak-supervision / label-efficient methods (HR data is hard to label), multilingual
- MEDIUM: domain-pretrained LMs for HR text, entity linking methods
- LOW: generic NER without domain transfer, single-language tools far from the jobboard scope
