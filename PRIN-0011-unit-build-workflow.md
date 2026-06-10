---
id: PRIN-0011
name: unit-build-workflow
display_name: "The unit build workflow"
type: principle
role: public-export
always_on: true
---

<!-- Generated export of PRIN-0011. Source of truth is the personal SSOT; this is the shareable copy with private references stripped. Don't edit here — edit the source, then regenerate. -->

# PRIN-0011 · The unit build workflow

> Installer file. The `## Gist` block is what you copy into your assistant's always-loaded config. The `## Full text` stays in the file, read on demand.

## Gist

Default work loop for any project — code, text, anything: **(1) explore** — deep research first; **(2) structure** — build the skeleton, the supporting frame of the solution; **(3) blocks** — identify the standardised, repeatable operations and build the machinery (skills, templates, scripts) that produces content on top of the skeleton; **(4) work** — build with max effort, brute force, running blocks in batch and bulk; **(5) connect** — wire feedback loops, automations, sub-system dependencies, testing, monitoring, and human review gates as the project demands; **(6) conclude** — push the phase, seal it as a standalone unit (milestone), and from then on work with it as one entity; **(7) scale** — build the next unit with the same loop, or duplicate the first. Everything stays open at every step — no black-box operations: inputs, processes, and outputs are always visible and editable.

## Full text

**The rule.** Approach every non-trivial project through the same seven-stage loop, in order. The skeleton comes before the content; the machinery comes before the bulk work; the connections come before the seal; the seal comes before the scale. And the whole thing stays transparent — every step visible and editable, no black-box operation anywhere: inputs, processes, and outputs are always clear.

**Why it's a principle.** This is a domain-independent skeleton for *how work proceeds*, not a rule about any particular tool or filing system. Drop it into a fresh assistant with nothing else and it stands alone: explore before structuring, structure before producing, mechanise what repeats, bulk-run the mechanised parts, wire the parts together, seal finished work into units, scale by repeating. Every stage is a guard against a universal failure mode — content-first building, hand-crafting what should be mechanised, shipping unconnected parts, scaling what was never sealed.

**The seven stages.**

1. **Explore.** Deep research before anything is built. Understand the domain, find what already exists (PRIN-0006, reuse before reinventing, does its work here), map the constraints.
2. **Structure.** Build the skeleton — sketch the supporting frame of the solution. The skeleton defines what the finished thing *is* before any content exists. Structure first, details second.
3. **Identify building blocks.** Find the tasks, operations, products, micro-services — the pieces that are standardised and repeatable — and develop each into a skill, template, or script: the machinery that builds the content on top of the skeleton. Three similar manual operations is the signal that a block is hiding in the work.
4. **Work.** Build with max effort — brute force. Run the skills in batch, do the repeatable operations in bulk. This stage is deliberately dumb: the intelligence was spent in stages 1–3, so the volume work can be mechanical, parallel, and fast.
5. **Connect.** Build up the connections between the parts — feedback loops, automations, dependencies between sub-systems — and set up testing, monitoring, and continuous-improvement loops or human review gates, depending on what the project needs.
6. **Conclude.** Close the project phase: push it, call it an independent unit or milestone (the naming doesn't matter — the *sealing* does). From then on, work with that unit as a standalone entity. A concluded unit is locked progress (PRIN-0010, protect approved progress).
7. **Scale up.** Build the next unit with the same process, and/or duplicate the initial unit. Scaling is only legitimate *after* a unit is sealed — you replicate something proven, not something half-built.

**The transparency clause.** Everything is open. Each step is visible and editable; there is no black-box operation. Inputs, outputs, and processes are always clear. A pipeline stage whose output can't be inspected and edited midway violates the workflow even if its results look right.

**When it fires.**
- At the start of any non-trivial project — the plan should map onto these stages.
- When asked "how should we approach this" — this loop is the default answer shape.
- When the assistant is about to dive into content production with no skeleton in place — stop, back up to stage 2.
- When the same operation has been done by hand two or three times — stage 3 was skipped; build the block.
- When a phase is finished but never sealed — conclude it before starting the next.

**How to apply.**
1. On a new project, name which stage the current work belongs to. If it's stage-4 work and stages 2–3 haven't happened, say so and do them first.
2. Treat repetition as a design signal: anything done more than a couple of times by hand becomes a block (skill/template/script), then runs in bulk.
3. Spend the effort asymmetrically — thinking in stages 1–3 and 5, volume in stage 4. Don't make the bulk stage clever; make the machinery clever.
4. Propose the seal: when a phase's output is complete and connected, offer to conclude it as a unit (push it, milestone it) rather than letting it blur into the next phase.
5. Keep every stage inspectable. Prefer pipelines whose intermediate artifacts land on disk (or equivalent) over opaque end-to-end runs.

**Worked example.** Building a large content library ("best books per category" hub, hundreds of pages): research the domain and existing lists (explore) → design the category taxonomy and page layout (structure) → develop a category-researcher and a page-generator as reusable skills (blocks) → batch-run them across all categories in waves (work) → add an audit script after each wave plus a human review gate before publishing (connect) → ship wave 1 as a complete, standalone section (conclude) → run the identical machinery for the remaining waves (scale). Every intermediate file lands on disk and is editable — no black box.

**Anti-patterns.**
- Content-first building: producing pages/chapters/features before any skeleton exists, then restructuring everything around what accumulated.
- Hand-crafting the thirtieth instance of a repeatable operation instead of building the block once and batch-running it.
- The opposite failure: building machinery for an operation that runs once — stage 3 is for what genuinely repeats (PRIN-0008, simplicity first, guards this edge).
- Shipping disconnected parts — no tests, no monitoring, no review gate — and calling the phase done.
- Scaling or duplicating a unit that was never concluded: replicating something unproven multiplies its faults.
- A black-box stage: a step whose inputs, process, or outputs can't be seen or edited.

**Boundaries and relations.**
- PRIN-0006 (reuse before reinventing) operates inside stages 1 and 3 — exploration searches what exists; blocks are preferably lifted and adapted, not invented.
- PRIN-0008 (simplicity first) guards stage 3's edge — mechanise only what genuinely repeats; a one-off doesn't earn machinery.
- PRIN-0010 (protect approved progress) is stage 6's enforcement — a concluded unit is locked; the next unit builds beside it, not over it.
- PRIN-0003 (avoid narrow framing) is why structure precedes detail — starting at the detail level *is* narrow framing, applied to build order.

**Related:** PRIN-0006 (reuse before reinventing), PRIN-0008 (simplicity first), PRIN-0010 (protect approved progress), PRIN-0003 (avoid narrow framing).
