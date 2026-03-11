# CLAUDE.md

This file provides guidance to Claude Code when working in this repository. This repo is the source of truth for personal Claude Code infrastructure — skills, memory, configuration, and shared tooling across all projects.

## Repository Purpose

Maintain and version-control personal Claude Code infrastructure:
- Custom skills (`skills/`)
- Shared CLAUDE.md templates (`templates/`)
- Global configuration and settings
- Documentation for Claude Code workflows

## Code Style

- Use `snake_case` for filenames and variable names
- Minimal comments — explain *why*, not *what*
- Ask before introducing new tools or dependencies
- Keep skills focused and composable — one skill, one job

## Workflow Rules

- Always branch + PR for changes, even small ones
- PRs should be small and reviewable — divide large tasks into phases
- Before implementing anything non-trivial:
  1. Restate your understanding of the task
  2. Ask 1-2 clarifying questions if requirements are ambiguous
  3. Propose the approach before writing code
- When deleting a branch, confirm it's merged first

## Skill Development Guidelines

When writing or modifying skills:
- Skills live in `skills/` and are documented in `SKILLS.md`
- A skill should do one thing well and be reusable across projects
- Include a brief header comment describing the trigger conditions and what the skill does
- Test skills in an isolated context before committing

## Memory Guidelines

- Memory files live in `~/.claude/projects/<project>/memory/`
- Prefer updating existing memories over creating duplicates
- Do not store ephemeral or task-specific context in memory — use tasks or plans instead
- Memory content should be timeless enough to be useful in a future conversation

## Templates

`templates/CLAUDE.md` is the baseline template for new project CLAUDE.md files. When starting a new project, copy and adapt this template rather than writing from scratch.
