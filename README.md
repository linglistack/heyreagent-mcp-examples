# heyreagent-mcp-examples

Copy-paste setups and ready-to-use prompt recipes for the HeyReagent LinkedIn MCP server.

HeyReagent is a hosted MCP server for your own LinkedIn account. One address, nothing to install:

`https://api.heyreagent.com/mcp`

Sign in at [heyreagent.com](https://heyreagent.com), connect LinkedIn once, and your AI app can read your inbox, send messages and invitations, search people, and work with posts. Free to start. Not made by, affiliated with, or endorsed by LinkedIn.

## Setup

Pick your app. Each guide is copy-paste.

- Claude Code: [setup/claude-code.md](setup/claude-code.md)
- Cursor: [setup/cursor.md](setup/cursor.md)
- ChatGPT: [setup/chatgpt.md](setup/chatgpt.md)
- n8n: [setup/n8n.md](setup/n8n.md)
- Claude (web) and Meta Muse: same MCP address. Follow the official steps at [heyreagent.com/docs](https://heyreagent.com/docs).

Full official docs: [heyreagent.com/docs](https://heyreagent.com/docs). Every action with its inputs: [heyreagent.com/docs](https://heyreagent.com/docs) index.

## Recipes

Paste the prompt into your AI app after connecting the MCP server. The app runs the documented actions for you. Each recipe names the exact actions and links to their docs pages.

| Recipe | What it does |
|---|---|
| [find-decision-makers](recipes/find-decision-makers.md) | Decision makers at a target company by title and seniority. Agent plan. |
| [revive-cold-threads](recipes/revive-cold-threads.md) | Conversations that went quiet, with drafted follow-ups. |
| [clean-up-invitations](recipes/clean-up-invitations.md) | Preview and withdraw unanswered invitations. |
| [mine-post-engagers](recipes/mine-post-engagers.md) | Turn post reactors and commenters into invitations. |
| [inbox-triage](recipes/inbox-triage.md) | Refresh the inbox, answer everyone waiting on you. |
| [funding-signals](recipes/funding-signals.md) | Recently funded companies, then their decision makers. Agent plan. |

## Pricing

Free tier: every Connect action, for live use. LinkedIn disconnects after an hour without use, so a workflow on a schedule needs the Connect plan at $29.99/mo, which keeps LinkedIn connected. The Agent plan ($499/mo, 7-day free trial) adds 5 more actions and runs LinkedIn for you. Details: [heyreagent.com/pricing](https://heyreagent.com/pricing).

## Honest note

LinkedIn's User Agreement does not allow automated activity, and LinkedIn can restrict an account it decides is automated. HeyReagent builds a per-account daily limit into every kind of action to lower that risk. The limits do not remove it. Start small, spread calls through the day, keep volumes well under the caps, and warm up new accounts gradually. The full limits table is in the [docs](https://heyreagent.com/docs).
