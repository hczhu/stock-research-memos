# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a plain-text research memo repository for personal stock investing. All content lives under `memos/` as Markdown files. There is no build system, test suite, or application code.

## File Naming Convention

```
memos/YYYY-MM-DD-kebab-case-description.md
```

Use the date the memo is created or the date of the source material, whichever is more meaningful. Multi-word titles with spaces are acceptable for older files but kebab-case is preferred for new ones.

## Memo Format

All memos use Logseq outliner Markdown — every line starts with `- ` and nesting uses tabs:

```markdown
- tags:: [[Ticker]], [[Topic]], [[sector]]

- ## Section Title
	- Content line
		- Nested content
	- **Bold label**: value
```

**Required elements for new memos:**
- `tags::` line at the top using `[[WikiLink]]` syntax — include ticker symbols, sector (e.g. `[[semiconductor]]`, `[[AI]]`), and topic tags
- A `## Section Title` as the first section
- `**Source**:` attribution where the content comes from a third party

**Optional but common elements:**
- `**Thesis**:` — one-line investment takeaway
- Data tables using standard Markdown table syntax
- `## Investment Implications` or `## Key Data Points` sections
- `## X Post` section at top when memo is intended for publishing (use `——` as section dividers, single post format for X Premium)

## Input Handling

- **No images**: Never use images in memos. When the input prompt contains images (screenshots, charts, tables), OCR them to extract text and data points, then work from the extracted content.
- **High data-point density**: When a text block contains many data points (metrics, figures, comparisons), structure it as a Markdown table rather than prose or bullet lists.

## Workflow Rules

- Never push directly to `main`. Always branch → PR → merge.
- Non-code changes (new memos, edits) can be committed and PR'd without prior confirmation.
- When searching for context before answering investment questions, `grep` across `memos/` by ticker symbol, company name, or topic keyword.

## Content Themes

Memos span: AI infrastructure (GPU, HBM, DRAM, packaging), hyperscaler capex and strategy, SaaS metrics and competitive dynamics, China tech, semiconductor supply chain, and macro. Most memos are based on earnings calls, sell-side research, industry podcasts, or primary source data extracted from screenshots.
