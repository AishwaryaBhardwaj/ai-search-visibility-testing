# AI Search Visibility Testing & Validation Programme

A systematic testing programme that measures whether brands get **mentioned and cited** when real buyers ask AI search engines what to buy — and turns the gaps into a fix-and-retest backlog.

Instead of opinions about "AI SEO", this programme runs the same discipline used in software quality work: a frozen test set, repeated execution across environments, logged defects with reproduction steps, fixes, and re-runs to confirm improvement.

## What it measures

- **Mention rate** — how often a brand appears in AI answers to non-branded buyer questions
- **Citation rate** — how often the brand's own pages are the source the AI cites
- **Share of voice** — the brand's presence versus competitors in the same answers
- **Category coverage** — whether the brand shows up on its core category questions, not just comparison queries

## How it runs

| Layer | Detail |
|---|---|
| Test set | A frozen matrix of non-branded buyer prompts per category ("best X for Y", "X vs Y", price-led and problem-led questions) |
| Environments | ChatGPT, Gemini, Google AI Overviews, Perplexity |
| Execution | Repeated runs per prompt — AI answers vary run to run, so a single observation proves nothing |
| Defect logging | Every gap logged with prompt, engine, run and severity, the same way a software defect is logged |
| Fix & retest | Page-level fixes (answer-first structure, comparison tables, structured data, entity consistency), then the identical matrix re-run to confirm movement |

## Programme scale so far

- 13 brands tracked across insurance, beauty, travel, fintech, SaaS and health categories
- 4 AI engines, up to 5 prompts per brand per engine per cycle
- Recurring measurement cycles with per-brand evidence dossiers

## What the data showed (anonymised patterns)

- **The invisible brand:** mentioned in roughly half of all runs, but in **zero runs on its own core category** — present in comparisons, absent where buyers actually decide.
- **The displaced incumbent:** wins head-to-head comparison prompts, then vanishes on plan and price questions, where a digital-first challenger takes the answer instead.
- **The one-engine brand:** perfect scores in one engine (5/5), completely absent (0/5) in another — visibility that depends on a single surface is not visibility.
- **The false positive:** brands that look "fine" because their name appears, while the AI recommends a competitor in the same answer.

## Why this matters

Buyers increasingly ask AI assistants instead of scrolling search results. A brand that is not mentioned or cited in those answers does not exist at the moment of decision. This programme makes that measurable — and fixable.

## In this repository

- `ai-visibility-index.md` — the named AI Visibility Index: 13 Indian brands × 4 AI engines, with the patterns and evidence from the November 2026 cycle
- `METHODOLOGY.md` — the full test design: prompt matrix construction, run protocol, scoring and the defect lifecycle
- `prompt-matrix-template.md` — the reusable prompt matrix template, by buyer intent
- `sample-findings.md` — anonymised findings from the 13-brand cycle

*Per-company dossiers (prompt-level evidence and fix roadmaps) and all point-of-contact details from the live programme are never published; the method, the patterns and the index are.*
