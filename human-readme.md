# Principles for working with an LLM

Standing rules to get better work out of any LLM — Claude, GPT, Gemini, others. Each one targets a single failure mode that shows up in most LLM interactions and degrades the output over time.

A **principle** runs always, before every output. A **skill** only fires when a specific pattern appears. The rules in this folder are principles.

Most LLM problems aren't about the model being "wrong" — they're about the model defaulting to behaviour that looks helpful but creates friction. It obsesses on the wrong piece of the problem and can't get unstuck. It tells you to do things it could do itself. It misses dead-obvious mistakes by staying inside the narrow frame of the task it was given. It interrupts you with questions whose answers it could have derived itself. It reinvents solutions that already exist instead of finding and adapting them. It delivers a file and leaves the index that tracks it stale. It overbuilds — in code, architecture, and its own answers — when minimum would do. These eight principles target those defaults directly, so the LLM acts more like a thoughtful collaborator than a confident bureaucrat.

---

## The eight principles

| Principle | Pain it solves | Benefit you get | Typical scenarios |
|---|---|---|---|
| [Avoid narrow framing](PRIN-0003-avoid-narrow-framing.md) | The LLM obsesses on a tiny piece of the problem, gets stuck in a patch loop, and can't see that the actual scope is wider | The LLM gets unstuck. When iteration stops working, it steps back, questions the framing, and rebuilds at the right scope instead of patching forever. | <ul><li>LLM is endlessly redesigning a button, not realising the entire landing page structure is broken</li><li>LLM keeps swapping words for synonyms, not realising the whole perspective of the paragraph needs to change</li><li>LLM keeps tweaking CSS padding when the underlying layout grid is wrong</li><li>LLM polishes a sentence over and over when the paragraph's argument is the actual problem</li><li>LLM tunes one function's output when the data flow upstream is the bug</li></ul> |
| [Making your LLM proactive](PRIN-0001-max-proactivity.md) | The LLM tells you to do things it could have done itself | Fewer manual steps. You handle only the bits that genuinely need you — passwords, approvals, decisions only you can make. | <ul><li>LLM gives you a six-step setup checklist when it could run five of the steps itself</li><li>LLM tells you to copy a code from the terminal instead of putting it on your clipboard</li><li>LLM says "go to this URL and sign in" instead of opening the page in your browser</li><li>LLM asks you to search the docs for a flag the LLM itself could fetch</li></ul> |
| [Sanity-check claims](PRIN-0002-sanity-check-claims.md) | The LLM misses dead-obvious mistakes by staying inside the narrow frame of the task. It looks only at what was explicitly asked for (grammar, formatting, tone) and doesn't examine the underlying logic of what the content actually says | The LLM goes a level deeper than the task framing. It checks the substantive claims of the content — arithmetic, scope, capacity, accreditation — and flags what doesn't add up, even if the original task didn't ask for it. | <ul><li>LLM proofreads a sentence containing "2+2=5" and corrects only the grammar, missing the dead-obvious semantic error a human would spot in an instant</li><li>LLM is asked to edit for tone and silently ships a budget claim that doesn't add up</li><li>LLM promises "ten podcast episodes recorded in a six-hour workshop" without doing the math</li><li>LLM writes "supports 1M concurrent users" with no idea of the actual infrastructure</li><li>LLM claims a course is "accredited" when no accreditation has been applied for</li><li>LLM says "delivered in two weeks" without checking team capacity</li></ul> |
| [Five-whys self-audit on your own questions](PRIN-0005-five-whys-self-audit.md) | The LLM interrupts you with clarifying questions whose answers it could have derived itself | Fewer pointless interruptions. The LLM filters its own questions before asking and only escalates the bits that genuinely need a human decision. | <ul><li>LLM asks "what timestamp format should I use?" when the format is right there in your template</li><li>LLM asks "should I auto-fill the index or do you?" for mechanically derivable clerical work</li><li>LLM asks "should I add a log entry?" when the convention obviously says yes</li><li>LLM proposes a checklist with steps like "fill in [deterministic field]" instead of just filling it in</li></ul> |
| [Karpathy guidelines](PRIN-0004-karpathy-and-assumptions.md) | The LLM overbuilds, edits things it wasn't asked to, asserts guesses as facts, declares "done" without verifying | Smaller and cleaner output. More honest hedging on uncertain claims. Defined success criteria that can be checked. | <ul><li>LLM writes 200 lines of "flexible configuration" when a hardcoded value would do</li><li>LLM refactors three adjacent functions while fixing one bug, exploding the diff</li><li>LLM declares "tests pass" without actually running them</li><li>LLM confidently states "X uses Y under the hood" when it never checked</li></ul> |
| [Reuse before reinventing](PRIN-0006-reuse-before-reinventing.md) | The LLM builds bespoke solutions to already-solved problems instead of finding and adapting what exists | Faster, sturdier results. The LLM searches for battle-tested solutions first, adopts them as building blocks, and reasons from scratch only when nothing good enough exists. | <ul><li>LLM designs a custom orchestration system when a popular open-source one already does it</li><li>LLM hand-rolls auth or session logic that a well-tested library handles</li><li>LLM calls a common, widely-implemented architecture "novel" and starts from a blank file</li><li>LLM reasons from first principles by default when a ready-made solution is one search away</li></ul> |
| [Keep index and logs current](PRIN-0007-keep-index-logs-current.md) | The LLM delivers a file but leaves the index/log files that track it stale, so the record drifts out of sync with reality | The record stays accurate on its own. After delivering a file, the LLM updates the index/log in the same folder and every parent up to the root — no prompting. | <ul><li>LLM writes a new doc but never adds it to the folder's index, so the next session can't find it</li><li>LLM updates a leaf folder's index but forgets the root master log in a cascading hierarchy</li><li>LLM says "you may want to update the changelog" instead of just updating it</li><li>LLM invents a new entry format instead of matching the index's existing schema</li></ul> |
| [Simplicity first](PRIN-0008-simplicity-first.md) | The LLM overbuilds — not just in code, but in architecture, docs, and its own answers — adding layers, files, and generality nobody asked for | Minimum that solves the problem, in everything. When two designs both work, the LLM ships the simpler one and says why; it cuts anything not load-bearing. | <ul><li>LLM designs a database with backlinks when a flat index does the job</li><li>LLM answers with three files where one would do</li><li>LLM writes a 1,300-word explainer where a 350-word README lands it</li><li>LLM builds "flexibility for later" that nobody requested</li></ul> |

