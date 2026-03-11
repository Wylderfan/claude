---
name: new-project
description: Initialize Claude Code for a new project. Fetches CLAUDE.md from the template repo and fills in project-specific details. Use when starting a new project or when asked to set up Claude Code.
disable-model-invocation: true
allowed-tools: Bash, Read, Write
---

Set up Claude Code for this project.

## Steps

1. Fetch the CLAUDE.md template:
   ```
   curl -fsSL https://raw.githubusercontent.com/Wylderfan/claude/main/CLAUDE.md -o CLAUDE.md
   ```

2. Ask the user for:
   - A short project description (what it is, what it does, current stage)
   - Build command
   - Test command
   - Lint/format command (or "none" to skip)

3. Fill in the `Project Overview` comment and `Build Commands` block in `CLAUDE.md` with the user's answers. Remove placeholder comments.

4. Create the skills directory:
   ```
   mkdir -p .claude/skills
   ```

5. Confirm setup is complete. Let the user know they can scaffold a new skill anytime with `/new-skill <name>`.
