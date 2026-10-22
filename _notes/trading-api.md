---
title: "Trading APIs for institutional clients"
summary: "How institutions trade digital assets through an API instead of a screen, and why quotes, idempotency and settlement shape the product."
tag: "Trading"
read_time: "5 min"
order: 5
---

## TL;DR

- A trading API lets a client's own system - a payments app, a treasury tool, a broker - request prices, place trades and settle them without a person clicking through a screen.
- For institutions, the common pattern is request-for-quote (RFQ): ask for a price, get a firm quote that lasts a short time, accept it or let it expire.
- The product is not the endpoints. It is predictable behaviour when something goes wrong - a timeout, a duplicate request, a quote that expired, a trade that has not settled yet.

## How it works

**Access.** The client is onboarded and verified first, then given API credentials. Requests are usually signed with a secret key, and many providers also restrict which IP addresses can call the API. Permissions are scoped: a key that can read balances should not automatically be able to trade or withdraw.

**Pricing.** Two common models:

- **RFQ:** the client asks "what is your price for 50,000 USDT to USD?" and receives a quote with an ID, a price and an expiry time. Accepting the quote ID before it expires locks the trade at that price.
- **Order book:** the client sends orders (market, limit) that match against other orders. More common on exchanges than with OTC desks.

Behind an RFQ, the provider sources prices from exchanges and liquidity providers, adds its spread, and must be able to fill the trade at the quoted price. Which trading pairs a client can trade depends on what those sources support.

**Channels.** REST endpoints for quotes, trades and balances; a streaming connection, such as a WebSocket, for live prices and status updates; and, at larger institutions, FIX, the long-standing messaging standard for trading.

**Settlement.** After a trade, assets and fiat move between accounts. In a custody-led model, trades settle into the client's custody account rather than an exchange wallet, and fiat legs go to the client's whitelisted bank account.

## Why users care

- **Price certainty:** the client's own customers are often waiting, so a quote must hold for long enough to act on it.
- **Reliability:** a payments business cannot tell its customers "the trade might have happened twice".
- **Reconciliation:** finance teams need every trade, fee and settlement to match their own records, by ID, at the end of the day.

## Product implications

- **Make retries safe.** An idempotency key on every trade request means a client can retry after a timeout without creating a duplicate trade.
- **Treat quote expiry as a designed state,** with a clear error and a fast way to re-quote, not a generic failure.
- **Expose status, not just results.** Trade and settlement states (accepted, executed, settling, settled, failed) should be queryable and pushed as events, so clients do not have to poll or call support.
- **Design the client's integration journey:** sandbox with realistic data, clear error codes, sample requests and an ops view for the provider's own team to see what a client's integration is doing.
- **Scope keys and limits per client,** so a misconfigured integration cannot trade more, or withdraw more, than the client intended.

## Where I applied it

At Hex Trust, I worked on the trading API used by institutional clients such as a UAE payment provider. My part was the integration behind it: getting quotes from Binance, getting the trading pairs clients could trade, and integrating with a liquidity provider so quotes could be filled.

## Further reading

- [The Idempotency-Key HTTP header (IETF draft)](https://datatracker.ietf.org/doc/draft-ietf-httpapi-idempotency-key-header/): the emerging standard for making API requests safe to retry.
- [The WebSocket protocol (RFC 6455)](https://www.rfc-editor.org/rfc/rfc6455): the standard behind most streaming price and status feeds.
- [Hex Trust OTC execution](https://www.hextrust.com/services/markets/otc-execution): an institutional desk's view of RFQ, order types and settlement to whitelisted bank accounts or wallets.
- [Hex Trust Convert-to-Pay](https://www.hextrust.com/services/payment/convert-to-pay): an API that lets payment providers accept digital assets and settle in fiat, using short-lived RFQ quotes.
