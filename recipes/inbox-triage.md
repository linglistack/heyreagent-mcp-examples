# Inbox triage

## Goal

Refresh the inbox, then work through everyone whose last message you have not answered.

## Prompt

Paste this into your AI app:

```
Refresh my LinkedIn inbox, then list everyone whose last message I have not answered, most recent first. For each person show me their last message and draft a reply in my voice. I approve every reply before you send it.
```

## Actions it uses

- [sync_inbox](https://heyreagent.com/docs/actions/sync_inbox): refreshes the stored inbox in the background. Run it first when the copy is stale or older than 7 days.
- [who_is_waiting_on_me](https://heyreagent.com/docs/actions/who_is_waiting_on_me): lists the unanswered threads, most recent first.
- [send_message](https://heyreagent.com/docs/actions/send_message): sends each approved reply into the existing conversation.

## When to use it

Daily, or every morning before outreach. Unanswered threads are the warmest pipeline you already own, and reading your inbox is not limited.
