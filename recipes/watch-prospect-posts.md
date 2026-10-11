# Watch a prospect's posts

## Goal

Keep an eye on what one prospect, customer, or competitor is posting on LinkedIn, spot the posts worth engaging with, and draft a comment that starts a real conversation.

## Prompt

Paste this into your AI app:

```
Show me the 10 most recent LinkedIn posts from [paste profile link, or a company id for a company page]. Rank them by reactions plus comments. For the top 2, list who commented and draft a short comment from me that adds something specific to the post, not praise. Do not post anything until I approve the exact text.
```

## Actions it uses

- [list_posts_by_author](https://heyreagent.com/docs/actions/list_posts_by_author): read-only. It needs `author`: a profile link, a member id, or a company id (with `isCompany: true` for a company; a company link is not accepted). Optional `limit` (1 to 100, default 10) and `cursor` (pass the previous answer's `nextCursor` for the next page). Each post comes back with its `posts[].id`, `shareUrl`, `text`, `date`, and reaction and comment counters. Good to know: resolving a profile link counts as a profile view on LinkedIn.
- [list_post_comments](https://heyreagent.com/docs/actions/list_post_comments) and [get_post_engagers](https://heyreagent.com/docs/actions/get_post_engagers): both take a post id from the first step and show who engaged and what they said.
- [comment_on_post](https://heyreagent.com/docs/actions/comment_on_post): posts only the comment you approved. Comments are limited to 40 a day.

## When to use it

Before outreach to a key account, or weekly on two or three competitors. It differs from [mine-post-engagers](mine-post-engagers.md), which works on your own posts: this one watches someone else's, so your first touch is a thoughtful comment on their turf, not a cold invitation.
