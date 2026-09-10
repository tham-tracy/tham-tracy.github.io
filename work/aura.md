---
layout: case-study
title: "Aura — wealth management platform"
org: "Aura"
permalink: /work/aura/
description: "Hex Trust's digital-asset wealth platform for private-wealth clients across APAC and MENA — onboarding, funding, trading, yield products and withdrawals on regulated custody infrastructure. Product case study."
summary: >-
  Hex Trust's digital-asset wealth platform for private-wealth clients across
  APAC and the Middle East — onboarding, funding, trading, yield products and
  withdrawals, run on the regulated custody infrastructure Hex Trust has
  operated since 2018.
meta:
  - ["Role", "Sole Product Manager"]
  - ["Period", "May 2025 – present"]
  - ["Platforms", "iOS, Android, web, ops admin"]
  - ["Team", "3 engineering squads + Design, QA, Compliance, Ops"]
  - ["Delivery", "Concept to production in under 9 months"]
---

<div class="phone-gallery" aria-label="Aura mobile screens">
  <div class="phone"><figure><div class="screen">Screen 1 — Home / portfolio</div><figcaption>Portfolio overview</figcaption></figure></div>
  <div class="phone"><figure><div class="screen">Screen 2 — Earn</div><figcaption>Earn product detail</figcaption></figure></div>
  <div class="phone"><figure><div class="screen">Screen 3 — On-ramp</div><figcaption>Add money</figcaption></figure></div>
  <div class="phone"><figure><div class="screen">Screen 4 — Off-ramp</div><figcaption>Withdraw</figcaption></figure></div>
  <div class="phone"><figure><div class="screen">Screen 5 — Transaction detail</div><figcaption>Activity</figcaption></figure></div>
</div>

<div class="todo" markdown="1">
**In progress.** Section 1 (Product snapshot) is drafted. Sections 2–10 are
placeholder briefs pending the interview. The five grey phone frames await
sanitised screenshots in `assets/img/aura/`.
</div>

<div class="overview" markdown="1">
**What it is.** Aura is Hex Trust's digital-asset wealth platform — onboard,
fund an account, trade, invest in yield products and withdraw, on regulated
custody infrastructure. Live on iOS, Android and web.

**My role.** Sole product manager, May 2025 – present. Owned the client apps
and the operational admin platform across three engineering squads, working
with Design, QA, Compliance and Operations. Taken from concept to production
in under nine months.

**Outcome.** _Covered in "Product outcomes and lessons" below — drafted after
the interview reaches that section._
</div>

## Product snapshot

**Aura is Hex Trust's digital-asset wealth platform** — a mobile and web
application that lets eligible private-wealth clients onboard, fund an account,
trade digital assets, invest in yield products, and withdraw. It runs on the
same regulated custody infrastructure Hex Trust has operated for institutions
since 2018, so client assets sit in licensed cold storage rather than on an
exchange.

**Who it serves.** High-net-worth and private-wealth clients in supported
markets across APAC and the Middle East. In practice they span a wide range —
from crypto-native investors who want regulated custody and yield, to
traditional wealth clients making their first allocation to digital assets. The
product has to be credible to both without overwhelming either.

**The alternative today.** Without Aura, a client assembles the same outcome
from four or five separate providers:

| Need | Typical standalone tool |
|------|------------------------|
| Trading | A centralised exchange |
| Custody | A separate wallet or custodian |
| Moving cash in and out | Bank transfers arranged privately |
| Yield | Separate earn / staking providers |
| Advice and service | A relationship manager outside the platform |

Every hand-off between them is a point of friction, cost, and counterparty
risk. Aura's proposition is to collapse that stack into one regulated platform
with a single onboarding, one portfolio view, and a relationship manager
attached.

**Where it sits.** Between a private bank (trusted, serviced, regulated — but
little native digital-asset capability), a brokerage (execution and order types
— but no custody or advice), and a self-custody wallet (control — but no
service, fiat rails, or yield). Aura takes the service model of the first, the
trading surface of the second, and the asset coverage of the third.

**Scope of this case study.** Onboarding and KYC; custody and portfolio; fiat
and digital-asset deposits and withdrawals; on- and off-ramp; Convert; spot,
limit and stop orders; recurring orders; Fixed Earn; Variable and Strategy
Earn; and the operational admin platform behind them. Borrow &amp; Lend, Card
and Statements are on the roadmap (shown "Coming Soon" in-app) and are not
claimed as delivered. OTC and TWAP execution are out of scope by choice, and
specific counterparties and internal operational rules are generalised
throughout.

## Mobile application mockups

<div class="note">A walk through the real screens above: what each one is
for, the key interaction, and one product decision visible in the design.</div>

## Customer journey and platform ecosystem

<div class="note">End-to-end journey from first open to funded and earning.
The systems involved — custody, ledger, pricing, KYC, banking partners — and
where Aura is the source of truth versus a consumer of someone else's.</div>

## Earn deep dive

<div class="note">Problem &rarr; decision &rarr; trade-off &rarr; outcome.
What "Earn" means on Aura, how yield is generated and represented, accrual and
payout mechanics, available vs. locked balance, and the risks disclosed to the
customer.</div>

## On-ramp deep dive

<div class="note">Moving value in: funding methods, the conversion and
pricing moment, settlement timing, failure and reversal handling, limits and
compliance checks, and what the customer sees at each step.</div>

## Off-ramp deep dive

<div class="note">Moving value out: withdrawal paths, holds and cooling-off
rules, fees and FX, reconciliation with banking partners, and the edge cases
— partial fills, failed payouts, clawbacks.</div>

## Supporting feature catalogue

<div class="note">The smaller features that round out the product —
recurring buys, price alerts, referrals, statements, support tooling. Kept
brief: what each does and why it earned a place.</div>

## Aura 1 to Aura 2 migration

<div class="note">Why the platform was rebuilt, what changed underneath,
how customers and balances were moved, the cutover approach, and how risk was
managed during the transition.</div>

## Operational and admin capabilities

<div class="note">The internal side: back-office tooling, manual recovery
paths, approvals and limits, monitoring and reconciliation, and how support
resolves customer issues.</div>

## Product outcomes and lessons

<div class="note">Sanitised results against the goals set out up top, what
worked, what you'd do differently, and what the next PM should know.</div>
