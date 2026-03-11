# Claude Code Templates

Minimal templates for getting Claude Code set up consistently across projects.

- **`CLAUDE.md`** — drop into any project to give Claude Code your conventions
- **`SKILL.md`** — starting point for writing a new custom skill

---

## What is CLAUDE.md?

`CLAUDE.md` is a file Claude Code reads automatically when it starts in a project directory. It tells Claude your build commands, code style, and workflow rules so you don't have to repeat yourself.

The template here has sensible defaults pre-filled. You only need to add your project-specific details.

## What is a skill?

A skill is a reusable prompt you can invoke with a slash command (e.g. `/gen-test`, `/pr-check`). Skills live in `.claude/skills/<name>/SKILL.md` inside your project, or in `~/.claude/skills/<name>/SKILL.md` to make them available globally across all projects.

`SKILL.md` is a template for writing one. Every option in the frontmatter is documented inline.

---

## Getting the files

### Clone the repo

```bash
git clone https://github.com/Wylderfan/claude.git
```

### Or grab individual files with curl

```bash
# CLAUDE.md template
curl -O https://raw.githubusercontent.com/Wylderfan/claude/main/CLAUDE.md

# SKILL.md template
curl -O https://raw.githubusercontent.com/Wylderfan/claude/main/SKILL.md
```

---

## Using CLAUDE.md in a new project

1. Copy `CLAUDE.md` into your project root:
   ```bash
   cp CLAUDE.md /path/to/your/project/
   ```

2. Fill in the placeholders:
   - `Project Overview` — what the project is and its current stage
   - `Build Commands` — your actual build, test, and lint commands

3. Adjust or remove any style/workflow rules that don't apply.

That's it. Claude Code picks it up automatically on the next run.

---

## Using SKILL.md to create a new skill

1. Create the skill directory in your project:
   ```bash
   mkdir -p .claude/skills/your-skill-name
   cp SKILL.md .claude/skills/your-skill-name/SKILL.md
   ```
   Or globally (available in all projects):
   ```bash
   mkdir -p ~/.claude/skills/your-skill-name
   cp SKILL.md ~/.claude/skills/your-skill-name/SKILL.md
   ```

2. Open the file and fill in:
   - `name` — the slash command (e.g. `gen-test` → `/gen-test`)
   - `description` — when Claude should use it
   - The steps and output sections
   - Remove the comment block and any unused frontmatter options

3. Invoke it with `/your-skill-name` or let Claude auto-invoke it based on the description.

---

## Frontmatter quick reference

| Field | Effect |
|---|---|
| *(omit invocation flags)* | User and Claude can both invoke |
| `disable-model-invocation: true` | User-only — good for side effects (commit, deploy, send) |
| `user-invocable: false` | Claude-only — good for background knowledge Claude applies silently |
| `allowed-tools: Read, Grep` | Restrict which tools the skill can use |
| `context: fork` | Run in an isolated subagent |

### Dynamic context injection

Prefix a shell command with `!` to inject its output before the skill runs:

```markdown
- Current branch: !`git branch --show-current`
- Staged files: !`git diff --cached --name-only`
```

### Arguments

Use `$ARGUMENTS` anywhere in the skill body to reference what the user passed:

```
/gen-test src/auth.py   →   $ARGUMENTS = "src/auth.py"
```
