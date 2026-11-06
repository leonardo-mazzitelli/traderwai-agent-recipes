# TraderWAI agent recipes

Ready-to-use prompts and agent setups for trading with AI through **[TraderWAI](https://traderwai.com)**, a hosted MCP server that lets Claude, ChatGPT, Grok and Cursor read live charts, run backtests on 1-minute history and work with your own broker account (MetaTrader 4/5, cTrader, TradeLocker, Match-Trader, DXtrade, Capital.com, tastytrade, Binance, Bybit).

Copy a recipe, paste it into your AI, adjust the symbol and your risk. That's it.

> **Risk warning.** Trading involves risk of loss. These recipes are examples, not investment advice. Past results, including backtests, don't guarantee future results. Start on a demo account.

## Connect TraderWAI first

MCP server URL: `https://mcp.traderwai.com` (Streamable HTTP, OAuth sign-in, free plan available).

| AI | How |
|---|---|
| **Cursor** (editor) | [One-click install](https://traderwai.com/en/docs) or add the server URL in *Settings → MCP* |
| **Cursor cloud agents / Automations** | [cursor.com/agents](https://cursor.com/agents) → MCP dropdown → add `https://mcp.traderwai.com` and sign in |
| **Grok** | [grok.com/connectors](https://grok.com/connectors) → New connector → Custom → paste the URL and sign in |
| **Claude** | Settings → Connectors → Add custom connector → paste the URL |
| **ChatGPT** | Plugins → Add → Custom MCP server → paste the URL |

Then link a broker account on [traderwai.com/app](https://traderwai.com/en/app) (a demo account works). Analysis-only recipes work without a broker.

## Recipes

| Recipe | Where it shines | Needs a broker? |
|---|---|---|
| [Hourly position watch](recipes/hourly-position-watch.md) | Cursor Automation, every hour | Yes |
| [Break-even manager](recipes/break-even-manager.md) | Any AI, set once | Yes |
| [Gold H1 review](recipes/gold-h1-review.md) | Any AI, or a scheduled agent | No |
| [London session brief](recipes/london-session-brief.md) | Cursor Automation, weekdays 06:45 UTC | No |
| [Backtest an idea in plain English](recipes/backtest-an-idea.md) | Any AI | No |
| [End-of-day journal](recipes/end-of-day-journal.md) | Cursor Automation, weekdays 21:15 UTC | Yes |

## Cursor rule

[`.cursor/rules/traderwai.mdc`](.cursor/rules/traderwai.mdc) tells Cursor's agent how to use TraderWAI safely: check the broker price before any order, size from risk, propose instead of executing unless you say so, and always show the chart.

## How the pieces fit

- **Your agent decides what to look at and when.** A Cursor Automation can run a recipe on a schedule, even with your laptop closed.
- **TraderWAI does the market and broker work.** Charts, exact candles, market structure, backtests and orders on your account, with server-side risk limits your agent cannot change.
- **Rules that must fire on time live on TraderWAI, not in the agent.** Conditional orders (close, break-even, entry on a candle close) are checked every minute on our servers, so they don't depend on when your agent runs.
- **You stay in control.** By default orders wait for your approval. Automatic execution is opt-in, per symbol, with daily caps.

## Links

- Website and free plan: [traderwai.com](https://traderwai.com)
- Docs: [traderwai.com/en/docs](https://traderwai.com/en/docs)
- MCP server listing: [github.com/leonardo-mazzitelli/traderwai-mcp](https://github.com/leonardo-mazzitelli/traderwai-mcp)
- Contact: info@traderwai.com

Operated by FLEXIN AGILE LTD (United Kingdom). Recipes are licensed under [CC BY 4.0](LICENSE).
