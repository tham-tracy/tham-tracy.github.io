---
layout: case-study
title: "TCBS loan management system"
org: "Techcom Securities (TCBS)"
permalink: /work/tcbs-loan-management/
description: "The platform behind the lending lifecycle at Techcom Securities — origination through servicing — and a migration of roughly 900,000 customers delivered across seven teams."
summary: >-
  The platform behind the lending lifecycle at Techcom Securities:
  origination, underwriting, disbursement and servicing — rebuilt and migrated
  for roughly 900,000 customers across a seven-team delivery programme.
meta:
  - ["Role", "Product Manager"]
  - ["Scope", "Loan lifecycle platform, migration"]
  - ["Timeframe", "— to —"]
  - ["Delivery", "Seven teams"]
---

<div class="todo" markdown="1">
**Draft skeleton.** Section order is locked; the prose is placeholder. We fill
each section in the interview. **Sanitisation check:** confirm the 900,000
figure is publicly disclosable; "Core platform architecture" and "Business and
risk rules" will describe patterns and reasoning, not the real system topology
or real rule values.
</div>

<div class="overview" markdown="1">
**What it is.** <!-- the loan management system in plain terms -->
**My role.** <!-- what you owned across the seven teams, dates -->
**Outcome.** <!-- 2–3 headline results, sanitised -->
</div>

## Loan-management product overview

<div class="note">What the system does, which lending products it supports,
and who uses it — customers, relationship managers, credit, operations,
finance. The one-minute picture before the detail.</div>

## Lending lifecycle

<div class="note">Origination &rarr; application &rarr; underwriting &rarr;
approval &rarr; disbursement &rarr; servicing &rarr; repayment &rarr; closure
(and the unhappy paths: decline, delinquency, restructure, write-off). Where
the state lives and what moves it forward.</div>

## Main capabilities

<div class="note">The core capability set — application intake, decisioning,
limit and collateral management, schedule generation, statements, collections
support. What each is for, kept tight.</div>

## Business and risk rules

<div class="note">The rule categories that govern lending decisions and
servicing — eligibility, exposure and limits, pricing, collateral, past-due
handling — described as patterns and the reasoning behind them. No real
thresholds or proprietary criteria.</div>

## Core platform architecture

<div class="note">The shape of the platform at a conceptual level: the
services and their responsibilities, the source of truth for balances and
statuses, how money movement and data movement are kept consistent, and how
retries, duplicates and partial failures are handled. Illustrative, not the
real topology.</div>

## 900,000-customer migration

<div class="note">Moving the existing loan book onto the new platform:
sequencing, data mapping and reconciliation, dual-running, cutover, rollback
planning, and how customer impact was kept to a minimum.</div>

## Seven-team delivery model

<div class="note">How the programme was organised — team boundaries,
ownership, dependencies and interfaces, the planning cadence, and the PM's
role in keeping seven teams pointed at one outcome.</div>

## Outcomes and lessons

<div class="note">Sanitised results against the programme goals, what the
delivery model got right, the hardest trade-offs, and what you'd carry into
the next platform migration.</div>
