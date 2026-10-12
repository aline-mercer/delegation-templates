---
name: long-task-checklist
description: Plans and runs a long or unattended task (hours, overnight or across several sessions) so it can be checkpointed, resumed after an interruption and audited at the end. Use before starting work that will outlast one sitting, when a run may hit usage limits or restarts, or when the user says "keep going while I'm away", "run this overnight" or "pick up where you left off".
metadata:
  author: aline-mercer
  version: "1.0"
---

# Long-task checklist

A long task fails differently from a short one. It drifts from its goal, it quietly widens its scope, or it
stops halfway and nobody can tell where it stopped. This checklist adds a written plan, regular checkpoints
and a resume point.

## When to use

- Work that will take more than about an hour, or more than one session or context window.
- Work that runs while the user is away, or that may be cut off by a usage limit, a crash or a restart.
- Any batch of many similar items, such as files, records, pages or tickets.

## Before you start

1. **Write the goal and the definition of done.** Make them checks someone else could verify.
2. **Set the budget.** Decide the wall-clock time, the spending, the usage or tokens allowed, and the
   number of attempts per step. Write down what happens when the budget runs out (stop and report is the default).
3. **Split the work into checkpointed units.** Each unit should be small enough to redo cheaply, with a
   visible result: a commit, a file, a row count.
4. **Create a progress file** (for example `PROGRESS.md`) next to the work. Use the template below.
   The progress file, not your memory, is where the state lives.
5. **Write the stop conditions now.** Stop on a missing input, a red baseline, an instruction conflict,
   anything irreversible or out of scope, the same error twice in a row, or a budget at 80%.
6. **Record the start state.** Note the branch and commit, the input versions and counts, and any failures
   that already exist, so they are not blamed on this run later.

## While it runs

- After each unit, update the progress file *before* starting the next unit. Record what is done, its
  evidence, what is next, and any decisions you made.
- Commit or save in small steps. Never leave a large unsaved diff in place across a checkpoint.
- If you are blocked on one unit, park it in the file with the reason and move on to independent units.
  Do not wait.
- Do not widen the scope. List new ideas under "Follow-ups" instead of doing them.
- Re-read the goal every few units. If the work has drifted, stop and say so.
- Silence is not success. If the run reports on a schedule, a missed report means it failed until proven otherwise.

## Resuming after an interruption

1. Read the progress file first, before any code or chat history.
2. Verify the last "done" unit really is done. Check its evidence, such as the commit, file or count.
3. Continue from "Next". Do not restart from the beginning, and do not redo verified units.

## Finishing

- Check every item of the definition of done and attach the evidence.
- Write the final report: what was done, what was not done and why, the decisions made, the follow-ups,
  and how to undo it.
- Clean up. Remove temporary files and branches, stop schedules nobody needs, and revoke access granted
  only for this task.

## Progress file template

```markdown
# PROGRESS — <task name>
Goal: ____
Done means: ____
Budget: time ____ · spend ____ · attempts per step ____
Started: <date time tz> at <branch/commit or input version>
Pre-existing problems: ____

## Units
| # | Unit | State (todo/doing/done/parked) | Evidence | Note |
|---|---|---|---|---|
| 1 | ____ | todo | | |

## Decisions
- <time> chose ____ because ____

## Parked
- <unit> — blocked by ____ — needs ____

## Next
<the exact next action, written so a fresh session can start from it>

## Follow-ups (not done)
- ____
```

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
