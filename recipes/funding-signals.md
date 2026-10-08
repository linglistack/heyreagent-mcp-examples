# Funding signals to decision makers

## Goal

Find recently funded companies in your ICP, then get the decision makers at the best fits.

## Prompt

Paste this into your AI app:

```
List software companies with 11 to 200 employees in the United States that recently raised funding. Show me the top 10. Then, for the 3 I pick, find their decision makers in sales and marketing leadership. Preview costs before pulling anything.
```

## Actions it uses

- [list_funding_signals](https://heyreagent.com/docs/actions/list_funding_signals): recently funded companies by industry, location, and headcount band. Narrow the filters, there is no next page.
- [find_decision_makers](https://heyreagent.com/docs/actions/find_decision_makers): decision makers at each picked company. Preview first with confirm=false, which shows the match count and cost before anything is charged.

## Plan note

Both actions are on the Agent plan ($499/mo, 7-day free trial). On other plans the calls are refused with upgrade_required. Details: [heyreagent.com/pricing](https://heyreagent.com/pricing).

## When to use it

Newly funded companies buy tools. This compresses "who raised" to "who to talk to" into one session.
