---
name: result-readback
description: Checks a result returned by a sub-agent, AI tool, coding agent, service or person against the original brief before accepting it or reporting it as done. It verifies claims against evidence, compares the summary with the actual changes, samples by rule and checks scope. Use whenever delegated work comes back, before saying "done", or when a report sounds confident but has not been checked.
metadata:
  author: aline-mercer
  version: "1.0"
---

# Result read-back

A returned result is a claim until someone checks it. This skill reads it back against the brief, by rule
and not by feel, and ends in a clear decision.

## When to use

- A sub-agent, tool, contractor or colleague has returned work.
- You are about to tell the user something is finished, fixed, sent or verified.
- A summary says "all tests pass", "no issues found" or "updated everywhere" without showing evidence.

## Steps

1. **Put the brief and its definition of done next to the result.** If there was no definition of done,
   write one now from the brief, before you look closely at the result.
2. **Decide how much to check, before you look.** Check more as the cost of a mistake rises. Where a single
   error would be costly, as with money, deletions, or anything sent to other people, check every item.
3. **Check the load-bearing claims against evidence.** Open the file, run the test, recount the rows,
   follow the link. A claim with no evidence counts as not done.
4. **Compare the summary with the actual changes.** Read the diff or change list. Are the counts of files
   and items what you expected? Nothing outside the scope was touched, sent or deleted.
5. **For a batch, sample by rule.** Take every Nth item, plus the awkward ones: the longest, the shortest,
   the oldest, the strangest source. Tally problems by kind. A kind that appears twice is probably in the
   rest too.
6. **Check what is missing.** Gaps should be admitted, assumptions listed, and questions asked. A confident
   tone is not evidence.
7. **Decide.** Accept, accept with edits, send back once with specific notes, or reject and take another route.
8. **Record why the result came back if it was not accepted.** A reason that repeats calls for a fix to the
   brief, not to the helper.

## Quick checks by type

- **Code:** the named tests pass and the output is shown. Only files in scope changed. The commits read
  sensibly from oldest to newest. There is a way to undo the change.
- **Research or summary:** at least three claims were traced to an opened source. Names, numbers and
  dates match the inputs. Sources that disagree are shown side by side.
- **Spreadsheet or table:** one total recomputed by hand matches. The row count matches the input. Units
  are consistent. There are no hidden rows or sheets.
- **Message or document draft:** it is still a draft and nothing was sent. Facts and promises match the notes.
- **Translation:** numbers, dates and names match the original. The count of sections matches. Key terms
  are used the same way everywhere.

## Report shape

```markdown
Result: <accept | accept with edits | rework | reject>
Checked: <what, how many, by which rule>
Evidence: <tests run / files opened / counts>
Problems by kind: <kind — count — example>
Scope: <unexpected changes, or "none found">
Rework note (if any): wrong ____ · change ____ · keep ____ · add to brief next time ____
```

Only report something as done or verified when the evidence is in hand. Otherwise say exactly what is
unverified.

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
