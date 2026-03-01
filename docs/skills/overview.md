---
id: overview
title: Skills Overview
sidebar_label: Overview
sidebar_position: 1
---

# Skills

Skills are reusable instruction files that agents can invoke as commands. They define how an agent
should perform a specific task — from transcribing audio to writing code reviews to generating
reports.

## What is a skill?

A skill is a Markdown file with YAML frontmatter that describes:

1. **What the skill does** (metadata in frontmatter)
2. **How to do it** (instructions in the Markdown body)

When an agent receives a command that matches a skill, it reads the skill file and follows the
instructions.

### Example skill

```markdown
---
name: summarize
description: Summarize a document or conversation into key points
---

# Summarize

Read the provided content carefully and produce a concise summary.

## Output format

- Start with a one-sentence TL;DR
- Follow with 3–5 bullet points covering the key points
- End with any action items or decisions made

## Guidelines

- Be concise — aim for 20% of the original length
- Preserve important numbers, dates, and names
- Use plain language
```

## How agents use skills

In OpenClaw, skills are invoked as native commands. When an agent receives a message like
`/summarize`, it:

1. Looks up the `summarize` skill file
2. Reads the instructions
3. Executes the task according to those instructions

Skills can be invoked by users via chat (e.g. Telegram) or by other agents in multi-agent workflows.

## Skills in the MosBot Dashboard

The **Skills** page in the dashboard provides a visual browser for all skills across your OpenClaw
installation. You can:

- Browse shared and agent-specific skills
- View skill content with rendered Markdown
- Create and edit skills directly in the browser
- Search skills by name or description

## Types of skills

MosBot OS supports two types of skills:

| Type                      | Location                  | Available to    |
| ------------------------- | ------------------------- | --------------- |
| **Shared skills**         | `/skills/`                | All agents      |
| **Agent-specific skills** | `/workspace-<id>/skills/` | That agent only |

See [Shared vs Agent-Specific Skills](./shared-vs-agent) for details.

## Next steps

- [Shared vs Agent-Specific Skills](./shared-vs-agent)
- [Creating Skills](./creating-skills)
- [Skill File Structure](./skill-structure)
- [Example Skills](./examples)
