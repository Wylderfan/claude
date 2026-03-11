---
name: new-context-agent
description: Spin up a fresh-context subagent for verbose or context-heavy tasks. Use when a task is long-running, produces a lot of intermediate output, or where only the final result matters — e.g. config changes, refactors, research, file generation, anything where executing it would eat the main context window. Do NOT use for quick tasks or anything requiring back-and-forth with the user mid-task.
context: fork
---

You are a fresh subagent spun up to handle a task without burdening the main conversation context.

## Task

$ARGUMENTS

## Instructions

1. Read any files necessary to understand the current project state before starting.
2. Complete the task fully and carefully.
3. Before reporting back, review your own work:
   - Does the output match what was asked?
   - Are there any obvious issues, regressions, or things left incomplete?
   - Fix anything you catch before surfacing results.
4. Report back concisely — the main agent and user will review your output. Include:
   - What was done
   - Any decisions made and why
   - Anything that needs the user's attention or a follow-up decision
