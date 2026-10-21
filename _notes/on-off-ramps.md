---
title: "Fiat on/off-ramps"
summary: "How money moves between bank accounts and digital-asset balances, and why that is where most trust is won or lost."
tag: "Payments"
read_time: "4 min"
order: 2
---

## TL;DR

- An on-ramp turns fiat (e.g. USD) into a digital asset; an off-ramp turns it back and pays out to a bank account.
- The hard parts are not on-chain: they are banking rails, compliance checks and reconciliation.
- Good ramp UX is about exact instructions, verified accounts and status the client can follow.

## How it works

**On-ramp.** The client sends fiat to the platform's bank account, usually by wire. The platform matches the incoming payment to the client's request, then credits the client with a digital asset - often a stablecoin such as USDT or USDC - at a quoted rate.

**Off-ramp.** The client chooses a digital-asset balance to sell or redeem and a bank account to receive fiat. The platform debits the balance and sends a bank transfer from its own account.

Around both flows sit:

- **KYC/AML checks:** the client and, often, the bank account must be verified in the client's name before money moves.
- **Banking rails:** wires have cut-off times, correspondent banks and settlement windows - a "same day" promise depends on all of them.
- **Reconciliation:** matching bank statements to client requests, especially when a client sends the wrong amount or forgets a reference.

## Why users care

- **Trust:** sending a large wire to a new provider is the moment a client is most nervous.
- **Cost:** spreads, conversion rates and bank fees should be visible before the client commits.
- **Speed and certainty:** "When will my money arrive?" is the most common question.

## Product implications

- **Show exact instructions.** Bank details, reference codes and the conversion rate on one screen, with copy buttons - mistakes here create manual work and anxious clients.
- **Verify bank accounts before the first withdrawal,** not during it, so payouts are not blocked at the worst moment.
- **Make status visible** from request to completion, including "received, being processed" states for wires.
- **Design for exceptions:** wrong amounts, missing references and returned payments need an operations view as well as a client message.

## Where I applied it

Aura's on-ramp lets clients deposit USD and receive USDT; its off-ramp lets them withdraw USD from a USDT or USDC balance to a verified bank account, with transaction statuses throughout. See [On-ramp and off-ramp in the Aura case study]({{ '/work/aura/' | relative_url }}#on-ramp-and-off-ramp).

## Further reading

- [FinCEN guidance on convertible virtual currency business models](https://www.fincen.gov/resources/statutes-regulations/guidance/application-fincens-regulations-certain-business-models): how US money-transmission and AML rules apply to platforms that exchange fiat and digital assets.
- [Fedwire Funds Service - Federal Reserve](https://www.federalreserve.gov/paymentsystems/fedfunds_about.htm): the US wire system behind many USD deposits and withdrawals, including its operating hours.
