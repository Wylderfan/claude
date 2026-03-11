---
# [REQUIRED] The slash command name. Must be lowercase, hyphens allowed. e.g. "gen-test"
name: skill-name

# [REQUIRED] Primary trigger mechanism — Claude reads ONLY this field to decide whether to invoke.
# All "when to use" context belongs here, not in the body. Be specific and a little pushy:
# Claude tends to undertrigger skills, so include explicit trigger phrases and edge cases.
# e.g. "...use this whenever the user mentions X, Y, or Z, even if they don't explicitly ask for it."
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
- Reference bundled files with relative links: [references/guide.md](references/guide.md)

BUNDLED RESOURCES (for complex skills — create subdirectories as needed):
  scripts/    - Reusable scripts Claude can run instead of rewriting each invocation
  references/ - Docs or guides Claude loads selectively (link from Steps when needed)
  assets/     - Templates or files used in output

SKILL FILE PLACEMENT:
  Project-scoped:  .claude/skills/<name>/SKILL.md
  Global (all projects): ~/.claude/skills/<name>/SKILL.md

WRITING STYLE:
  Explain the "why" behind instructions rather than issuing directives. Claude understands
  reasoning and generalizes better from it than from rigid rules. If you find yourself writing
  ALWAYS or NEVER in all caps, reframe it as an explanation of why the thing matters instead.
-->

## Steps

1. <!-- What should Claude do first? -->
2. <!-- Next step -->
3. <!-- Continue as needed -->

## Output

<!-- What should Claude produce or report when done? -->
