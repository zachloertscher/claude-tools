# claude-tools

Personal [Claude Code](https://claude.com/claude-code) skills.

| Skill | What it does |
|---|---|
| [`mermaid-diagrams`](skills/mermaid-diagrams/) | Mermaid ERDs and lineage DAGs that color-code new vs. changed vs. untouched, for PR descriptions and architecture docs. |

## mermaid-diagrams

Green for new, amber for changed, gray for untouched — so a reviewer sees the shape of a change before reading a line of the diff.

```mermaid
%%{init: {'themeVariables': {'fontSize':'18px'}, 'flowchart': {'nodeSpacing':50,'rankSpacing':60}}}%%
flowchart LR
    classDef newNode fill:#22c55e,stroke:#15803d,color:#fff
    classDef changedNode fill:#f59e0b,stroke:#b45309,color:#fff
    classDef existingNode fill:#9ca3af,stroke:#4b5563,color:#fff

    subgraph staging[Staging]
        stg_orders["stg_orders"]:::existingNode
        stg_refunds["stg_refunds"]:::newNode
    end

    subgraph intermediate[Intermediate]
        int_orders["int_orders"]:::existingNode
        int_refunds["int_refunds"]:::newNode
    end

    subgraph mart[Mart]
        dim_orders["dim_orders"]:::changedNode
        fact_refunds["fact_refunds"]:::newNode
    end

    style staging fill:#f3f4f6,stroke:#d1d5db,color:#111827
    style intermediate fill:#f3f4f6,stroke:#d1d5db,color:#111827
    style mart fill:#f3f4f6,stroke:#d1d5db,color:#111827

    stg_orders --> int_orders --> dim_orders
    stg_refunds --> int_refunds --> fact_refunds
```

**[See the ERD example and full details →](skills/mermaid-diagrams/)**

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

## License

[MIT](LICENSE) — use it however you like.
