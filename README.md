# Principles for working with an LLM

Standing rules to get better work out of any LLM — Claude, GPT, Gemini, others. Each one targets a single failure mode that shows up across most LLM interactions.

A **principle** runs always, before every output. A **skill** only fires when a specific pattern appears. The rules here are principles.

---

## The four principles

| Principle | Pain it solves | Benefit you get |
|---|---|---|
| [Making your LLM proactive](making-your-llm-proactive.md) | The LLM tells you to do things it could have done itself | Fewer manual steps. You handle only the bits that genuinely need you. |
| [Karpathy guidelines](karpathy-guidelines.md) | The LLM overbuilds, edits things it wasn't asked to, asserts guesses as facts | Smaller, cleaner output. More honest hedging. Clearer "done". |
| [First-principles claim audit](first-principles-claim-audit.md) | The LLM confidently says things that fall apart under simple arithmetic | The LLM catches its own impossible claims before you do. |
| [Avoid narrow framing](avoid-narrow-framing.md) | The LLM flags or asks about things the conversation already answered | Fewer pointless interruptions. Real concerns when raised. |

---

## How to use

Copy any file into your LLM's standing-rules config — wherever your model picks up baseline behaviour. Each file is self-contained and ready to lift.

The principles stack. Each tackles a different failure mode; using all four compounds the effect.

---

## Why these are intentionally vague

The principles don't hard-code your domain, your tools, or your workflow. They're frames — you fill them with content from your own work.

**This has been intentionally left vague, so you can personalise it to your use case and shape the system as you wish.**

---

MIT-licensed. Maintained by [Andrewg223](https://github.com/Andrewg223).
