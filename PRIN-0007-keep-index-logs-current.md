---
id: PRIN-0007
name: keep-index-logs-current
display_name: "Keep index and log files current after delivering"
type: principle
role: public-export
always_on: true
---

<!-- Generated export of PRIN-0007. Source of truth is the personal SSOT; this is the shareable copy with private references stripped. Don't edit here — edit the source, then regenerate. -->

# PRIN-0007 · Keep index and log files current after delivering

> Installer file. The `## Gist` block is what you copy into your assistant's always-loaded config. The `## Full text` stays in the file, read on demand.

## Gist

After delivering a file, update the index/log files that track it — automatically, no asking. Look for `index.md` (then `log.md`) in the same folder you dropped the file into, then work upward to the project root. For each that exists, add/update the entry in that file's existing schema (newest-on-top, timestamps, `modified:` field, file counts — whatever it already uses). Cascading hierarchies: update every level, leaf to root. Only update logs that already exist; don't scaffold new ones unless asked. Deterministic clerical work — never a question for the human.

## Full text

**Why.** Index and log files are only useful if they stay in sync with reality. A delivered file that isn't logged is invisible to the next session — the whole point of an index is that a future session can pick up without rediscovering. If the user has to remember to say "now update the index", the system leaks. So the update is automatic, part of delivering the file, not a separate request.

**What it covers.** After creating or modifying any file (any extension), look in its folder *and* every parent folder up to the project root for `index.md` and `log.md`. For each that exists, write the entry for what was just delivered.

**Cascading hierarchies.** Some projects keep index/log files at multiple levels — a leaf folder index, a mid-level index, a root master index. When a file lands in a deep folder, update the local index *and* every ancestor index that is supposed to reflect its descendants. Propagate up the tree. A single delivery can touch three or four index files; update all in one pass.

**How to apply.**
1. After the file is written, list the candidate logs: the file's own folder, then walk up to the project root, collecting every `index.md` / `log.md`.
2. For each, read its existing schema and add/update the entry in that exact shape — newest-on-top if that's the convention, ISO timestamps, per-entry fields, `modified:` frontmatter bumped, file counts adjusted.
3. Log decisions only — skip "I verified" / "confirmed working".
4. Never ask whether to update them. It's deterministic clerical work (see PRIN-0005).

**Boundaries.**
- Only update logs that already exist. Don't scaffold a new `index.md` / `log.md` where none is present unless asked — that's a structural decision, not clerical fill-in.
- Respect each file's own format. Different levels can use different schemas; don't homogenise them.
- Surgical-edits discipline still applies: add the entry, bump the counters and `modified:`, don't reflow the rest.

**Anti-pattern.** Delivering a file and stopping — leaving the index stale, or telling the user "you may want to update the index". Asking "should I log this?" Inventing a new entry format instead of matching the existing one. Updating the leaf index but forgetting the root master index in a cascading hierarchy.

**Related:** PRIN-0001 (do the deterministic work), PRIN-0005 (clerical fields are never the human's job), PRIN-0004 (surgical — touch only the entry).
