---
title: "Crypto yield products: staking, lending and structured"
summary: "Where crypto yield comes from, what risks sit behind each source, and how to present it so clients understand what they are buying."
tag: "Yield"
read_time: "5 min"
order: 4
---

## TL;DR

- Crypto yield comes from three main sources: staking rewards, lending interest and structured strategies.
- Each source carries different risks - lock-ups, counterparty failure, market moves - that a headline APY hides.
- The core product job is to separate what is promised from what is estimated, and to show exit terms before a client commits.

## How it works

**Staking.** Proof-of-stake blockchains reward holders who lock tokens to help validate the network. Rewards vary with network conditions, and unstaking can involve a waiting period. Validators that misbehave can be **slashed**, losing part of the staked tokens.

**Lending.** Assets are lent to borrowers - trading firms, or on-chain lending protocols - who pay interest. Rates move with demand, and the lender takes on the risk that a borrower or protocol fails.

**Structured products.** Strategies such as options-based or market-linked products pay a return that depends on how the market moves, sometimes with a fixed coupon and conditions on the principal.

Platforms package these into products with a term (flexible or fixed), a displayed rate (fixed APY or an estimated range) and rules for subscribing and redeeming.

## Why users care

- **Return:** what will I actually earn, and is it guaranteed?
- **Access:** when can I get my money back, and what does it cost to exit early?
- **Risk:** what happens to my principal if markets fall, a counterparty fails, a validator is slashed, or a smart-contract bug or exploit hits the protocol?

## Product implications

- **Separate promised and estimated values.** A fixed APY and a market-linked estimate must not look the same on screen.
- **Show terms at the moment of decision:** term, minimum and maximum, subscription cut-off, maturity and redemption settlement - before confirmation, not in a PDF.
- **Make complexity progressive.** Offer a simple, deposit-like product first, and keep market-linked products clearly labelled for clients who want more.
- **Track positions after purchase.** Clients need value, accrued yield and maturity in their portfolio, not just a receipt.

## Where I applied it

Aura's Earn offered Fixed Earn, presented like a term deposit, alongside market-linked Variable and Strategy products, with subscription cut-off and redemption timing shown before clients confirm. See [Earn in the Aura case study]({{ '/work/aura/' | relative_url }}#earn-designing-yield-products-clients-can-understand-and-trust).

## Further reading

- [Ethereum staking - ethereum.org](https://ethereum.org/en/staking/): how staking works on the largest proof-of-stake network.
- [Proof-of-stake rewards and penalties - ethereum.org](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/rewards-and-penalties/): where staking rewards come from, and how slashing works.
- [DeFi risks and the decentralisation illusion - BIS](https://www.bis.org/publ/qtrpdf/r_qt2112b.htm): a central-bank analysis of on-chain lending and its risks.
