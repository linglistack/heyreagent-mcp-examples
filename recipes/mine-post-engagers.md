# Mine post engagers

## Goal

Turn the people who reacted to or commented on a LinkedIn post into connection invitations.

## Prompt

Paste this into your AI app:

```
I posted this on LinkedIn: [paste post link]. List everyone who reacted or commented. Filter to [your ICP, for example: VP Sales at B2B software companies]. For each match, draft a short connection note referencing the post. Do not send anything until I approve each one.
```

## Actions it uses

- [get_post_engagers](https://heyreagent.com/docs/actions/get_post_engagers): takes the post link, returns reactors and commenters with their LinkedIn URLs. To get the link, open the post, click the three dots at the top right, then "Copy link to post".
- [send_invitation](https://heyreagent.com/docs/actions/send_invitation): sends the approved invitation, with or without a note. Watch the note limits: 300 characters on a paid LinkedIn account, 200 on a free one, and only 5 notes per 30 days on free accounts.

## When to use it

After any post that performed well. Engagers already raised their hand, so the acceptance rate beats cold search.
