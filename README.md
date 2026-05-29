# LLM Principles — standing rules that actually get followed

A small, simple system for giving an AI assistant standing rules (Claude, GPT, others) and keeping them easy to maintain as they grow. Each rule is one file. Read them, take the ones you want, skip the rest.

## The idea in one breath

Every rule is one file with a permanent ID. Each file holds a short **gist** — you copy it into your assistant's always-loaded config so the rule fires — and the **full text**, read on demand. One file, one ID, one always-loaded line.

## How one principle file is built

Open any `PRIN-NNNN-*.md`:

```
[id]         e.g. PRIN-0002 — a permanent handle. Rename the rule; the ID still resolves.
[gist]       ~80 words: the rule + how + one example. Copy this into your config.
[full text]  the complete rule. Stays in the file, read when depth is needed.
```

The file is an installer: the **gist** is what you install into your config; the **full text** is the manual that stays in the box.

## Install in 3 steps

1. **Read the `PRIN` files. Pick the ones you want.** They are independent — take any subset.
2. **Copy each chosen `## Gist` block into your assistant's always-loaded config** (for Claude Code that is a `CLAUDE.md`). Keep the `[PRIN-NNNN]` tag.
3. **Keep this folder reachable** so your assistant can open the full text when the gist is not enough.

## Why gist + full text?

Your always-loaded config is read on every request. Paste full rules there and every conversation gets heavier — and buried rules fire less, not more. The gist is the smallest thing that still makes a rule fire; the full text waits in the file.

## The keystone: a stable ID

Names change, and references to them break. A permanent ID like `PRIN-0002` is the handle everything points at, so you can rename a rule freely. Like a book's ISBN versus its title — re-title the book, change the cover, the ISBN still finds it.

## Also in this folder

- `CLAUDE.md` — the builder your assistant follows to set the system up.
- `human-readme.md` — the catalogue of the actual principles, and the pain each one solves.

MIT-licensed. Copy, fork, teach.
