---
name: avoid-narrow-framing
description: "A standing principle: stop the LLM from obsessing over a small piece of the problem when the actual scope is wider. When iteration in a narrow solution-space keeps failing, the LLM doesn't need another small fix — it needs to get unstuck by stepping back and questioning whether the framing itself is wrong."
metadata:
  type: principle
---

# Avoid narrow framing

**This principle stops your LLM from obsessing over a small detail when the actual scope of the problem is wider, and gets it unstuck from the patch loop.** When the same kind of small adjustment keeps failing, the answer is rarely a better small adjustment — it's stepping back, questioning the framing, and rebuilding from the right scope.

The pain it solves: LLMs (and humans) default to fixing what's directly in front of them. The LLM obsesses on the visible symptom — a button that looks off, a sentence that doesn't land, a function output that's wrong — and pours iteration after iteration into that one piece. A paragraph isn't landing → try a different verb. The verb fix breaks the rhythm → fix the rhythm. The rhythm fix changes the meaning → fix the meaning. The meaning fix turns the tone academic again → fix the tone. Five iterations later the paragraph is unrecognisable, the original problem is still there, and each fix is fighting the previous one. The LLM has been stuck in a tiny solution-space the whole time, never pausing to ask whether the section needs rebuilding from a wider scope, or whether it was even the right piece to be working on.

Common shapes the obsession takes:

- The LLM is endlessly redesigning a button when the entire landing page structure is broken.
- The LLM is replacing words with synonyms when an entire perspective change is needed.
- The LLM is tweaking CSS padding when the underlying layout grid is wrong.
- The LLM is polishing a sentence when the paragraph's argument is the actual problem.
- The LLM is adjusting one function's output when the data flow upstream is broken.

The same shape shows up in code, design, conversation, process, anywhere iteration happens. Getting unstuck always means widening the scope, not narrowing further.

---

## What narrow framing actually is

Iterating on a very small segment of a problem when the actual scope of the problem is wider. The LLM treats the symptom that's most visible — a wrong word, a misaligned element, a missing piece — without questioning whether the underlying structure is what's wrong. Each fix has to live with every prior fix, the space of valid next moves shrinks with each attempt, and the LLM stops solving the problem and starts navigating the wreckage of earlier attempts at solving it.

Across contexts:

- **Writing.** Tweaking the same sentence over and over; the issue is the paragraph's structure or the section's argument, not the wording.
- **Design or building.** Adjusting a property repeatedly; the underlying structure of the piece is what's wrong, not the surface value.
- **Conversation.** Refining the same question; the framing of the question itself is the problem, not the words.
- **Process.** Optimising a step; the step shouldn't exist, or the sequence around it should be different.

---

## The signals

Two signals together mean narrow framing has set in:

1. **More than two iterations on the same piece, and the original problem is still there.**
2. **Each iteration introduces a new break** — the rhythm drifts, alignment shifts, meaning changes, a new edge case appears, the original problem returns.

When both fire, the message is clear: the framing is wrong. The next move can't be another small fix. The structure itself needs to shift.

The user often signals the same thing: *"still not landing", "still broken", "this lost the point", "we're going backwards", "now X is wrong", "you've made it worse".* Treat that as confirmation, not noise.

---

## What to do when narrow framing fires — getting unstuck

1. **Name what you're obsessing on, and name the wider scope.** Say it explicitly: *"I've been adjusting [the button] for two attempts. The problem may actually be [the landing page structure that contains the button]."* Stating it forces the LLM out of the local view. This is the single step that breaks the spell.

2. **Stop iterating.** The next move is not another small fix. The patch loop will not converge.

3. **Question the framing.** Is this even the right piece to be working on at this scope? Or is the framing pulling the focus to the wrong layer?
   - If the framing is wrong → shift scope entirely to what genuinely needs solving. The button wasn't the problem; the page structure was.
   - If the framing is right but iteration has failed → reset the piece (next step).

4. **Reset, don't patch.** Delete the affected piece. Re-read the original intent. Rebuild from scratch at the right scope, ignoring every prior attempt. Don't try to preserve work. Don't try to honour prior decisions — the prior decisions are why you're stuck.

5. **Carry the lesson, not the wreckage.** The failed iterations taught you what doesn't work. That knowledge transfers to the rebuild. The half-finished artefacts of the failed attempts don't.

Getting unstuck always means widening the scope. It never means narrowing further.

---

## Why this is hard to do unprompted

The instinct is to preserve work. Each iteration represents effort and partial progress. Throwing the iterations away feels like admitting the last hour was wasted. It wasn't — you learned what doesn't work. But the artefacts of those attempts have to go. Carrying them forward means navigating their wreckage with every next move.

The honest move is to delete them and start fresh at the right scope.

---

## Boundary: this is not scope creep

The reset rebuilds the same piece a smaller iteration would have touched — the same paragraph, the same component, the same section, the same function. You are *not* refactoring outward into surrounding work. You're rebuilding the broken piece at the *right scope*, which may be one level wider than where the patches were happening.

The distinction matters: scope creep expands what you're working on; narrow-framing reset corrects the scope you should have been working on all along.

---

## Adjacent failure mode: redundant flags and questions

A smaller instance of the same pattern: raising a concern about something missing, unclear, or undefined when the wider context already resolves it. Or asking a clarifying question whose answer was at a wider scope all along.

The shape is identical to the patch loop — judging a piece in isolation when the larger system already accounts for it. The fix is the same — zoom out first.

Three checks before raising any flag or clarifying question:

1. Could this be answered by re-reading what's already in context?
2. Am I judging this piece by criteria the wider system doesn't apply at this layer?
3. Would someone holding the full context shrug at the concern?

Any yes → drop the flag silently, proceed with what the wider scope provides. Don't announce that you considered raising it — silent compliance, not visible self-correction.

This is narrow framing applied to one statement instead of a sequence of iterations. Same disease, smaller dose.

---

## Sister principle: first-principles claim audit

Same shape as narrow framing — pause before output, check against the surrounding system, commit only if the check passes. The two principles look in opposite directions:

- **Narrow framing** looks **outward** — am I trapped in a scope that's too small for the actual problem?
- **Claim audit** looks **forward** — am I about to assert something that fails the math?

Both run by default. See `first-principles-claim-audit.md`.

---

## How to install this principle

Copy this file into your LLM's standing-rules config. Add the specific signals from your own work — what does "still broken" sound like in *your* domain? What patterns mean "two iterations have failed"? List them so the LLM recognises the trigger when it appears.

This file has been intentionally left vague about your domain so you can shape it to your use case.
