# Engagers not connected

## Goal

Find the people who reacted to or commented on one of your LinkedIn posts and are not your connections yet, then draft invitations for the ones who fit.

## Prompt

Paste this into your AI app:

```
I posted this on LinkedIn: [paste post link]. List the people who reacted or commented and are not my connections. Where there is a comment, show me what they wrote. Filter to [your ICP, for example: founders and heads of sales at B2B companies]. For each match, draft a short connection note that references their comment, or the post itself if they only reacted. Do not send anything until I approve each one.
```

## Actions it uses

- [engagers_not_connected](https://heyreagent.com/docs/actions/engagers_not_connected): read-only, changes nothing. It needs `postUrl`: the post link or its social id (a bare post id is refused). Optional `maxReactions` and `maxComments` (1 to 100 each) cap how many engagers it scans, and `limit` (1 to 200, default 100) caps the leads returned. A commenter's comment text comes back in `leads[].note`.
- [send_invitation](https://heyreagent.com/docs/actions/send_invitation): sends the approved invitation, with or without a note. Watch the note limits: 300 characters on a paid LinkedIn account, 200 on a free one, and only 5 notes per 30 days on free accounts.

## When to use it

After a post that drew engagement from outside your network. It differs from [mine-post-engagers](mine-post-engagers.md), which lists every engager: this one cuts straight to the people you cannot message yet because you are not connected. They already engaged once, so the invitation starts warm.
