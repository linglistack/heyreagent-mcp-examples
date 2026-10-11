# Connections never messaged

## Goal

Find connections you have never exchanged a message with, and draft a first message for the ones worth reaching, without sending anything yet.

## Prompt

Paste this into your AI app:

```
List my LinkedIn connections I have never messaged, only ones I connected with on or after [a date, for example 2026-01-01], up to 50. For each, show their name, headline, and profile link. Draft one short first message that references something specific on their profile and connects it to [your goal, for example: founders comparing notes on outbound]. Do not send anything. I will approve each one first.
```

## Actions it uses

- [connections_never_messaged](https://heyreagent.com/docs/actions/connections_never_messaged): read-only, changes nothing. Optional inputs: `since` (an ISO date, so you only see newer connections), `limit` (1 to 200, default 100), and `refresh` (true pulls the latest connections first). The answer carries a summary and a leads list. It compares your stored connections with your stored inbox, so it is only as fresh as both.
- [send_message](https://heyreagent.com/docs/actions/send_message): sends the approved message to a first-degree connection, using the `leads[].profileUrl` from the step above. Messages are capped at 100 a day per LinkedIn account.

## When to use it

Monthly network hygiene. Most connection lists are full of people who accepted and were never spoken to. A specific first message to someone already in your network beats cold outreach to a stranger, and the read step is the safe place to start.
