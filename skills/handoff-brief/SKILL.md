---
name: handoff-brief
description: Writes a self-contained hand-off brief before work goes to another agent, sub-agent, coding tool, service or person. Use when delegating a task that will run without you watching, when spawning a sub-agent, or when the user asks to "hand this off", "brief someone", "write a prompt for another agent" or "delegate this".
metadata:
  author: aline-mercer
  version: "1.0"
---

# Handoff brief

A hand-off usually fails in a few predictable ways. The goal stayed in someone's head, "done" meant different
things to each side, or the receiver could not tell when to stop. This skill writes a brief that a stranger
can start from.

## When to use

- You are about to give a task to a sub-agent, another AI tool, a coding agent, a service or a colleague.
- The task will take more than a few minutes, or nobody will be watching while it runs.
- The user asks for a "prompt", "brief", "spec" or "instructions" for someone else to follow.

Skip it for one-line requests where the receiver already has all the context.

## Steps

1. **Collect the goal and the reason.** Write one sentence for what is wanted and one for what it is for.
   The reason lets the receiver make sensible choices that nobody spelled out.
2. **Add the context the receiver cannot guess.** That means the audience, the history, what was tried
   before, and any words used in a special way. The receiver has none of your conversation.
3. **List the inputs with their exact locations.** Use paths, URLs or names, and mark each one final or
   draft. If there is a good example, say what to copy from it and what to change.
4. **Split the constraints into fixed, open and out of scope.** Fixed is never changed. Open is the
   receiver's judgment, to be reported back. Out of scope is not done even if it looks helpful.
5. **State the limits.** Give the time or effort allowed, the spending allowed (write "none" if none), and
   the sources the receiver may and may not use.
6. **Specify the output shape.** Give the format, length, structure, where to deliver it, and what goes
   first: the answer, the decision needed, or the main risk.
7. **Write the definition of done as checks.** Each item should be verifiable in minutes, such as "every
   figure traces to a listed source" or "tests X and Y pass and the output is shown". "Good quality" is not a check.
8. **Add stop conditions.** These cover a missing or odd input, conflicting instructions, a limit about to
   be passed, anything irreversible, and anything out of scope.
9. **Set permissions.** Split them into may-do-alone, may-suggest and must-never-touch. Grant access, not
   secrets: never put passwords, keys, tokens or codes into a brief.
10. **Run the stranger test.** Reread the brief as someone with none of your history. Could they start? Fix
    every place where they would have to guess.

If information is missing, ask the user up to three questions in one message. Or proceed on stated
assumptions and list them in the brief.

## Template

```markdown
## Goal
I want: ____
So that: ____

## Context
Background (2–3 sentences): ____
Who uses the result: ____
Tried before: ____
Terms: ____ means ____

## Inputs
| Input | Location | Final/draft |
|---|---|---|
| ____ | ____ | ____ |

## Constraints
Fixed: ____
Open (choose, then tell me what you chose): ____
Out of scope: ____
Limits: time ____ · spending ____ · sources allowed ____ / not allowed ____

## Output
Format ____ · length ____ · deliver to ____ · put first ____
End with: sources · assumptions · what you could not do · questions

## Done means
- [ ] ____
- [ ] ____
Not required: ____

## Check-ins
First report by ____; then every ____. Each report: done / next / blocked / need from me.

## Stop and ask if
- an input is missing or looks different from this brief
- two instructions conflict
- a limit is about to be passed
- the next step cannot be undone
When you stop: what you did, what you found, what you would do next, the question.

## Permissions
May do alone: ____
May suggest, I decide: ____
Never: ____
Access granted (no secrets in this brief): ____
```

## Quality bar

- Short and complete beats long and padded. Delete every section that does not apply.
- Every path, date and number in the brief is exact. Give times with a time zone.
- The brief makes sense on its own. Never write "as discussed" or "the usual way".
- Any example data in the brief is anonymised. Use placeholders in `[square brackets]`.

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
