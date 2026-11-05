# Methodology — AI Search Visibility Testing

## 1. Test design

For each tracked brand, build a **frozen prompt matrix** of non-branded buyer questions — the questions a real customer asks before choosing, with no brand name in them:

- Category head terms ("best health insurance for families")
- Use-case questions ("which X is good for Y")
- Comparison intent ("X vs Y" style category comparisons)
- Price-led questions ("cheapest / best value X")
- Problem-led questions ("X that covers Y problem")

The matrix is frozen before the first run. Changing the questions mid-cycle would invalidate the comparison, so new prompts enter only in the next cycle.

## 2. Execution protocol

- Run every prompt on every engine: ChatGPT, Gemini, Google AI Overviews, Perplexity.
- Run each prompt **more than once**. AI answers are non-deterministic; the same question can return different brand lists across runs. A single run is an anecdote; a rate across runs is a measurement.
- Record for each run: brand mentioned (yes/no), position in the answer, cited sources (URLs), and which competitors appeared.

## 3. Scoring

- **Mention rate** = runs mentioning the brand / total runs
- **Citation rate** = runs citing the brand's own domain / total runs
- **Share of voice** = brand mentions / mentions of all tracked competitors
- **Category coverage** = mention rate on the brand's core category prompts specifically

Report rates, never ranks. "Mentioned in 10 of 20 runs, cited in 0" is a fact; "#1 in ChatGPT" is not a promise anyone can keep.

## 4. Defect lifecycle

Each gap is logged like a software defect:

1. **Reproduction** — prompt, engine, run, and the answer received
2. **Severity** — absence on a core category prompt outranks absence on a comparison prompt
3. **Root-cause hypothesis** — missing answer-first content, no comparison material, weak entity signals, uncrawlable or unstructured pages
4. **Fix** — page-level rebuild: direct-answer blocks, comparison tables, structured data (JSON-LD), consistent entity facts
5. **Retest** — the identical frozen matrix re-run; the defect closes only when the rate moves

## 5. Known limitations

- AI answers vary by run, account state, region and time; results are labelled by coverage, and partial coverage is reported as partial.
- Free-tier engine limits can truncate a cycle; truncated legs are disclosed, never silently treated as complete data.
