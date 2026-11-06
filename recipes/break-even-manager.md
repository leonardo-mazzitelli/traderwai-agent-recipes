# Break-even manager

Set a rule once, in plain English, and TraderWAI moves your stop to break-even when price gets there. The rule runs on TraderWAI's servers every minute, so it keeps working after you close the chat.

**Best in:** any AI with TraderWAI connected (Claude, ChatGPT, Grok, Cursor).
**Needs:** a linked broker account with an open position.

## Prompt

```text
Using TraderWAI, look at my open position on EUR/USD.
When price reaches 1R in profit, move the stop loss to my entry price (break-even).
Create it as a conditional order on the position and show me the rule before you save it.
```

Variations:

- "When an H1 candle closes above 1.1250, move my stop to break-even."
- "If gold drops back below 4,040 before 18:00 UTC, close half of my position."
- "Close my NAS100 trade at 20:45 UTC if it's still open."

## What happens

- Your AI calls `create_conditional_order` with the rule. You can list, pause or delete rules any time ("show my conditional orders").
- TraderWAI evaluates the rule every minute with live prices and acts on the broker when it triggers.
- Free plan: 1 new conditional order per day (2 active). Paid plans allow more.

> Trading involves risk of loss. Automated rules can trigger in fast markets at prices different from the level you set.
