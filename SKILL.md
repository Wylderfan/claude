---
# [REQUIRED] The slash command name. Must be lowercase, hyphens allowed. e.g. "gen-test"
name: skill-name

# [REQUIRED] When Claude should invoke this skill and what it does.
# Be specific — this is how Claude decides whether to auto-invoke.
description: One sentence describing what this skill does and when to use it.

# [OPTIONAL] Invocation control — choose one or omit for default (both user and Claude can invoke).
#   disable-model-invocation: true   → user-only  (use for side effects: deploy, commit, send)
#   user-invocable: false            → claude-only (use for background knowledge Claude applies automatically)

# [OPTIONAL] Restrict which tools this skill can use.
# allowed-tools: Read, Grep, Glob, Bash, Write

# [OPTIONAL] Run in an isolated subagent (good for long-running or read-only analysis).
# context: fork
# agent: Explore   # agent type when forked: Explore, Plan, general-purpose
---

<!-- Delete this comment block when filling in the skill.

TIPS:
- Use $ARGUMENTS to reference anything the user passes: /skill-name some input
- Use !`command` to inject live shell output before the skill runs:
    Branch: !`git branch --show-current`
- Reference bundled files with relative links: [checklist.md](checklist.md)
  Skills can bundle supporting files (templates, scripts, examples) in the same directory.

SKILL FILE PLACEMENT:
  Project-scoped:  .claude/skills/<name>/SKILL.md
  Global (all projects): ~/.claude/skills/<name>/SKILL.md
-->

## Steps

1. <!-- What should Claude do first? -->
2. <!-- Next step -->
3. <!-- Continue as needed -->

## Output

<!-- What should Claude produce or report when done? -->
