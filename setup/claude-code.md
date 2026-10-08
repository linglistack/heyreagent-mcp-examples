# Claude Code setup

## 1. Get your key

1. Sign in at [heyreagent.com](https://heyreagent.com) with your email. There is no password, they send you a sign-in link.
2. On your thread page, connect LinkedIn if you have not. Press Connect on the LinkedIn card and sign in there.
3. Open Menu, then Developers, and press Create a key. Copy it at once. It is shown only once, so keep it somewhere safe.

## 2. Add the MCP server

Run this in a terminal, with your key where it says YOUR_KEY:

```
claude mcp add --transport http heyreagent https://api.heyreagent.com/mcp \
  --header "Authorization: Bearer YOUR_KEY"
```

## 3. Check it

In Claude Code, ask: "List the HeyReagent tools and run get_my_profile."

If it answers with your LinkedIn profile, it works. Then paste any recipe from [recipes/](../recipes/find-decision-makers.md).

Full docs: [heyreagent.com/docs](https://heyreagent.com/docs)
