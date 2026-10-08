# n8n setup

Two ways to use HeyReagent in n8n. The MCP path is easiest inside an AI agent. The HTTP path works in any workflow.

## Get your key first

1. Sign in at [heyreagent.com](https://heyreagent.com) with your email.
2. Connect LinkedIn on your thread page.
3. Open Menu, then Developers, and press Create a key. Copy it at once. It is shown only once.

## Option A: MCP Client Tool node (for AI agents)

1. Add an MCP Client Tool node to your agent.
2. Endpoint: `https://api.heyreagent.com/mcp`
3. Server Transport: HTTP Streamable.
4. Authentication: Bearer, with your key.

The agent can now call every HeyReagent action as a tool. Give it a recipe prompt and let it work.

## Option B: HTTP Request node (plain API, no agent needed)

Add an HTTP Request node and fill it in per action:

- Method: `POST`
- URL: `https://api.heyreagent.com/v1/actions/<action_name>`, for example `https://api.heyreagent.com/v1/actions/who_went_cold`
- Send Headers: on. Name `Authorization`, value `Bearer YOUR_KEY`.
- Send Body: on, JSON. Paste the action's inputs, or `{}` when it needs none.

Every action's docs page shows the exact call with inputs: [heyreagent.com/docs](https://heyreagent.com/docs).

## Community node

There is also a community node package for HeyReagent: [n8n-nodes-heyreagent](https://github.com/linglistack/n8n-nodes-heyreagent). More n8n guides: [heyreagent.com/n8n-linkedin](https://heyreagent.com/n8n-linkedin).

## Note on schedules

The free plan disconnects LinkedIn after an hour without use, so a workflow on a schedule needs the Connect plan ($29.99/mo), which keeps LinkedIn connected. Details: [heyreagent.com/pricing](https://heyreagent.com/pricing).
