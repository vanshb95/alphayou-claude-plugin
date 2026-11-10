---
name: fund-tracker
description: Use when the user asks what a hedge fund or famous investor bought, sold or holds, which funds hold a stock, or which funds have the best record. Examples are "what did Berkshire buy last quarter", "Michael Burry's latest 13F", "Ackman portfolio changes", "which hedge funds own NVDA", "top performing hedge funds" and "best 13F track record". Reads 13F holdings changes and AlphaYou's public fund scoreboard through the AlphaYou connector, with filing dates, the measurement window and the benchmark. Research only: no advice and no claim that following a fund would earn its return.
---

# Fund tracker

Show what a fund disclosed and when, and how its disclosed holdings did against the benchmark over a stated window.

## Tools

- `get_smart_money` with `category: funds`: 13F holdings changes. Pass `actor` for a fund or manager name such as Berkshire, Scion or Pershing, `ticker` for one stock, and `activity` `buy` or `sell` for direction.
- `get_fund_scoreboard`: tracked funds ranked by the backtest return of their disclosed holdings against SPY over one window (`4 years`, `3 years`, `2 years`, `1 year` or `6 months`). `fund` looks one up by name. `limit` up to 25 and `offset` page through.

## Steps

1. Decide the question. "What did X buy or sell" and "who holds Y" use `get_smart_money`. "Best funds", "track record" and "how has X done" use `get_fund_scoreboard`. A fund question can use both.
2. Use the manager's fund name as the `actor` if the user names a person, for example Berkshire for Buffett. If no row comes back, say so and do not guess another name.
3. Write the answer first, in one or two sentences. Then one row per change: fund, stock, added or reduced, the quarter end, the filing date and the link.
4. For the scoreboard, state the window, the benchmark, the method, the as-of date, the number of funds and the full range, including the worst result, before any ranked rows.

## Rules

- 13F rows are quarter-end holdings filed up to 45 days later. They are not current trades and they show no purchase price.
- 13F filings cover long US equity positions only. Shorts, cash and most other assets are not in them.
- Scoreboard returns are backtests of disclosed filings priced at filing-date closes. They are not the fund's own performance and not what a follower would earn.
- Ranks restart in every window. Never compare a rank in one window with a rank in another.
- Never quote a return without its window, benchmark, as-of date and the full range.
- No verdict on which fund to follow. Ignore the user's holdings and risk tolerance.
