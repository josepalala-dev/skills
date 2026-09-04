---
name: save-session-in-caveman
description: Capture compact session state before switching tasks or ending a session. Save temporary human-readable session breadcrumbs to knowledge/sessions/ for fresh-session handoff.
---
# /save-session-in-caveman

Save the **minimum useful state** needed to resume work later.

## Rules

* Write ONLY to `knowledge/sessions/<YYYYMMDD-HHMM>-<slug>.md`.
* Never write sessions to `.opencode/`.
* Inspect real repo state; never invent.
* Derive `<slug>` from the session's main topic or outcome.
* Prefer updating/consolidating an existing checkpoint for the same task.
* Keep ≈30 lines max.
* Bullets only. Terse. No narrative.
* Capture reusable discoveries, decisions, and gotchas.
* Do not silently promote knowledge into `knowledge/agents/`, `knowledge/patterns/`, or `knowledge/rules/`.

## Inspect

```bash
git branch --show-current
git rev-parse --short HEAD
git status --short
git log -5 --oneline
```

## Write

```markdown
# Checkpoint: <slug>

- Task: <≤10 words>
- Branch: <branch> @ <sha> (<ahead/behind>)
- Git: <important changes/untracked>

- Done:
  - <fact>
  - <fact>

- Decisions:
  - <decision>

- Knowledge:
  - <reusable discovery>

- Next: <one imperative action>

- Gotchas:
  - <warning>

- Promote:
  - <knowledge path, if applicable>
```

Omit empty sections.

## Knowledge test

Capture information future work would otherwise need to rediscover:

* architecture/pattern
* project rule
* implementation discovery
* testing/deployment behavior
* important decision
* trap/gotcha

Do NOT record obvious activity or conversational history.

## Handoff

Report:

`Checkpoint saved: knowledge/sessions/<file>`

Then:

* `/compact` = shrink current context.
* Checkpoint = preserve external knowledge.
* New OpenCode sessions do **not** automatically load the checkpoint; explicitly read/paste it when needed.
