# Principle Library — Builder & Install Guide (Public)

This folder is a **library of standing principles** for an LLM assistant (Claude, GPT, others). Each principle is one self-contained file. You read them, pick the ones you want, and install them. Skip the rest.

This `CLAUDE.md` is the **builder**: it tells your assistant how to stand the system up from these files. Point your assistant at this folder and say "set up these principles," or follow the steps yourself.

---

## The idea in one breath

> Every principle is one file with a permanent **ID**. Each file holds two things: a short **gist** that you copy into your assistant's always-loaded config so the rule actually fires, and the **full text** your assistant reads on demand when it needs depth. To change a rule, edit its file. One file, one ID, one always-loaded line.

If that sentence makes sense, you already understand the system. The rest is detail.

---

## The three parts of every principle

Open any `PRIN-NNNN-*.md` file in this folder. Each has the same shape:

| Part | What it is | Where it ends up |
|---|---|---|
| **`[ID]`** | A permanent handle, e.g. `PRIN-0002`. Never changes, even if the principle is renamed. | Frontmatter + every reference |
| **`[GIST]`** | The rule in ~80 words: what to do, how, one vivid example. Enough to *fire* the principle. | **Copied into your assistant's always-loaded config** |
| **`[FULL TEXT]`** | The complete principle: reasoning, all examples, edge cases, anti-patterns. | **Stays in the file**, read on demand |

Why split gist from full text? Because the always-loaded config is read on *every* request — if you paste full text for 20 principles there, you bloat every conversation and, counterintuitively, each rule fires *less* (it's buried). The gist is the smallest thing that still makes the rule fire and act correctly. The full text is there when the assistant needs to go deep, but it doesn't cost you on every turn.

Think of each file as an **installer package**: the gist is the part that gets "installed" into your always-loaded config; the full text is the manual that stays in the box.

---

## The ID is the keystone

Every principle has a stable ID like `PRIN-0002`. Names change — the moment you rename a principle, every reference to it by name breaks. The ID never changes, so it's the handle everything points at. Rename the principle freely; the ID still resolves.

Analogy: a book's ISBN versus its title. Re-title the book, change the cover — the ISBN still finds it. The ID is the ISBN of the rule.

---

## The principle gate (what qualifies as a principle)

A principle is a **universal** guard rule — one that holds across contexts, people, and assistants at a general level. Before you save a rule as a principle, test it:

> Take the rule out of context and drop it into a brand-new assistant with nothing else — only this one rule. Does it stand on its own as a general rule that's immediately applicable to anyone?

- **Yes** → it's a principle. Install it.
- **No** — it only makes sense inside your specific setup, tools, or workflow → it is **not a principle**. It's a *working rule*: keep it in your assistant's project/config instructions, not in this principle library.

Example of a rule that fails the gate: "keep my index files in sync." It assumes a particular filing system exists, so it means nothing to a fresh assistant. Useful, but a working rule — not a principle. When in doubt, default to working rule.

## How to install (3 steps)

You need two places: an **always-loaded config** your assistant reads every session (for Claude Code that's a `CLAUDE.md` at your project or home directory; adapt for your tool), and a **folder** where these principle files live so your assistant can read full text on demand.

1. **Read the principles. Pick the ones you want.** They're independent — take any subset. Each file's gist tells you in 80 words what it does, so you can decide fast.

2. **Copy each chosen principle's `## Gist` block into your always-loaded config.** Keep the `[PRIN-NNNN]` tag on it. That tag is the pointer back to this file for full text.

3. **Keep this folder where your assistant can reach it.** When the gist isn't enough — applying the principle deeply, or editing it — the assistant opens the `PRIN-NNNN` file and reads the full text.

That's the install. Your always-loaded config now carries a handful of ~80-word gists; the full library sits on disk, read only when needed.

---

## How to maintain

One rule, and it's the whole discipline:

> **Editing flows one direction: source first, copies follow.** To change a principle, edit its `PRIN-NNNN` file (the source of truth). Then refresh the gist you copied into your config. Never edit the config copy and let the file go stale — the file is canonical.

---

## How to scale past a handful

When you have many principles, split them by how often they apply:

- **Always-on (a small core).** Universal rules that apply to nearly every task. Their gists live in your always-loaded config full-time.
- **Conditional (the long tail).** Domain-specific rules (e.g. "when building HTML, do X"). Don't load these every turn. Keep a one-line index entry; the assistant reads the file when the trigger comes up.

This keeps your always-loaded config small no matter how big the library grows.

---

## Adapting these to your own work

These principles are written to be general. The failure mode each one targets is universal; only the examples are specific. When you install one, replace its worked example with one from your own work — that's what makes a principle stick. The structure is the gift; the personalisation is yours to add.

---

MIT-licensed. The structure is free to copy, fork, and teach.
