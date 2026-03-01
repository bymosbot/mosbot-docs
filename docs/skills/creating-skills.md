---
id: creating-skills
title: Creating Skills
sidebar_label: Creating Skills
sidebar_position: 3
---

# Creating Skills

You can create skills directly in the MosBot Dashboard or by writing files to the OpenClaw workspace
filesystem.

## Method 1: MosBot Dashboard (recommended)

1. Open the MosBot Dashboard and navigate to **Skills**
2. Click **New Skill** (or the `+` button)
3. Choose the skill type:
   - **Shared skill** — available to all agents
   - **Agent-specific skill** — available to one agent only
4. Enter the skill name (this becomes the command name, e.g. `summarize` → `/summarize`)
5. Write the skill content in the editor
6. Click **Save**

The skill is immediately available to agents.

## Method 2: Write directly to the workspace

Skills are plain files in the OpenClaw workspace. You can create them by writing to the appropriate
directory.

### Shared skill

Write a file to `/skills/<skill-name>`:

```bash
# Via MosBot API
curl -X POST http://localhost:3000/api/v1/openclaw/workspace/file \
  -H "Authorization: Bearer <mosbot-jwt>" \
  -H "Content-Type: application/json" \
  -d '{
    "path": "/skills/summarize",
    "content": "---\nname: summarize\ndescription: Summarize content into key points\n---\n\n# Summarize\n\nRead the content and produce a concise summary..."
  }'
```

### Agent-specific skill

Write a file to `/workspace-<agent-id>/skills/<skill-name>`:

```bash
curl -X POST http://localhost:3000/api/v1/openclaw/workspace/file \
  -H "Authorization: Bearer <mosbot-jwt>" \
  -H "Content-Type: application/json" \
  -d '{
    "path": "/workspace-cto/skills/architecture-review",
    "content": "---\nname: architecture-review\ndescription: Review system architecture and provide recommendations\n---\n\n..."
  }'
```

## Skill naming conventions

- Use lowercase letters, numbers, and hyphens only
- Keep names short and descriptive
- The filename becomes the command name (no extension needed)
- Examples: `summarize`, `code-review`, `daily-brief`, `write-report`

## Testing a skill

After creating a skill, test it by sending the command to an agent:

1. Open a chat with the agent (e.g. via Telegram)
2. Send `/<skill-name>` followed by any required input
3. The agent should execute the skill instructions

## Editing skills

To edit an existing skill:

1. In the dashboard, navigate to **Skills**
2. Find the skill and click on it to open it
3. Click **Edit** (pencil icon)
4. Make your changes
5. Click **Save**

## Deleting skills

To delete a skill:

1. In the dashboard, navigate to **Skills**
2. Find the skill and open it
3. Click **Delete** (trash icon)
4. Confirm the deletion

:::caution Deleting a skill is permanent. Agents that reference the skill will no longer be able to
invoke it. :::
