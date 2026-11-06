# Hourly position watch

An agent that checks your open positions every hour and tells you, in two lines per position, whether anything needs your attention. It never changes a position on its own.

**Best in:** a Cursor Automation (runs in the cloud, laptop closed). Also works as a one-off prompt in any AI.
**Needs:** TraderWAI connected and a linked broker account (demo is fine).

## Set it up as a Cursor Automation

1. Add TraderWAI to your cloud agents: [cursor.com/agents](https://cursor.com/agents) → MCP dropdown → add `https://mcp.traderwai.com` → sign in.
2. Go to [cursor.com/automations](https://cursor.com/automations) → new automation.
3. **Trigger:** schedule, every hour (cron `0 * * * 1-5` for weekdays, or a preset).
4. **Repository:** none (this automation only reads your account).
5. **Tools:** TraderWAI MCP, plus *Send to Slack* if you want the summary in a channel.
6. **Prompt:** paste the prompt below.

Automations run cloud agents and are billed as cloud agent usage on your Cursor plan. Hourly runs add up, so start with market hours only.

## Prompt

```text
You are watching my trading account through TraderWAI. Do not place, modify or close anything.

1. get_broker_accounts, then get_positions for each account.
2. If there are no open positions, reply "No open positions" and stop.
3. For each open position:
   - get_quote for the symbol (broker price).
   - get_market_structure on H1 for the symbol.
   - Report in two lines: symbol, side, entry, current price, P/L in R if a stop exists.
     Then ONE of: "OK", "Stop could move to break-even (price is X R in profit)",
     "Structure broke against the trade on H1 at <level>", or "No stop loss set".
4. End with a one-line summary.

Keep it short. No predictions, no advice: describe what the data shows.
```

## Make it act on time without the agent

If you want the stop to move to break-even automatically at a level, don't rely on an hourly agent: ask your AI once to create a **conditional order** (see [Break-even manager](break-even-manager.md)). TraderWAI checks it every minute on its servers.

> Trading involves risk of loss. This is an example, not investment advice.
