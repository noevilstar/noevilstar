# CLAUDE.md

<!-- Baseline rules: https://github.com/noevilstar/claude-master -->
<!-- Local clone:    /Users/ms-claus/Projects/claude-master/CLAUDE.md -->
<!-- Freshness:      git -C /Users/ms-claus/Projects/claude-master pull --ff-only -->
<!-- If missing:     git clone https://github.com/noevilstar/claude-master.git /Users/ms-claus/Projects/claude-master -->

<!-- This project also ships an AGENTS.md sibling for ChatGPT Codex / generic agents.
     AGENTS.md is a thin pointer to this CLAUDE.md; do not add rules there.
     See claude-master/modules/agent-files.md for the pattern. -->

@../claude-master/CLAUDE.md

<!-- Project-specific overrides and additions below supersede claude-master. -->

---

## Project Overview

This repository powers the public GitHub profile README at
`github.com/noevilstar/noevilstar`.

## Tech Stack

- Markdown-only GitHub profile repository.
- No runtime app, package manager, tests, or deployment target.

## Sync Contract

- The portfolio site in `../no-evil-llc` is the source of truth for public project
  inventory, portfolio links, and the website-native GitHub activity panel.
- When changing public project lists, GitHub activity cards, or the canonical GitHub
  profile link here, update the matching `no-evil-llc` content in the same work session.
- Canonical GitHub profile repository URL:
  `https://github.com/noevilstar/noevilstar`.

## Local Development

- Edit `README.md`.
- Preview on GitHub after pushing.

## Overrides

- The baseline Python, database, CI, and Railway rules do not apply unless this repo
  grows beyond a Markdown profile README.
