---
name: report-footer
description: Adds a standard audit footer and run checks to every recurring report or scheduled output (daily digests, weekly summaries, data pulls, monitoring results), so each run shows its sources, period, changes and owner, and a silent failure cannot pass for "nothing to report". Use when creating or editing a scheduled job, report template or cron-driven summary.
metadata:
  author: aline-mercer
  version: "1.0"
---

# Report footer

A report that merely appears cannot be audited. A job that fails quietly looks the same as a job with
nothing to say. This skill adds the same short footer to every run, plus a few checks that turn silence
into a signal.

## When to use

- You are setting up or changing anything that runs on a schedule and produces output for a reader.
- A recurring report has no stated sources or period, or nobody can tell whether last night's run happened.

## The footer

Put these lines at the bottom of every output, in the same order every time:

```markdown
---
Sources: <every file, sheet, API or system used, with version or export time>
Period: <exact start and end, with time zone — not "last week">
Changes since last run: <new source, changed definition or filter, or "none">
Owner: <a named person or role to ask>
Review date: <when this report itself will next be reviewed>
Cannot tell you: <optional — the main limit of this report>
Run: <run id or timestamp> · items <n> · status <ok | partial: what failed>
```

Rules:

- **Sources** name the actual inputs used in *this* run, not the ones intended.
- **Period** uses absolute dates. Relative words drift when the report is read later.
- **Changes** is never left blank. Write "none" when nothing changed.
- **Run** shows partial failures, such as "2 of 3 sources answered". Never present a partial run as a full one.

## Run checks (add them to the job itself)

1. **Expected arrival.** Write down when the output should exist, and who notices if it does not.
2. **Empty output is decided in advance.** Either empty means failure, or empty is normal for a stated reason.
3. **Sanity range.** Give the main figure an expected range. Outside the range, flag the output instead of
   sending it as normal.
4. **Count check.** Give an expected item or row count, or compare it with the previous run. A large swing
   gets a line in "Changes".
5. **Proof of life.** The output always carries the `Run:` line, even when there is nothing else to say.
6. **Review date.** Put the review date on the calendar. Retire jobs nobody reads: tell the readers, do a
   last run, pause the schedule, revoke the job's access, then archive.

## Steps

1. Find the template, script or prompt that produces the output.
2. Add the footer, filled from real run variables. Never hard-code values.
3. Add the run checks to the job, and make the job exit non-zero or mark its status `partial` when they fail.
4. Run the job once and read the footer back against the real inputs.

## Example

```markdown
---
Sources: orders.csv export 2026-03-02 06:00 UTC; refunds API v2
Period: 2026-02-23 00:00 → 2026-03-01 23:59 UTC
Changes since last run: refunds now include partial refunds (new filter)
Owner: Finance ops (on-call: rotation sheet)
Review date: 2026-04-01
Cannot tell you: chargebacks still in dispute
Run: 2026-03-02T06:05Z · items 1,284 · status ok
```

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
