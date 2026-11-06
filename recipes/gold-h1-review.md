# Gold H1 review

A structured look at XAU/USD on the 1-hour chart, with the levels drawn on a real chart. Analysis only: no broker needed.

**Best in:** any AI with TraderWAI connected. Schedule it in a Cursor Automation (e.g. `0 7,13 * * 1-5`) to get it before London and New York.

## Prompt

```text
Using TraderWAI, review XAU/USD:

1. get_chart on H4, then H1, to see the context and the last 2-3 days.
2. get_market_structure on H1: trend, last break of structure, key swing highs and lows.
3. get_ohlc on H1 for exact prices of the levels you'll use.
4. draw_chart on H1 with: the range or trend, the nearest supply and demand zones,
   the last break of structure, and a label with your read ("range", "breakout", "rejection").
5. Reply in five lines max: bias, the two levels that matter most, what would change your mind.

No trade recommendation. Describe what the chart shows.
```

Swap `XAU/USD` for any of the 40+ symbols (forex majors and crosses, silver, oil, indices, futures, BTC, ETH).

> Trading involves risk of loss. This is an example, not investment advice.
