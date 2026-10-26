# AlphaYou for Claude

Ask Claude about a stock or a Hyperliquid trader and get the filing, the date and the source link instead of a guess.

## What you can ask

- Smart money in a stock: funds (13F), Congress, insiders (Form 4), government contracts, influencers and tracked top traders, each with its own date and source link.
- Company facts from SEC filings: financials, reported earnings and management guidance, announced earnings dates and financial quality ratios.
- US macro data and weekly CFTC futures positioning for context.
- Hyperliquid research: rank and compare public wallets by their historical record, and inspect positions, observed activity and market context.

Try: "Who is buying NVDA, and what did insiders do this quarter?", "Rank the top Hyperliquid traders by Sharpe and show what the best three hold", "What did Nvidia file with the SEC in the last 90 days?"

## What this plugin connects to

It adds one remote MCP server, `https://alphayou.net/api/mcp/market?utm_source=claude`, with 19 read-only tools (version 0.4.0). No sign-in, account, API key or credentials are needed. The `utm_source=claude` part only tells AlphaYou that the request came from Claude. It is not authentication.

## Skills and commands

Four skills tell Claude when to use the tools and how to present the answer: `smart-money-check`, `hyperliquid-wallet-research`, `company-filings-brief` and `market-brief`. Four commands start them directly: `/alphayou:smart-money`, `/alphayou:wallet`, `/alphayou:compare-wallets` and `/alphayou:brief`.

Skills and commands are plain Markdown instructions. The plugin runs no scripts, hooks or local servers, and its only network destination is the AlphaYou server above.

## What is sent

Only what a question needs: stock tickers, research filters, public wallet addresses, asset names and comparison choices. AlphaYou records which tool was used, the ticker, whether the call succeeded, how long it took and that the request came from Claude. It does not record full chats, wallet addresses, emails or a persistent user identifier. See the [privacy policy](https://alphayou.net/legal/privacy).

## What it does not do

This is research only. It never connects a wallet, signs, trades, copies a trader, sets up alerts or gives personal advice or position sizing. Missing coverage is reported as unknown, never as zero. Nothing here is investment advice.

## Links

- Website and help: https://alphayou.net/connectors
- Privacy policy: https://alphayou.net/legal/privacy
- Terms: https://alphayou.net/legal/terms
- Support: info@alphayou.net

## License

MIT, see LICENSE. The license covers the files in this repository, not the AlphaYou service or its data.
