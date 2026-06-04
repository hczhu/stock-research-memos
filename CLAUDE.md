# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

See [AGENTS.md](AGENTS.md) for the full repository overview, directory structure, file naming conventions, memo format, tag conventions, and workflow rules. All guidance there applies equally to Claude Code.

## Claude-Specific Notes

- When searching for context before answering investment questions, `grep` across `memos/`, `earnings/`, and `theses/` by ticker symbol, company name, or topic keyword.
- Structured data in `data/` is CSV; read it directly to answer quantitative questions rather than guessing from memo text.
- **No images**: Never embed images in memos. When the input contains images (screenshots, charts, tables), OCR them to extract text and data points, then work from the extracted content.
- **High data-point density**: When a text block contains many data points (metrics, figures, comparisons), structure it as a Markdown table rather than prose or bullet lists.
