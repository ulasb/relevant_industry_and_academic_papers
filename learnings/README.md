# Learnings

Post-read notes on papers/posts from the weekly digests. One file per paper (or per insight that crosses multiple papers).

## Filename convention

`<YYYY-MM-DD>--<short-slug>.md`

The date is when you wrote the note (not the paper's pub date). Slug is short and human-friendly: `2026-05-08--two-tower-ssl-glassdoor.md`.

## File template

```markdown
---
paper: <Title>
url: <link>
source: <publication>
pub_date: <YYYY-MM-DD or "unknown">
read_date: <YYYY-MM-DD>
topic: <topic name from topics/>
verdict: keep | drop | followup
---

## Summary
2-4 sentences. What's the idea? Skip the abstract — paraphrase what's actually new.

## Why it matters
Concrete: which open problem, which decision, which surface area. If you can't write this part, the paper probably isn't worth the slot.

## What we'd actually do with this
- Action 1 (if any): "Try X next quarter"
- Action 2: "Bring to <team> meeting"
- Or: "FYI only, no immediate action"

## Caveats / why we might NOT use it
What assumptions does it make that don't fit our context? What's the cost to implement? Where would it break?

## Related work / prior weeks
- Related: [link to prior digest entry or related paper]
```

## When to use which `verdict`

- **keep**: The idea is worth remembering, even if we don't act on it now.
- **drop**: Read it, didn't pan out — record so we don't re-read in 6 months.
- **followup**: Worth circulating, prototyping, or bringing to a team. Track in your own task system; this file is just the breadcrumb.

## Cross-paper insights

If multiple papers point to the same trend, write a synthesis note: `<YYYY-MM-DD>--insight-<topic>.md` with the same frontmatter (omit `paper`/`url`, use `papers:` as a list).
