---
name: new-skill
description: Scaffold a new Claude Code skill from the template. Use when the user wants to create a new skill or slash command.
disable-model-invocation: true
allowed-tools: Bash, Read, Write
---

Scaffold a new skill named: $ARGUMENTS

## Steps

1. If $ARGUMENTS is empty, ask the user for the skill name before continuing.

2. Create the skill directory:
   ```
   mkdir -p .claude/skills/$ARGUMENTS
   ```

3. Fetch the skill template:
   ```
   curl -fsSL https://raw.githubusercontent.com/Wylderfan/claude/main/SKILL.md -o .claude/skills/$ARGUMENTS/SKILL.md
   ```

4. Ask the user:
   - What should this skill do? (one sentence — used for `description` and auto-invocation)
   - Who can invoke it — user only, Claude only, or both?
   - What are the steps Claude should follow?

5. Fill in the template with the user's answers:
   - Set `name` to $ARGUMENTS
   - Set `description`
   - Set the appropriate invocation flag (or remove both for default)
   - Remove unused frontmatter options and the comment block
   - Fill in the Steps and Output sections

6. Show the completed skill to the user for review.
