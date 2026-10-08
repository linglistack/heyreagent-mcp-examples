# Revive cold threads

## Goal

Find LinkedIn conversations that went quiet and draft a follow-up for each, without sending anything yet.

## Prompt

Paste this into your AI app:

```
List my LinkedIn conversations that went cold in the last 30 days, only the ones where the other person replied at least once. For each, show me the last exchange and draft one short follow-up in my voice. Do not send anything. I will approve each one first.
```

## Actions it uses

- [who_went_cold](https://heyreagent.com/docs/actions/who_went_cold): lists quiet conversations. Use days=30 and onlyWithReply=true to skip threads that never got a reply.
- [send_message](https://heyreagent.com/docs/actions/send_message): sends the approved follow-up into the existing conversation.

## When to use it

Weekly pipeline hygiene. A cold thread where the other person once replied converts far better than cold outreach, and most people never follow up at all. Reading is unlimited, so the list step costs nothing.
