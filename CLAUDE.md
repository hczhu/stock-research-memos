# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

See [AGENTS.md](AGENTS.md) for the full repository overview, directory structure, file naming conventions, memo format, tag conventions, and workflow rules. All guidance there applies equally to Claude Code.

## Claude-Specific Notes

- When searching for context before answering investment questions, `grep` across `memos/`, `earnings/`, and `theses/` by ticker symbol, company name, or topic keyword.
- Structured data in `data/` is CSV; read it directly to answer quantitative questions rather than guessing from memo text.
