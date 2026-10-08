# Find decision makers

## Goal

Get the decision makers at one target company, filtered by title, seniority, and function.

## Prompt

Paste this into your AI app:

```
Find the decision makers at [company name]: VPs and C-level in sales and marketing, in the United States. Show me the preview first: how many match and what it costs. Do not pull the full list until I say so.
```

## Actions it uses

- [find_decision_makers](https://heyreagent.com/docs/actions/find_decision_makers): company name in, people out. It runs with confirm=false first, which only previews the match count and the cost. confirm=true pulls the list and charges 0.02 credits per person.

## Plan note

This action is on the Agent plan ($499/mo, 7-day free trial). On other plans the call is refused with upgrade_required. Details: [heyreagent.com/pricing](https://heyreagent.com/pricing).

## When to use it

Building a target account list before any outreach. Approve the preview, pull the list, then invite with send_invitation.
