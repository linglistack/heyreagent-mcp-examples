# n8n workflow pack

Importable n8n workflows for the HeyReagent LinkedIn API. Every workflow here is **read-only**: it reads your own LinkedIn through the API and formats the answer. Nothing sends, invites, posts, or withdraws anything.

For driving HeyReagent from inside an n8n AI agent instead (MCP Client Tool node), see [../setup/n8n.md](../setup/n8n.md).

## Before you import

1. Get a key: sign in at [heyreagent.com](https://heyreagent.com), connect LinkedIn, then on your thread page open *Menu → Developers → Create a key*. The key is shown once.
2. Make the key available to n8n as an environment variable named `HEYREAGENT_API_KEY` (self-hosted: set it where n8n runs; n8n Cloud: set it in your instance's environment settings). The workflows read it as `Bearer {{ $env.HEYREAGENT_API_KEY }}` and never contain a key themselves.
3. Scheduled workflows need LinkedIn to stay connected. On the free plan LinkedIn disconnects after an hour without use, so a workflow on a schedule needs the Connect plan ($29.99/mo). Details: [heyreagent.com/pricing](https://heyreagent.com/pricing).

## Import

In n8n: *Workflows → Import from File*, pick a `.json` file from this folder, then open it and press *Test workflow* once before activating it.

## The workflows

| File | Schedule | What it does |
|---|---|---|
| [morning-brief.json](morning-brief.json) | Weekdays 08:00 | Calls `who_is_waiting_on_me` and formats who is waiting on your reply into one short brief. |
| [cold-conversation-radar.json](cold-conversation-radar.json) | Mondays 09:00 | Calls `who_went_cold` and lists conversations that went quiet. Read-only: it drafts nothing and sends nothing. For follow-up drafts, use the [revive-cold-threads recipe](../recipes/revive-cold-threads.md) in your AI app. |
| [daily-usage-guard.json](daily-usage-guard.json) | Daily 07:30 | Calls `get_usage` and shows today's used/remaining per-account action limits, so a scheduled workflow never starts blind. |

Each workflow ends in a placeholder **Deliver (replace me)** node. Swap it for Slack, Gmail, Telegram, or any node you like and pass it `{{ $json.brief }}`.

## How the calls work

Every call is the same shape, per the [official docs](https://heyreagent.com/docs):

- `POST https://api.heyreagent.com/v1/actions/<action_name>`
- Header `Authorization: Bearer <your key>`
- JSON body: `{}` when the action needs no inputs
- The answer is `{ "ok": true, "result": { ... } }`, or `{ "ok": false, "error": "...", "message": "..." }` when it did not work. Each workflow's format node surfaces that message instead of failing silently.

Want another action in a workflow? Copy any HTTP Request node, change the action name in the URL, and check the action's page in the docs for its inputs and what comes back.

## Honest note

LinkedIn's User Agreement does not allow automated activity, and LinkedIn can restrict an account it decides is automated. HeyReagent builds a per-account daily limit into every kind of action to lower that risk; the limits do not remove it. These workflows only read, which is the lowest-risk place to start. Start small, spread calls through the day, and keep volumes well under the caps. The full limits table is in the [docs](https://heyreagent.com/docs).
