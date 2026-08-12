# claude-tools

Personal Claude Code skills.

## Skills

| Skill | What it does |
|---|---|
| [`mermaid-diagrams`](skills/mermaid-diagrams/SKILL.md) | Mermaid ERDs and DAGs with a green-for-new / gray-for-existing color convention, for PR descriptions and architecture docs. |

## Install

Copy a skill into your global skills dir to use it in every project:

```bash
cp -R skills/mermaid-diagrams ~/.claude/skills/
```

Or into a single project:

```bash
cp -R skills/mermaid-diagrams /path/to/project/.claude/skills/
```

Claude Code picks up skills from `~/.claude/skills/` (global) and `.claude/skills/` (per-project). No restart needed.
