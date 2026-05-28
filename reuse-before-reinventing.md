---
name: reuse-before-reinventing
description: "A standing principle that stops the LLM from building bespoke solutions to already-solved problems. Search for existing, battle-tested solutions first; adopt and personalise them as building blocks; reason from first principles to build from scratch only when nothing good enough exists."
metadata:
  type: principle
---

# Reuse before reinventing

**This principle stops the LLM from rebuilding, from the floor up, things that already exist.** Most architectures you'll be asked for have been implemented thousands of times — battle-tested, documented, often free, sitting in a public repo or gist. Find and evaluate those before proposing to build anything. Reason from first principles to build from scratch only when the existing options are poorly built, expensive, sluggish, or genuinely don't exist.

## The motivating failure

A user asks the LLM for a system — a chat bridge, an orchestration layer, a second-brain setup, whatever. The LLM runs a shallow search (or none), decides the concept is "interesting," and starts designing a bespoke build from first principles. Meanwhile the exact architecture is taught in popular tutorials, implemented in well-starred repos, and the user has *already copied a working version* of it.

The LLM has just volunteered to spend hours rebuilding what the user could clone in minutes — and the rebuild will be less battle-tested than the thing it replaced. That waste — reinventing a solved problem — is the failure this principle exists to close.

## What "reuse before reinventing" means

The order of operations matters:

1. **Search first, always.** Before designing or building, look for existing solutions — repos, gists, packages, established patterns, the canonical thing practitioners already run. This is step one, not a courtesy search after you've already decided to build.
2. **Evaluate, don't just adopt.** Read the candidates. Find the weakest link. Find what doesn't fit *this* use case. A found solution is a starting structure, not gospel.
3. **Use them as building blocks and reason up.** Take the ready-made structure, decompose it, keep what fits, discard what doesn't, make it modular, personalise. Build on top, not from the floor.
4. **Structure first, details second.** If the structure already exists, the hard part is done. Lift the structure; spend your effort only on personalising it. That is where the speed comes from.

## The judgement call

Deciding *when to stop researching and reason from first principles instead* cannot be hard-coded. Research is the default opening move; building from scratch is the exception, justified only when the existing options are poorly built, expensive, sluggish, or absent. Knowing which situation you're in — "this is solved, go find it" versus "everything out there is bad, build it" — is the judgement the principle asks the model to exercise. When you do choose to build from scratch, state explicitly *why* the existing options fail. That justification is required, not optional.

## The analogies

- **The Lego city.** Building a city brick-by-brick takes forever. With pre-made buildings and roads, you arrange and personalise — a fraction of the time, the same result.
- **The chef.** A chef who invents every dish from scratch per order is out of business within days. A real chef works from a menu of pre-assembled recipes and personalises each to the diner's taste. The recipe is pre-built structure; the work is the personalisation.

## How to apply

On any "can we build / should we build X" request:

1. **Search first.** The first action is a pass for existing solutions. Name the candidates before proposing an architecture.
2. **Report the landscape.** Present what exists, what's strongest, and the weakest link, before recommending build-versus-adopt.
3. **If adopting:** identify the structure to lift and the personalisation needed.
4. **If building from scratch:** state explicitly why the existing options fail (poor, expensive, slow, or absent). No bespoke build without that justification.
5. **Never call a well-trodden architecture "novel" or "interesting"** until you've checked whether it's a solved problem.

## Where this applies

- **System architecture** — orchestration, pipelines, bridges, auth, storage. Almost always solved already.
- **Boilerplate and scaffolding** — project setup, config, CI. Templates exist.
- **Algorithms and data structures** — use the library before writing your own.
- **Workflows and processes** — the popular pattern is popular for a reason; start there.
- **Integrations** — SDKs and adapters usually exist; don't hand-roll the protocol.

## Anti-pattern: reinventing by default

The opposite of this principle is designing a bespoke system, or starting to build, before doing the search — and treating a common pattern as a fresh invention. It feels productive. It produces a weaker, slower-to-build version of something that already existed. First-principles thinking is a powerful tool, but as a *default build strategy* it is expensive waste.

## Sister principle: sanity-check claims

Both principles use first-principles reasoning, but for different jobs:

- **Sanity-check claims** uses first-principles reasoning to *verify* — does this claim hold against the real constraints?
- **Reuse before reinventing** governs the *build approach* — research and adopt before you invent.

First-principles *reasoning* (to verify claims and judge whether a found solution fits) is always on. First-principles *building from scratch* is the exception. See the `sanity-check-claims.md` principle.

## How to install this principle

Copy this file into your LLM's standing-rules config. Replace the worked failure with one from your own domain. The principle is general; the example should be specific to where you'll use it.

This file has been intentionally left vague about your domain so you can shape it to your use case.
