---
title: "Digital-asset custody: hot, cold and MPC"
summary: "Who holds the keys, how they are protected, and why that decides how fast a client can withdraw."
tag: "Custody"
read_time: "4 min"
order: 1
---

## TL;DR

- Owning a digital asset means controlling the private key that can move it. Custody is the business of protecting those keys.
- Hot, cold and MPC set-ups trade off speed of access against exposure to theft.
- The custody model directly shapes product UX: withdrawal times, approval steps and what you can promise a client.

## How it works

A blockchain records which addresses hold which assets. Whoever can sign a transaction with an address's **private key** can move those assets - there is no bank to reverse a mistake. A custodian's job is to keep keys safe while still letting authorised transactions through.

- **Hot wallets** keep keys on internet-connected systems. Transactions can be signed in seconds, but the attack surface is larger, so balances are usually kept small.
- **Cold storage** keeps keys offline, for example on air-gapped devices. Much safer, but moving funds needs manual, multi-person procedures that can take hours.
- **HSMs (hardware security modules)** are tamper-resistant hardware that protects keys and performs signing. They can run online or offline and are common in institutional set-ups.
- **MPC (multi-party computation)** splits signing between several parties so no single device ever holds the whole key. Shares can sit with different people, machines or organisations, and a quorum must cooperate to sign. It allows policy-based approvals without one point of failure.

Most institutional custodians combine these: a small hot balance for day-to-day flows, the bulk in cold or MPC-controlled storage, and policy engines that decide which path a transaction takes.

## Why users care

- **Trust:** "Are my assets safe if the provider is hacked or fails?" Segregation, insurance and audits matter as much as the technology.
- **Speed:** clients expect withdrawals to feel like a bank transfer. Cold-stored assets cannot always move instantly.
- **Control:** institutions and private-wealth clients often want approval rules - who can withdraw, how much, to which addresses.

## Product implications

- **Set expectations on timing.** If large withdrawals come from cold storage, say so up front and show a status the client can track, instead of a spinner.
- **Allow-listed addresses.** Requiring clients to register and verify withdrawal addresses in advance reduces fraud and mistakes; design the flow so it feels like adding a payee at a bank.
- **Approval flows are product.** Multi-approver policies need clear states (pending, approved, rejected) for both the client and operations.
- **Explain safety without jargon.** Clients rarely need to know what MPC is; they need to know who can move their assets and what protects them.

## Where I applied it

At Hex Trust, custody sat underneath Aura's **Hold** experience: portfolio value, P&amp;L and asset activity for private-wealth clients. See [Product position in the Aura case study]({{ '/work/aura/' | relative_url }}#product-position).

## Further reading

- [Securing your wallet - bitcoin.org](https://bitcoin.org/en/secure-your-wallet): online vs offline key storage, backups and multi-signature.
- [Multi-Party Threshold Cryptography - NIST](https://csrc.nist.gov/projects/threshold-cryptography): NIST's project on the threshold schemes behind MPC signing.
- [FIPS 140-3 - NIST](https://csrc.nist.gov/pubs/fips/140-3/final): the security standard HSMs and other cryptographic modules are certified against.
