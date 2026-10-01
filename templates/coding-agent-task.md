# Coding agent task

Written for: a coding agent making a change in a repository, and for you as its reviewer.
Use it when: you hand a code change to a tool that edits files, runs commands or makes commits.

> Guidance lines start with `>`. Delete them before you send.
> The fix for a messy run is rarely a better prompt. It is somewhere to put the work (a branch), small steps (commits) and a way back (a rollback).

## 1. Task

- Task name: ____
- Repository and path: ____
- Base branch: ____
- New branch, named for the task: ____ (for example `add-csv-export`, not `agent-work`)
- Date and owner: ____

## 2. Goal and context

- What should be true when this is done: ____
- Why it matters, in a sentence: ____
- Where to look first (files, directories, documents): ____
- Related issue, ticket or earlier change: ____
- Behavior that must not change: ____

## 3. Commands, exactly

> Write the real commands. Do not make the agent guess how your project builds and tests.

- Install or set up: ____
- Build: ____
- Run all tests: ____
- Run one test or one file: ____
- Lint or format check: ____
- Start locally, if needed: ____

## 4. Start state

> If the base branch was already red before the agent started, nobody can tell whose failure it is afterwards.

- [ ] My working tree is clean. My own uncommitted work is committed or stashed
- [ ] The base branch is up to date
- [ ] I ran the full test command on the base branch before starting
- Result of that run: ____
- Failures that were already there, listed so they are not blamed on this task: ____

## 5. Plan first

- [ ] Before editing, post a plan: the files you expect to change, the steps in order, and the risks
- [ ] Wait for my reply: ____ (approve, change, or proceed if there is no answer by ____)

## 6. Tests first

- [ ] Write or extend the tests before the change, in their own commit
- [ ] Show that the new tests fail for the right reason before the change, and pass after it
- Cases to cover: ____
- Edge cases to cover: an empty input, the largest input, a repeated item, ____

For a refactor ("clean this up, but do not change behavior"), pin down today's behavior first:

- [ ] Choose the seams: the functions or endpoints whose behavior must not change: ____
- [ ] Record real outputs for a set of inputs, odd ones included, by running them against the untouched code
- [ ] Only then change the code. The recorded outputs are the specification
- [ ] If a recorded output has to change, stop and tell me which one and why

## 7. Commit rules

- One concern per commit. Tests in their own commit
- Each message says what changed and why
- Small commits: at most about ____ files each. If more, split it
- No unrelated fixes, formatting changes or renames mixed in. List them for me instead
- Do not rewrite shared history. Do not force-push

## 8. Scope

- Files and directories you may change: ____
- Files and directories you must not change: ____
- New dependencies: [ ] not allowed  [ ] allowed if listed with a reason first: ____
- Configuration, build and pipeline files: [ ] do not touch

## 9. Permissions

> Grant access, not secrets. No credentials in this brief or in the repository.

May do on its own:

- Edit files in scope, run the commands in section 3, commit and push to the task branch

May suggest, and I decide:

- ____

Must never:

- Push to the main branch, merge its own branch, or rewrite shared history
- Deploy, publish, or run anything against production
- Read, print or write real credentials, tokens or personal data
- Delete data, branches or files outside the task branch

## 10. Dry run and rollback

> For anything that changes data, configuration or a live system. Write the change and its reverse together.

- [ ] Every change has a written way back: ____ (a revert, a reverse script, a restore point)
- [ ] Scripts that change data have a dry-run mode that prints what would change without changing it
- [ ] The first run happens on a copy or a test environment: ____
- [ ] The verification checks are written before the run: ____ (counts, totals, spot lookups, expected state)
- [ ] Any run against something real stays with a person: ____
- Rollback trigger, decided now: if ____ then roll back, without waiting to discuss it
- Who can pull the trigger: ____

## 11. Stop conditions

Stop and ask, instead of continuing, if:

- [ ] The baseline is red in a way not listed in section 4
- [ ] A test needs to change in a way the plan did not mention
- [ ] The work needs a file outside section 8
- [ ] It would take more than ____ commits or ____ files
- [ ] Two instructions here conflict, or something is unclear
- [ ] You have gone ____ rounds without the tests passing
- [ ] You are about to do something that cannot be undone

When you stop, report what you did, what you found, and the question you need answered.

## 12. Definition of done

- [ ] The tests in section 3 pass, and the output is shown
- [ ] Only files in scope changed
- [ ] ____ (documentation, changelog or comments updated)
- [ ] Follow-up ideas are listed, not done

## 13. Report back

> Ask for this shape. It is what you will review.

- Branch name and base commit
- The commits in order, one line each: what and why
- The commands run, with results
- The files changed, and anything you did not do
- Assumptions made
- Risks, and things to look at carefully
- Follow-ups you noticed

## 14. How I will review (reviewer's side)

- [ ] Read the history from oldest to newest, tests first
- [ ] Each commit makes sense alone, and the checks pass after each logical group
- [ ] The diff matches the report
- [ ] If one commit is wrong, ask for that commit to be redone and leave the others, or revert it
- [ ] Merge: [ ] squash (the history is noise)  [ ] keep the commits (the history tells a story)
- [ ] Delete the branch after merging
