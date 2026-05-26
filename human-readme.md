# Principles for working with an LLM

Standing rules to get better work out of any LLM — Claude, GPT, Gemini, others. Each one targets a single failure mode that shows up in most LLM interactions and degrades the output over time.

A **principle** runs always, before every output. A **skill** only fires when a specific pattern appears. The rules in this folder are principles.

Most LLM problems aren't about the model being "wrong" — they're about the model defaulting to behaviour that looks helpful but creates friction. It tells you to do things it could do itself. It overbuilds when minimum would work. It obsesses on the wrong piece of the problem and can't get unstuck. It states guesses as if they were facts. These four principles target those defaults directly, so the LLM acts more like a thoughtful collaborator than a confident bureaucrat.

---

## The four principles

| Principle | Pain it solves | Typical scenarios | Benefit you get |
|---|---|---|---|
| [Making your LLM proactive](making-your-llm-proactive.md) | The LLM tells you to do things it could have done itself | LLM gives you a six-step setup checklist when it could run five of the steps itself; LLM tells you to copy a code from the terminal instead of putting it on your clipboard; LLM says "go to this URL and sign in" instead of opening the page in your browser; LLM asks you to search the docs for a flag the LLM itself could fetch. | Fewer manual steps. You handle only the bits that genuinely need you — passwords, approvals, decisions only you can make. |
| [First-principles claim audit](first-principles-claim-audit.md) | The LLM confidently says things that fall apart under simple arithmetic | LLM promises "ten podcast episodes recorded in a six-hour workshop" without doing the math; LLM writes "supports 1M concurrent users" with no idea of actual infrastructure; LLM claims a course is "accredited" when no accreditation has been applied for; LLM says "delivered in two weeks" without checking team capacity. | The LLM catches its own impossible claims before you do. Promises survive the math against your actual constraints. |
| [Avoid narrow framing](avoid-narrow-framing.md) | The LLM obsesses on a tiny piece of the problem, gets stuck in a patch loop, and can't see that the actual scope is wider | LLM endlessly redesigns a button, not realising the entire landing page structure is broken; LLM keeps swapping words for synonyms, not realising the whole perspective of the paragraph needs to change; LLM keeps tweaking CSS padding when the underlying layout grid is wrong; LLM polishes a sentence over and over when the paragraph's argument is the actual problem. | The LLM gets unstuck. When iteration stops working, it steps back, questions the framing, and rebuilds at the right scope instead of patching forever. |
| [Karpathy guidelines](karpathy-guidelines.md) | The LLM overbuilds, edits things it wasn't asked to, asserts guesses as facts, declares "done" without verifying | LLM writes 200 lines of "flexible configuration" when a hardcoded value would do; LLM refactors three adjacent functions while fixing one bug, exploding the diff; LLM declares "tests pass" without actually running them; LLM confidently states "X uses Y under the hood" when it never checked. | Smaller and cleaner output. More honest hedging on uncertain claims. Defined success criteria that can be checked. |

---

## How to use

1. **Copy any file** into your LLM's standing-rules config — wherever your model picks up baseline behaviour. Each file is self-contained and ready to lift.

2. **Adapt the examples** to your domain. The principles are general; the scenarios above are illustrative. Replace them with cases from your own work — the failure modes are the same everywhere, only the surface changes.

3. **Stack them.** Each principle handles a different failure mode. Using all four together compounds the effect — proactivity covers *how* the work gets done, the claim audit covers *what* the LLM says is true, narrow framing covers *when to step back instead of keep going*, and Karpathy covers *how to do the work cleanly*.

---

## Why these are intentionally vague

The principles don't hard-code your domain, your tools, or your workflow. They're frames — you fill them with content from your own work. Your examples, your signals, your constraints, your decisions.

**This has been intentionally left vague, so you can personalise it to your use case and shape the system as you wish.**

A working LLM principle is one that fits the way *you* actually work. The template is the starting point; the personalisation is what makes it useful.

---

MIT-licensed. Maintained by [Andrewg223](https://github.com/Andrewg223).
