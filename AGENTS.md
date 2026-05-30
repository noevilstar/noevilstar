# AGENTS.md

<!-- Baseline rules: https://github.com/noevilstar/claude-master -->
<!-- Local clone:    /Users/ms-claus/Projects/claude-master/CLAUDE.md -->
<!-- Freshness:      git -C /Users/ms-claus/Projects/claude-master pull --ff-only -->
<!-- If missing:     git clone https://github.com/noevilstar/claude-master.git /Users/ms-claus/Projects/claude-master -->

> **This project's rules live in `CLAUDE.md`, not here.**
> `AGENTS.md` is a thin pointer for agents that read this convention (ChatGPT Codex
> and others). The single source of truth is `CLAUDE.md` and the baseline it imports
> from `claude-master`.

---

## If you are an agent reading this file

1. **Read `./CLAUDE.md`** in this project root. It defines project-specific rules and
   overrides.
2. **Read `../claude-master/CLAUDE.md`** (the baseline). The project's `CLAUDE.md`
   imports it via Claude Code's `@` syntax, but other tools must follow the path
   manually.
3. If `../claude-master/` is missing locally, fetch the baseline from
   `https://github.com/noevilstar/claude-master` (raw `CLAUDE.md`) and treat it as if
   cloned.
4. The baseline references modules under `claude-master/modules/`. Read the ones
   relevant to your task.
5. Apply baseline rules unless this project's `CLAUDE.md` has an "Overrides" section
   that supersedes them.

---

## Why this file exists

Different agentic CLIs read different convention files. Claude Code reads
`CLAUDE.md` and resolves `@` imports natively. ChatGPT Codex and similar tools read
`AGENTS.md`. Rather than duplicate rules, every tool-specific file in this project is
a pointer back to the same `CLAUDE.md`.

The mechanism is documented in `claude-master/modules/agent-files.md`.
