# claude-tools

Personal Claude Code skills.

## Skills

| Skill | What it does |
|---|---|
| [`mermaid-diagrams`](skills/mermaid-diagrams/SKILL.md) | Mermaid ERDs and DAGs with a green-for-new / gray-for-existing color convention, for PR descriptions and architecture docs. |

## Install

Symlink a skill into your global skills dir to use it everywhere:

```bash
ln -s "$PWD/skills/mermaid-diagrams" ~/.claude/skills/mermaid-diagrams
```

Or copy it into a specific project:

```bash
cp -R skills/mermaid-diagrams /path/to/project/.claude/skills/
```

`.claude/skills/` in this repo symlinks to `skills/`, so the skills are live when working here.
