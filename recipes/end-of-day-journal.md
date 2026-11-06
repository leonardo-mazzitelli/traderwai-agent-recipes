# End-of-day journal

Every evening, a short journal of what you traded today: results in R, what went right, what broke your rules. Written from your real trade history, not from memory.

**Best in:** a Cursor Automation on weekdays at 21:15 UTC (cron `15 21 * * 1-5`). Add *Memories* so the agent spots patterns over weeks, or point it at a repository to commit one Markdown file per day.
**Needs:** a linked broker account.

## Prompt

```text
Using TraderWAI, write today's trading journal. Do not place or change any order.

1. get_trade_results for today (all linked accounts).
2. For each closed trade: symbol, side, entry, exit, result in R and money, and which AI or rule opened it.
3. get_positions: list anything still open with its current R.
4. Three short sections:
   - What worked (max 3 bullets)
   - What broke my rules (stop moved away, size above my risk limit, trade outside my hours)
   - One thing to do differently tomorrow
5. Totals: trades, win rate, total R, best and worst trade.

Be factual and short. If there were no trades, say so in one line.
```

> Trading involves risk of loss. This is an example, not investment advice.
