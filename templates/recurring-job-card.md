# Recurring job card

Written for: you and the helper. Keep one card per repeating job.
Use it when: something runs on a schedule (a report, a data pull, a clean-up, a reminder) and will keep running while you are not looking.

> Guidance lines start with `>`. Delete them when you copy this.
> A job that runs unchecked is a job that stops being checked. The card says who owns it, how to tell it ran, and when to review it.

## 1. The job

- Name: ____
- Purpose in one sentence: ____
- Who reads the output: ____
- Owner: ____
- Helper that runs it: ____
- Status: [ ] active  [ ] paused  [ ] retired
- Started on: ____
- Review the job itself on: ____

## 2. Schedule, worked backwards

> Start from when the reader needs it, then subtract. The last row is the time everything must be in place.

| Step | Time | How you got it |
|---|---|---|
| Reader needs it by | ____ (day, time, time zone) | Set by the reader |
| Minus time for me to review | ____ | ____ |
| Result must be ready by | ____ | Row 1 minus row 2 |
| Minus how long the run takes | ____ | ____ |
| Run must start by | ____ | Row 3 minus row 4 |
| Minus time for inputs to arrive | ____ | ____ |
| Inputs must be in place by | ____ | Row 5 minus row 6 |

- Repeats: ____ (for example every Friday)
- Time zone for every time on this card: ____
- Holidays and dates to skip: ____

## 3. Inputs

- Source, named exactly: ____
- Version or export to use: ____
- Period covered: ____ (exact dates, not "last week")
- Fields, in order: ____
- If the source looks different (columns moved, empty, late): stop and report. Do not guess.

## 4. Output

- Format and shape: ____
- Name pattern: ____ (include the date)
- Saved to: ____
- Sent to: ____

## 5. Footer for every run

> Put these lines at the bottom of every output, in the same place each time. They turn a report that merely appears into one that can be audited.

- Sources: ____ (every file, sheet or system, and which version)
- Period: ____ (exact dates and time zone)
- Changes: ____ (what is different from last time: a new source, a changed definition, a new filter)
- Owner: ____ (who to ask)
- Review date: ____ (when the report itself will be reviewed)
- Optional sixth line, what this report cannot tell you: ____

## 6. Silence is not success

> A job that fails quietly looks the same as a job with nothing to report. Decide in advance how you will tell them apart.

- Expected to arrive by: ____
- If nothing has arrived by then, I will: ____
- Who notices if it stops: ____ (a name, not "everyone")
- An empty output counts as: [ ] a failure  [ ] normal, because ____
- Sanity range for the main figure: between ____ and ____ (outside it, flag it instead of sending it)
- Row count or item count expected: ____
- A check that shows the job ran at all: ____ (for example a "last run" line)
- Weekly spot check: I open ____ and compare one figure with ____

## 7. When it goes wrong

- First response: ____ (retry once, or stop)
- Tell: ____ by ____
- Manual fallback: ____
- Never retry on its own if: ____

## 8. Run log

| Date | Ran on time | Output looked right | Checks passed | Notes |
|---|---|---|---|---|
| ____ | [ ] | [ ] | [ ] | ____ |
| ____ | [ ] | [ ] | [ ] | ____ |
| ____ | [ ] | [ ] | [ ] | ____ |
| ____ | [ ] | [ ] | [ ] | ____ |

## 9. Retiring the job

Work through these in order and write the date on each.

1. Announce it to the people who read the output: ____
2. Do a last run and keep the result: ____
3. Pause the schedule: ____
4. Revoke the access the job used: ____
5. Archive the card, the outputs and the log: ____
6. Delete what you no longer need, after a waiting period of ____: ____
