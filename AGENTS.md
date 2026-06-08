# AGENTS.md

Guidance for AI agents (Codex, Claude Code, etc.) working in this repository.

## Repository Overview

Plain-text research memo repository for personal stock investing. No build system, tests, or application code.

## Directory Structure

| Directory | Purpose |
|-----------|---------|
| `memos/` | Research notes — earnings summaries, podcast/report extractions, investment analysis |
| `data/` | CSV files with structured quantitative data (e.g. cost shares, pricing tables by quarter) |
| `earnings/` | Earnings call notes, one file per company-quarter (e.g. `MediaTek-2026-Q1.md`) |
| `theses/` | Long-form investment theses and thesis templates |

## Before Creating a New Memo

**Always check for an existing memo from the same source before writing a new one.**

```bash
# Search by source name, company, or key phrases from the content
grep -ril "<source name or key phrase>" memos/
```

- If a memo already exists that was extracted from the same original content (same PDF, same podcast episode, same earnings call), **do not create a duplicate**. Update or extend the existing file instead.
- Check both the `tags::` line and the `**Source**:` field of candidate files to confirm they share the same origin.
- A memo covering a different angle or topic *from the same source* should be a new section in the existing file, not a separate file, unless the topics are genuinely non-overlapping and the file would become unwieldy.

## File Naming Convention

```
memos/YYYY-MM-DD-kebab-case-description.md
```

Use the date the memo is created or the date of the source material, whichever is more meaningful.

## Memo Format

All memos use Logseq outliner Markdown — every line starts with `- ` and nesting uses tabs:

```markdown
- tags:: [[Ticker]], [[Topic]], [[sector]]

- ## Section Title
	- Content line
		- Nested content
	- **Bold label**: value
```

**Required elements:**
- `tags::` line at the top using `[[WikiLink]]` syntax
- `**Source**:` attribution
- At least one `## Section Title`

## Tag Conventions

Use canonical tag forms — no duplicates or near-duplicates:

| Use | Not |
|-----|-----|
| `[[DRAM]]` | `[[memory]]` |
| `[[$NVDA]]` (ticker form) | `[[NVIDIA]]`, `[[Nvidia]]` |
| `[[data-center]]` | `[[data center]]`, `[[data centers]]`, `[[data-centers]]` |
| `[[GPU]]` | `[[GPUs]]` |
| `[[inference]]` | `[[AI inference]]`, `[[AI Inference]]` |
| `[[hyperscalers]]` | `[[hyperscaler]]` |
| `[[semiconductor]]` | `[[Semiconductors]]` |
| `[[agents]]` | `[[AI-agents]]` |
| `[[capex]]` | `[[capital-expenditures]]` |
| `[[Michael-Burry]]` | `[[Michael Burry]]` |

Before adding a tag, grep existing memos to confirm the canonical form already in use.

## Workflow Rules

- Never push directly to `main`. Always branch → PR → merge.
- Non-code changes (new memos, edits) can be committed and PR'd without prior confirmation.
- When searching for context before answering investment questions, `grep` across `memos/` by ticker, company name, or topic keyword.
- When data-point density is relatively high in a paragraph, use a Markdown table instead of dense prose.
- Exception: do not use tables in `Anecdotes & Opinions` sections. Use one short paragraph per anecdote/opinion, and use quoted text blocks for literal words from sources.
