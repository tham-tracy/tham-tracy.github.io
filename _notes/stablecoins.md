---
title: "Stablecoins"
summary: "Tokens designed to hold a steady value - what backs them, what can go wrong, and why they power most crypto money movement."
tag: "Payments"
read_time: "4 min"
order: 3
---

## TL;DR

- A stablecoin is a token designed to track a reference asset, usually the US dollar.
- Fiat-backed stablecoins such as USDT and USDC hold reserves of mostly cash equivalents and short-term government debt (Tether also holds other assets such as gold, bitcoin and secured loans); others use crypto collateral or algorithms.
- For products, they are the bridge between banks and blockchains - but "stable" is a design goal, not a guarantee.

## How it works

The most widely used stablecoins are **fiat-backed**. An issuer mints one token for each dollar it receives and holds reserves - cash, bank deposits, short-term government bills - to redeem tokens back into dollars. Issuers publish reserve reports or attestations so holders can check backing.

Other designs exist:

- **Crypto-collateralised:** backed by other digital assets held in smart contracts, usually over-collateralised to absorb price swings.
- **Algorithmic:** rely on market incentives rather than reserves to hold the peg - historically the most fragile design.

Because stablecoins move on public blockchains, they settle around the clock and can be transferred globally in minutes, which is why platforms use them as the "cash leg" of trading and on/off-ramps.

## Why users care

- **Stability:** clients assume one USDC is always worth one dollar. A "depeg" - trading below its target - breaks that assumption.
- **Trust in the issuer:** what backs the token, where reserves are held and who can freeze it.
- **Convenience:** fast, 24/7 transfers compared with bank wires.

## Product implications

- **Be precise about what the client holds.** "USDT" and "USD" are not the same; balances, statements and conversion screens should never blur them.
- **Choose which stablecoins to support deliberately,** based on issuer transparency, liquidity and regulatory treatment in target markets.
- **Show conversion rates and fees** when moving between fiat and stablecoins, even when the rate is close to 1:1.
- **Plan for stress.** Decide in advance how the product communicates and behaves if a supported stablecoin depegs.

## Where I applied it

Aura used stablecoins as the bridge for fiat: clients deposit USD and receive USDT, and can withdraw USD from USDT or USDC balances. See [On-ramp and off-ramp in the Aura case study]({{ '/work/aura/' | relative_url }}#on-ramp-and-off-ramp).

## Further reading

- [MAS finalises stablecoin regulatory framework](https://www.mas.gov.sg/news/media-releases/2023/mas-finalises-stablecoin-regulatory-framework): Singapore's rules on reserve backing, redemption and disclosure for single-currency stablecoins.
- [Circle - USDC transparency](https://www.circle.com/transparency): an issuer's reserve reporting.
- [Tether - transparency](https://tether.to/en/transparency/): an issuer's reserve reporting.
- [BIS Annual Economic Report 2025, chapter III](https://www.bis.org/publ/arpdf/ar2025e3.htm): a central-bank view of stablecoins' role in the monetary system.
