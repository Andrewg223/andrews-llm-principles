# Principles for working with an LLM

Standing rules to get better work out of any LLM — Claude, GPT, Gemini, others. Each one targets a single failure mode that shows up in most LLM interactions and degrades the output over time.

A **principle** runs always, before every output. A **skill** only fires when a specific pattern appears. The rules in this folder are principles.

Most LLM problems aren't about the model being "wrong" — they're about the model defaulting to behaviour that looks helpful but creates friction. It tells you to do things it could do itself. It overbuilds when minimum would work. It gets stuck iterating on the wrong scope. It states guesses as if they were facts. These four principles target those defaults directly, so the LLM acts more like a thoughtful collaborator than a confident bureaucrat.

---

## The four principles

| Principle | Pain it solves | Benefit you get |
|---|---|---|
| [Making your LLM proactive](making-your-llm-proactive.md) | The LLM tells you to do things it could have done itself | Fewer manual steps per task. You handle only the bits that genuinely need you — passwords, approvals, decisions only you can make. |
| [First-principles claim audit](first-principles-claim-audit.md) | The LLM confidently says things that fall apart under simple arithmetic | The LLM catches its own impossible claims before you do. Promises survive the math against your actual constraints. |
| [Avoid narrow framing](avoid-narrow-framing.md) | The LLM gets stuck iterating on small fixes inside the wrong scope, each new fix breaking something else | The LLM steps back when iteration stops working, questions the framing, and rebuilds at the right scope. No more patch loops. |
| [Karpathy guidelines](karpathy-guidelines.md) | The LLM overbuilds, edits things it wasn't asked to, asserts guesses as facts, declares "done" without verifying | Smaller and cleaner output. More honest hedging on uncertain claims. Defined success criteria that can be checked. |

---

## How to use

1. **Copy any file** into your LLM's standing-rules config — wherever your model picks up baseline behaviour. Each file is self-contained and ready to lift.

2. **Adapt the examples** to your domain. The principles are general; the examples in each file are illustrative. Replace them with cases from your own work — the failure modes are the same everywhere, only the surface changes.

3. **Stack them.** Each principle handles a different failure mode. Using all four together compounds the effect — proactivity covers *how* the work gets done, the claim audit covers *what* the LLM says is true, narrow framing covers *when to step back instead of keep going*, and Karpathy covers *how to do the work cleanly*.

---

## Why these are intentionally vague

The principles don't hard-code your domain, your tools, or your workflow. They're frames — you fill them with content from your own work. Your examples, your signals, your constraints, your decisions.

**This has been intentionally left vague, so you can personalise it to your use case and shape the system as you wish.**

A working LLM principle is one that fits the way *you* actually work. The template is the starting point; the personalisation is what makes it useful.

---

MIT-licensed. Maintained by [Andrewg223](https://github.com/Andrewg223).
