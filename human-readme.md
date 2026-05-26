# Principles for working with an LLM

A set of standing principles for getting better work out of any LLM — Claude, GPT, Gemini, others. These aren't prompt-engineering tricks or one-off hacks. They're standing rules the model applies to every output by default, regardless of what task you've asked for.

**Standing principle ≠ triggered skill.** A skill fires on a specific pattern ("when the user has asked for the same fix three times, propose a reset"). A principle runs always, before every output. The rules in this folder are principles.

---

## The pains these principles solve

Most LLM interactions degrade in predictable ways:

- **You get told to do things the LLM could have done.** Six steps in a checklist where three are shell commands and one is "open this URL". The model could have run all four. You shouldn't have to.
- **You get plausible-sounding facts that turn out wrong.** The model says "X uses Y library under the hood" — full confidence, no hedge. Turns out it was a guess that sounded like a fact. You only find out after you've based a decision on it.
- **You get flagged for things that aren't problems.** "I notice X is undefined" — the definition was three paragraphs up. The model didn't read the wider context.
- **You get a stack of surgical fixes that drift further from what you wanted.** Each fix breaks something the previous fix didn't touch. By the fifth fix the file is unrecognisable and the original bug is still there.
- **You get architecturally overcomplicated solutions.** Twenty lines for a job ten lines would have done — "for future flexibility" that nobody asked for.

Each principle targets one of these failure modes.

---

## Principles in this folder

| File | Outcome / benefit |
|---|---|
| `making-your-llm-proactive.md` | **Fewer manual steps per task.** The LLM opens URLs in your browser, copies codes to your clipboard, pre-fills CLI prompts, runs installs, fetches docs. You're left with the irreducible human steps only — passwords, 2FA, decisions only you can make. Two clicks instead of six. |
| `karpathy-guidelines.md` | **Less LLM coding sloppiness.** Five behavioural rules (Karpathy's original four plus a fifth — check your own assumptions). Result: less overcomplication, fewer unsolicited refactors, fewer confidently-wrong claims, clearer success criteria, smaller diffs. |
| `first-principles-claim-audit.md` | **The LLM catches its own impossible claims before you do.** Before stating any scope, timeline, capacity, or accreditation claim, the model multiplies it against real constraints. "You'll have 10 podcast episodes from a 6-hour workshop" gets audited against the maths and corrected. |
| `avoid-narrow-framing.md` | **Fewer pointless flags and clarifying questions.** Before raising any concern or asking a question, the model zooms out one level. If the wider scope already answers it, the concern gets dropped silently. You don't have to re-explain what's already in the conversation. |

---

## How to use this

1. **Copy any principle file** you want into your own LLM setup — your `CLAUDE.md`, your project README, your system prompt, your `.cursor/rules/`, your skill library. Each file is self-contained and ready to be lifted.

2. **The principles are intentionally left vague where they touch *your* system, *your* workflow, *your* projects.** This is intentional. You add your own specifics — your domain examples, your OS-specific commands, your team's approval gates, your unusual tradeoffs. Each principle is a frame; you fill it with content from your actual work.

3. **Combine them — they stack.** Each principle addresses a distinct failure mode:
   - **Max proactivity** covers *how* work gets done (the model does the boring bits, not you).
   - **Karpathy guidelines** covers *how the model codes* (minimum surgical scope, verified claims, defined success).
   - **First-principles claim audit** covers *what the model says is true* (claims survive arithmetic against constraints).
   - **Avoid narrow framing** covers *when the model should flag or ask* (only when the wider context doesn't already answer).

   Together they form a baseline. Each one alone is useful; together they compound.

4. **Adapt freely.** The point is *your* working principles, not Andrew's. The examples in each file (a GitHub CLI setup, a podcast workshop, a code review scenario) are illustrative. Replace them with examples from your domain — the failure modes are the same, the surface is different.

---

## Why these are intentionally vague

Each principle could be made more specific by hard-coding decisions:

- Max proactivity could specify `pbcopy` for clipboard — but Windows users need `clip` and Linux users need `xclip` or `wl-copy`.
- The claim audit could specify "workshops" as the domain — but the principle applies equally to SaaS capacity claims, content deliverable claims, and architecture performance claims.
- Karpathy could specify a language or framework — but the rules are language-agnostic.

**This has been intentionally left vague, so you can personalise it to your use case and shape the system as you wish.** Make it specific to where *you* work. The principle is the frame; your specifics are the content.

---

## Where these come from

These principles are derived from real working sessions with Claude across building software, writing prose, designing interfaces, and shipping content. Each one has a worked example in its file showing the failure mode it addresses and the corrected behaviour.

Personal versions (with project-specific examples, named memory files, system pointers, and a merged HTML / design ruleset) live in a private repo. The public versions in this folder are the generalisable cores — written so they're useful without needing the author's specific setup.

---

## Contributing

If you find a clearer phrasing for a principle, a failure mode that isn't covered, or a principle that compounds with these — PRs welcome. The bar: each principle should be standing (always-on), generalisable (works across domains), and self-contained (one file, lift-and-ship).

---

Maintained by [Andrewg223](https://github.com/Andrewg223). MIT-licensed where applicable.
