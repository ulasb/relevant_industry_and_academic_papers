---
name: paper-watch
description: Curate top industry+academic papers/posts from a recent time window across 11 topics relevant to a recruitment / two-sided jobboard marketplace. Searches the web, presents up to 10 candidates per topic, lets the user prune, and writes a digest into the relevant_industry_and_academic_papers repo. Manually triggered, runs ad-hoc.
user_invocable: true
---

# paper-watch

Manually-triggered, ad-hoc digest builder. Run from inside the `relevant_industry_and_academic_papers` repo (or anywhere with `$REPO_ROOT` set to point to it).

## Inputs

Optional argument: a date range or single date. If omitted, defaults to the **last 7 days** ending today. The label used for the output folder is **today's date** (YYYY-MM-DD), regardless of what window was searched. Runs are ad-hoc — no enforced cadence.

Examples:
- `/paper-watch` — last 7 days
- `/paper-watch since=2026-04-30` — custom start
- `/paper-watch since=2026-04-30 until=2026-05-06` — custom range

## Setup steps (do these first, in order)

1. Resolve `$REPO_ROOT`:
   - If invoked from inside a git repo whose `origin` ends with `relevant_industry_and_academic_papers(.git)?`, use the repo root.
   - Else, prompt the user for the path.
2. Read `$REPO_ROOT/topics/*.md` — these define what to search for and the relevance lens.
3. Read `$REPO_ROOT/seen.json` — `{"surfaced_urls": [...]}` — used to dedupe across weeks.
4. Compute the search window (default: last 7 days).

## Search procedure (per topic)

For each `topics/NN-*.md` file:

1. Extract the **search query templates** and **tracked sources** sections.
2. Run **WebSearch** queries combining: the query templates × a recency hint (e.g., "last week", "May 2026", or explicit date filters where supported). Aim for 4-8 queries per topic to cast a reasonable net.
3. For each search result:
   - **Filter out** anything older than the search window (check publish dates in snippets/results)
   - **Filter out** URLs already in `seen.json["surfaced_urls"]`
   - **Filter out** generic landing pages, marketing fluff, vendor pitches with no technical substance
4. Use **WebFetch** to read the top candidates (~15-20 per topic) and confirm:
   - Publication date is within the window
   - Content is substantive (paper, technical post, well-researched analysis), not a press release or summary-of-summary
5. Score each candidate against the **relevance heuristics** in the topic file. Pick the top 10.

If a topic has fewer than 10 substantive results in the window, that's fine — surface what you have and note "only N results found this week."

## Cost / performance notes

- 11 topics × ~6 searches × 1 WebSearch call each ≈ ~66 searches. Plus ~15 WebFetch calls per topic for verification ≈ ~165 fetches. This will take 8-15 minutes.
- Run topics **sequentially**, not in parallel — parallel WebSearch calls share rate-limit budget poorly.
- If a search comes back empty or rate-limited, retry once with a relaxed query, then move on.
- **Cache nothing in memory across topics** beyond the running candidate list — keep state in `seen.json`.

## Interactive accept/reject

After all topics are searched, present results to the user **one topic at a time** in this format:

```
## Topic 1 / 11: Recommender Systems
Found 8 candidates (window: 2026-04-30 → 2026-05-07):

1. [Title]
   <one-paragraph relevance pitch tied to a recruitment-marketplace lens>
   Source: <publication> | Date: YYYY-MM-DD | URL

2. ...

Which to keep? Reply with numbers (e.g., "1,3,4,7" or "all" or "none").
```

Accept up to 5 per topic. If the user picks more, push back: "You picked N; the spec is up to 5. Drop M to keep top 5, or override?"

After all topics: confirm the final list with the user before writing.

## Output format

Write `$REPO_ROOT/<TODAY>/contents.md` with this structure:

```markdown
# Paper Digest — YYYY-MM-DD

Search window: YYYY-MM-DD → YYYY-MM-DD

---

## Recommender Systems

### <Title>
* **Document**: [<short link text>](<url>)
* **Tags**: Recommender systems, <other tags as relevant>
* **Source**: <publication name> (<academic|industry blog|preprint>, <pub date>)
* **The Core Concept**: <2-4 sentences. Tie it back to a recruitment-marketplace lens — what does this teach us about a problem in this space?>

### <next paper>
...

## Search & Information Retrieval
...
```

Only include topics where at least one paper was kept. Use the topic name (not the filename) as the section heading.

Also write `$REPO_ROOT/<TODAY>/rejected.md` with the same format but for items the user explicitly rejected. (Items merely not-picked-as-top-10 don't go here — only those the user saw and said no to.) This is dedupe data, not for review.

Append every URL that was *surfaced to the user* (whether kept or rejected) to `$REPO_ROOT/seen.json["surfaced_urls"]`. This prevents re-surfacing them in future weeks.

## Final step: hand off, don't push

After writing the files, print a summary like:

```
Wrote 2026-05-08/contents.md (N papers across M topics)
Wrote 2026-05-08/rejected.md (K items)
Updated seen.json (+P URLs)

Review with:
  cd $REPO_ROOT
  git diff
  git add 2026-05-08/ seen.json
  git commit -m "Digest: 2026-05-08"
  git push
```

**Do NOT auto-commit or auto-push.** The user owns the final review and push.

## Updating topics over time

If during a run you discover that a topic's search queries or sources are stale (consistently empty results, missing a key new venue, etc.), surface that to the user at the end:

> "Note: topic 04-llms-and-agents-for-recruitment had 0 hits from `site:medium.com indeed engineering` — consider removing that source. Want me to update the topic file?"

The user accepts or declines. If accepted, edit the topic file in the same run.

## Adding a learning later

The skill doesn't write learnings directly. After the user reads a paper, they add notes to `$REPO_ROOT/learnings/<paper-slug>.md` following the format in `learnings/README.md`. The skill should reference this in the final summary as a reminder.

## Failure modes

- **WebSearch returns nothing**: relax the query (drop site: filters), retry once, then mark the topic as "thin this week."
- **All results from one publication**: probably a search-engine bias — try different query templates from the topic file.
- **A "result" is paywalled or 403s**: skip it, log to rejected.md with reason.
- **User says "all results suck this week"**: respect it. Write an empty contents.md with a note explaining the window had thin pickings, still update seen.json.
