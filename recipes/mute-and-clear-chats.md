# Mute and clear old chats

## Goal

Work through your LinkedIn chats once, mark the finished ones read, and mute the noisy group chats so the inbox only surfaces conversations that still need you.

## Prompt

Paste this into your AI app:

```
List my LinkedIn chats. Group them into: waiting on me, finished, and group chats with no message in the last 30 days. Show me the list first. Then, only for the ones I approve, mark the finished ones read and mute the stale group chats. Change nothing until I say go.
```

## Actions it uses

- [list_chats](https://heyreagent.com/docs/actions/list_chats): lists your chats; each chat's id comes back as `chats[].id`, which is what the next action needs.
- [set_chat_status](https://heyreagent.com/docs/actions/set_chat_status): it needs `chatId`. Optional `read` (true marks it read, false marks it unread) and `muted` (true mutes notifications, false unmutes). The answer repeats what was changed. This action changes things right away when it runs, which is why the prompt makes it list first and wait for your go.

## When to use it

When the unread badge has stopped meaning anything. Marking read here is the local inbox state, separate from `mark_read` in the older inbox flow, and muting is reversible: run it again with `muted: false` to unmute. Pairs with [inbox-triage](inbox-triage.md): triage answers the people waiting, this clears the rest.
