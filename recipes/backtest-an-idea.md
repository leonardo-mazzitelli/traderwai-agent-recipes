# Backtest an idea in plain English

Describe a rule the way you'd explain it to a friend. TraderWAI turns it into a backtest on historical 1-minute candles and returns every trade.

**Best in:** any AI with TraderWAI connected. No broker needed.

## Prompt

```text
Using TraderWAI's backtest_strategy, test this on EUR/USD over the last 6 months:

Buy when the London session (07:00 UTC onwards) breaks above the Asian range high (00:00-06:00 UTC).
Stop loss below the Asian range low. Take profit at 2R. One trade per day, close any open trade at 16:00 UTC.

Show win rate, total R, max drawdown, number of trades and the worst losing streak.
Then explain in plain words whether this is robust or just a handful of lucky trades.
```

More ideas to try:

- "Sell gold after a liquidity sweep of the previous day's high on M15, stop above the sweep, target 1.5R."
- "Buy NAS100 when the 20 EMA crosses above the 50 EMA on H1, only between 13:30 and 17:00 UTC."
- "Fade the first fair value gap after the New York open on XAU/USD."

## Good to know

- History depends on the plan: Free covers the last 2 weeks; paid plans go back 6 months to 2 years.
- A few dozen trades prove little. Ask your AI to compare against a different period before trusting a result.

> Past results don't guarantee future results. Trading involves risk of loss.
