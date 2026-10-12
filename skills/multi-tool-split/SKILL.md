---
name: multi-tool-split
description: Splits one task across several AI tools, coding agents or sub-agents (for example one implements while another reviews, or research runs in parallel) with clear boundaries, one owner per unit, a merge plan and a non-author review. Use when a task is too big for one pass, when parallel work would save time, when a second opinion matters, or when the user wants to "use Claude Code and Codex together" or "run several agents on this".
metadata:
  author: aline-mercer
  version: "1.0"
---

# Multi-tool split

Running several tools on one task pays off only when their work does not collide. This skill decides
whether to split, cuts the work into independent units, gives each unit one owner, and plans the merge
before anything starts.

## When to split, and when not to

Split when at least one of these is true:

- The units are genuinely independent, with different files, questions or data, and running them in
  parallel saves real time.
- A second opinion matters. Review by a tool or agent that did not write the work catches what the
  author cannot see.
- Different units need different strengths or access, such as a coding agent, a research tool or a design tool.

Do **not** split when the units share the same files or depend on each other step by step, or when
coordinating would cost more than doing the work. One owner is then better.

## Steps

1. **List the units.** For each one, give its input, its output, and the area it may touch (files,
   directories, documents, records).
2. **Check for overlap.** No two writers on the same file or record. If two units must touch the same
   thing, merge them or put them in order.
3. **Assign one owner per unit.** Choose the tool by strength, cost and the access it already has. Each
   tool runs under your own account and its provider's terms.
4. **Write a brief per unit.** Include goal, inputs, boundaries, done checks and stop conditions (see the
   `handoff-brief` skill). Each brief stands on its own: the receiver cannot see the other briefs or your chat.
5. **Plan the merge before starting.** Decide the order of merging, who resolves conflicts, and which
   checks run after each merge (tests, counts, a full read).
6. **Pick a reviewer who is not the author** for anything that matters.
7. **Track the units in one table** (below) and update it as results arrive.
8. **Read back each result before merging it** (see the `result-readback` skill). Check the load-bearing
   parts yourself; do not relay claims unverified.
9. **Merge in the planned order, then run the full checks once on the combined result.**

## Unit table

```markdown
| Unit | Owner (tool/agent) | Touches | Input | Output | Done check | Status | Reviewed by |
|---|---|---|---|---|---|---|---|
| U1 | ____ | src/api/** | ____ | branch u1 | tests A,B pass | todo | ____ |
| U2 | ____ | docs/** | ____ | docs PR | links resolve | todo | ____ |
```

## Common splits

- **Implement + review:** tool A writes the change on a branch. Tool B reviews the diff against the brief
  and the tests, read-only. You decide.
- **Parallel research:** each tool answers a distinct sub-question with sources. One merge step lays out
  disagreements side by side instead of blending them.
- **Fan-out batch:** split items by a stable key, such as ID ranges. Every tool uses the same brief and
  output format, then one step validates the counts.

## Stop and re-plan if

- two units turn out to need the same file;
- a unit's result changes another unit's input;
- coordination messages outnumber work steps.

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