---

## How to use

1. **Copy any file** into your LLM's standing-rules config — wherever your model picks up baseline behaviour. Each file is self-contained and ready to lift.

2. **Adapt the examples** to your domain. The principles are general; the scenarios above are illustrative. Replace them with cases from your own work — the failure modes are the same everywhere, only the surface changes.

3. **Stack them.** Each principle handles a different failure mode. Using all eight together compounds the effect — narrow framing covers *when to step back instead of keep going*, proactivity covers *how the work gets done*, the claim audit covers *what the LLM says is true and how deep it looks*, the five-whys self-audit covers *which questions are even worth asking you*, Karpathy covers *how to do the work cleanly*, reuse-before-reinventing covers *whether to build it at all or adopt what already exists*, keep-index-and-logs-current covers *keeping the record in sync once the work ships*, and simplicity-first covers *how much to build in the first place*.

---

## Why these are intentionally vague

The principles don't hard-code your domain, your tools, or your workflow. They're frames — you fill them with content from your own work. Your examples, your signals, your constraints, your decisions.

**This has been intentionally left vague, so you can personalise it to your use case and shape the system as you wish.**

A working LLM principle is one that fits the way *you* actually work. The template is the starting point; the personalisation is what makes it useful.

---

MIT-licensed. Maintained by [Andrewg223](https://github.com/Andrewg223).
