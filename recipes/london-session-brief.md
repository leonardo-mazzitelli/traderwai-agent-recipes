# London session brief

Before London opens, a short brief on the pairs you trade: where the Asian range is, what got swept overnight and the levels to watch.

**Best in:** a Cursor Automation on weekdays at 06:45 UTC (cron `45 6 * * 1-5`), sent to Slack. No repository and no broker needed.

## Prompt

```text
Using TraderWAI, prepare my London session brief for EUR/USD, GBP/USD and XAU/USD.

For each symbol:
1. get_ohlc on M15 from 00:00 UTC today: Asian session high and low (00:00-06:00 UTC).
2. get_market_structure on H1: trend and last break of structure.
3. Note if the Asian high or low already swept yesterday's high or low.

Reply as a compact table: symbol | Asian high | Asian low | H1 trend | note (max 12 words).
Then one draw_chart on M15 for the symbol with the clearest setup, with the Asian range shaded.
No trade recommendations.
```

Want to know if trading the Asian-range breakout has worked? See [Backtest an idea](backtest-an-idea.md).

> Trading involves risk of loss. This is an example, not investment advice.
