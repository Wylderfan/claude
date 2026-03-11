# SKILLS.md

A blueprint and registry for custom Claude Code skills in this repo.

---

## What is a Skill?

A skill is a reusable prompt template that Claude Code can invoke via a slash command (e.g., `/commit`, `/review-pr`). Skills live in the `.claude/` directory of a repo or globally in `~/.claude/`. This file tracks the skills maintained here, their purpose, and their trigger conditions.

---

## Skill File Format

Each skill is a Markdown file with YAML frontmatter:

```markdown
---
name: skill-name
description: One-line description — shown in the skill picker
---

The prompt that Claude will execute when this skill is invoked.
Use $ARGUMENTS to capture user-provided arguments.
```

**Placement:**
- Project-scoped: `.claude/skills/<name>.md`
- Global (available in all projects): `~/.claude/skills/<name>.md`

---

## Skill Registry

| Skill | Scope | Trigger | Description |
|-------|-------|---------|-------------|
| *(none yet)* | — | — | — |

Add rows here as skills are created.

---

## Guidelines for Writing Skills

1. **One job** — a skill should do exactly one thing well
2. **Composable** — skills can call other skills, but avoid deep nesting
3. **Documented trigger** — be explicit about when Claude should invoke the skill automatically vs. when the user must call it manually
4. **Tested** — verify the skill works in an isolated project before adding to the registry
5. **Versioned** — commit skill changes with a message explaining what changed and why

---

## Skill Ideas Backlog

Use this section to capture skill ideas before implementing them:

- `new-project` — scaffold a new project directory with CLAUDE.md from template
- `phase-plan` — break a large task into small, reviewable phases
- `pr-checklist` — run a pre-PR review against project conventions before pushing

---

## Related Resources

- Claude Code skill docs: https://docs.anthropic.com/claude-code (check for latest)
- Skills in this repo: `skills/`
- Global skills: `~/.claude/skills/`
