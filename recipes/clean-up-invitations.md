# Clean up unanswered invitations

## Goal

See which sent invitations are still unanswered, then withdraw the stale ones to free up invitation capacity.

## Prompt

Paste this into your AI app:

```
Preview how many of my sent LinkedIn invitations are still unanswered after 14 days, broken down by campaign. Show me the count. After I confirm, withdraw them.
```

## Actions it uses

- [preview_withdraw_invitations](https://heyreagent.com/docs/actions/preview_withdraw_invitations): read-only count per campaign. Only invitations pending 7 to 42 days qualify. Pass the campaignId from the preview, or the linkedinConnectionId to cover all campaigns on one account.
- [withdraw_invitations](https://heyreagent.com/docs/actions/withdraw_invitations): takes them back in the background. Same inputs as the preview. Run the preview first.

## Warnings

Withdrawing cannot be undone. Calling withdraw twice queues the withdrawal twice, so call it exactly once. Invitations are capped per day and per 7 days, so clearing stale ones keeps you under the caps.

## When to use it

Monthly, or whenever you are close to the weekly invitation limit and need room.
