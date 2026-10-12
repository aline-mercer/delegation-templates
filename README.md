# delegation-templates

[![skills.sh](https://skills.sh/b/aline-mercer/delegation-templates)](https://skills.sh/aline-mercer/delegation-templates)

Agent skills and fill-in templates for handing work to AI tools, assistants and services.

Hand-offs go wrong in small, predictable ways. The goal stayed in your head, "done" meant one thing to you and another to the helper, or the result came back and nobody knew how to check it. These files put those things on the page: as **agent skills** your coding agent can load, and as **plain templates** for people.

## Agent skills

Each skill is a folder under [`skills/`](skills/) containing a `SKILL.md` ([Agent Skills format](https://agentskills.io/specification)). The skills work on their own and need no particular product.

Install with the [skills CLI](https://github.com/vercel-labs/skills), which supports Claude Code, Codex, Cursor, OpenCode and other agents:

```bash
# list the skills in this repo
npx skills add aline-mercer/delegation-templates --list

# install all of them
npx skills add aline-mercer/delegation-templates

# install one
npx skills add aline-mercer/delegation-templates --skill handoff-brief
```

| Skill | Use it when |
|---|---|
| [handoff-brief](skills/handoff-brief/SKILL.md) | Handing a task to another agent, sub-agent, tool or person who will not have your context |
| [long-task-checklist](skills/long-task-checklist/SKILL.md) | Work will run for hours, overnight or across sessions, and must be resumable |
| [safe-sample-data](skills/safe-sample-data/SKILL.md) | Building fixtures, demos or examples, or masking a real export before sharing it |
| [report-footer](skills/report-footer/SKILL.md) | Setting up a recurring report or scheduled output that someone must be able to audit |
| [multi-tool-split](skills/multi-tool-split/SKILL.md) | Splitting one task across several AI tools or agents without collisions |
| [result-readback](skills/result-readback/SKILL.md) | Delegated work has come back and must be checked before anyone calls it done |

## Templates (for people)

Each template is a plain Markdown file with blanks. `____` is a blank, `- [ ]` is a box to tick, and lines that start with `>` are guidance.

1. Copy the file you need, or open it in your editor.
2. Fill the blanks. Delete the guidance lines and anything that does not apply. A short, complete brief beats a long, padded one.
3. Paste the result into whatever helper you use: an AI chat, an assistant, a scheduling tool, a contractor's inbox, a colleague's message.
4. Keep your filled copy next to the work. You will want it again when the result comes back.

| File | Use it when | Written for |
|---|---|---|
| [templates/handoff-brief.md](templates/handoff-brief.md) | You are handing over a task and will not be watching it | The helper |
| [templates/definition-of-done.md](templates/definition-of-done.md) | A result could look finished without being finished | You and the helper |
| [templates/permission-and-secrets-checklist.md](templates/permission-and-secrets-checklist.md) | Before you give a helper access to anything | You |
| [templates/coding-agent-task.md](templates/coding-agent-task.md) | You are handing a code change to a coding tool | The coding tool, and you as reviewer |
| [templates/review-checklist.md](templates/review-checklist.md) | A result has come back and you must decide whether to trust it | You |
| [templates/recurring-job-card.md](templates/recurring-job-card.md) | A job repeats on a schedule | You and the helper |
| [templates/away-note.md](templates/away-note.md) | You will be unreachable while work keeps moving | Whoever covers for you |
| [templates/decision-log.md](templates/decision-log.md) | You want to remember why you chose what you chose | You, later |

### A sensible order

1. Write the brief and the definition of done before you send anything.
2. Settle permissions before the helper starts, and grant access, not secrets.
3. Review what comes back with the checklist, by rule and not by feel.
4. Give each repeating job a card. Write an away note before an absence.
5. Log decisions on the day you make them.

These are general starting points. For legal, medical, financial or safety-critical work, involve a qualified person as well.

## About

Made by Tutuo, Inc. These skills and templates were drafted by AI and editorially reviewed by AI. They have had no independent human review. Corrections and suggestions are welcome via issues.

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
