# Repository guidelines for AI agents

This file is the single source of truth for AI coding agents working in this
repo. `CLAUDE.md` and `GEMINI.md` are symlinks to this file; Codex reads
`AGENTS.md` natively.

## Repository overview

A collection of small, self-contained web utilities. Each tool lives in its
own top-level directory and is intended to be runnable directly (open the
`index.html` in a browser — no build step, no server).

### Tools

- `clean_html/` — Paste content from Google Docs and get clean HTML suitable
  for Strapi's CKEditor field.

## Conventions

- Each utility is self-contained in its own directory.
- Prefer a single `index.html` with inline CSS/JS unless complexity justifies
  splitting files — these are meant to be drop-in, copy-anywhere tools.
- No build step. No package manager. No framework unless a tool genuinely
  needs one.
- Keep dependencies to zero where possible; otherwise load from a CDN.

## Allowed commands

Agents may run the following commands without asking for confirmation:

- `git status`
- `git add`
- `git commit`
- `git log`
- `git diff`
- `cat`
- `ls`

Any other command — especially anything that writes outside the repo, pushes
to a remote, deletes files, or installs software — should be confirmed with
the user first.

## When adding a new utility

1. Create a new top-level directory with a descriptive snake_case name.
2. Put an `index.html` inside that works when opened directly.
3. Add a one-line entry under **Tools** above.
