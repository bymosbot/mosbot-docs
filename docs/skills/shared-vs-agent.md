---
id: shared-vs-agent
title: Shared vs Agent-Specific Skills
sidebar_label: Shared vs Agent-Specific
sidebar_position: 2
---

# Shared vs Agent-Specific Skills

MosBot OS supports two categories of skills, each stored in a different location in the OpenClaw
workspace filesystem.

## Shared skills

**Location**: `/skills/`

Shared skills are available to **all agents**. They live in the root `/skills/` directory of the
OpenClaw workspace.

Use shared skills for:

- Tasks that any agent might need to perform
- Common workflows used across multiple agents
- Organization-wide standards and templates

```
/skills/
├── summarize           ← any agent can use /summarize
├── write-report
├── code-review
└── daily-brief
```

## Agent-specific skills

**Location**: `/workspace-<agent-id>/skills/`

Agent-specific skills are available only to the agent whose workspace they live in. They live inside
an agent's workspace directory.

Use agent-specific skills for:

- Tasks specific to that agent's role
- Skills that reference agent-specific context or tools
- Specialized workflows for a particular agent

```
/workspace-cto/skills/
├── architecture-review ← only the CTO agent can use this
├── code-audit
└── tech-debt-analysis

/workspace-cmo/skills/
├── campaign-brief      ← only the CMO agent can use this
└── market-analysis
```

## How the Skills page organizes them

In the MosBot Dashboard's Skills page, skills are grouped into two sections:

1. **Shared Skills** — all files from `/skills/`
2. **Agent-Only Skills** — grouped by agent, showing each agent's skills from
   `/workspace-<id>/skills/`

## Choosing between shared and agent-specific

| Use shared skills when...                    | Use agent-specific skills when...                    |
| -------------------------------------------- | ---------------------------------------------------- |
| Multiple agents need the same skill          | The skill is tailored to one agent's role            |
| The skill is general-purpose                 | The skill references agent-specific tools or context |
| You want a consistent workflow across agents | You want to customize behavior per agent             |

## Skill naming

Skill names are derived from the filename (without extension). A file named `code-review` becomes
the `/code-review` command.

Keep skill names:

- Lowercase and hyphenated
- Short and descriptive
- Unique within their scope (shared or per-agent)

:::tip If a shared skill and an agent-specific skill have the same name, the agent-specific skill
takes precedence for that agent. :::
