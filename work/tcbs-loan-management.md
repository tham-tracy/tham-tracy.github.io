---
layout: case-study
title: "TCBS margin lending platform redesign"
org: "Techcom Securities"
permalink: /work/tcbs-loan-management/
description: "Redesigning margin lending across purchasing power, risk, loan servicing and service tools, with approximately 900,000 customers migrated across seven teams."
summary: >-
  A seven-month redesign of margin lending, from purchasing power and risk
  controls to loan servicing and service-team tools. Approximately 900,000
  customers migrated across seven teams, with no rollback required.
meta:
  - ["Role", "Product Owner"]
  - ["Duration", "7 months"]
  - ["Scale", "≈900,000 customers"]
  - ["Delivery", "7 teams"]
  - ["Migration", "No rollback required"]
---

<div class="case-visual case-visual-tcbs">
  <div>
    <p class="eyebrow">Financial infrastructure</p>
    <p class="display-title">From vendor dependency<br>to product control.</p>
  </div>
  <div class="system-orbit" aria-label="Margin system capability overview">
    <span>Funding pools</span><span>Stock loans</span><span>Risk</span>
    <span>Products</span><span>Customers</span><strong>Margin<br>system</strong>
  </div>
</div>

<div class="overview" markdown="1">
**Product.** The core margin lending platform at Techcom Securities, connecting
purchasing power, funding limits, collateral, repayment and loan servicing.

**Users.** Customers trading with margin, service teams managing loans, and
business teams configuring products and pricing.

**My scope.** Margin logic, customer and service flows, product decisions, and
integration planning with the teams responsible for connected services.
</div>

## Context and product problem

During the volatile stock-market conditions of 2021-2022, increased activity
exposed limitations in the existing margin platform. Its closed-source model
created vendor dependency, slowed feature changes and limited the team's
control over performance and future development.

The redesign needed to address six connected product needs:

<div class="feature-grid">
  <article><h3>Responsive experience</h3><p>Support customers reliably during periods of higher market activity.</p></article>
  <article><h3>Faster change</h3><p>Reduce the time required to introduce or adjust margin capabilities.</p></article>
  <article><h3>Scalability</h3><p>Serve a growing customer base without degrading the experience.</p></article>
  <article><h3>Product control</h3><p>Give internal teams greater ownership of development and maintenance.</p></article>
  <article><h3>Operational clarity</h3><p>Make lending information easier for service and business teams to manage.</p></article>
  <article><h3>Customer continuity</h3><p>Move to the new platform without disrupting existing customer journeys.</p></article>
</div>

This reframed the work from a technical replacement into a product-system
redesign: define what the platform must enable, who needs each capability and
how the modules work together.

## My role

I was the Product Owner for margin lending. I owned the margin logic, the
flows and the product decisions behind them. Within the new microservices
platform, my team's scope covered purchasing power, loan servicing, margin
calls and forced liquidation.

A central part of my work was defining what each margin journey needed from
other teams' services and agreeing on integration responsibilities and the
delivery plan.

## Discovery and system decomposition

I analysed the existing system, documented its strengths and limitations,
researched industry approaches and compared alternative solutions. I then
decomposed the margin domain into eight modules, giving teams clear ownership
while preserving the end-to-end lending journey.

<div class="feature-grid">
  <article><h3>Lending pools</h3><p>Funding-source capacity, configurable limits, pricing terms and utilisation monitoring.</p></article>
  <article><h3>Stock loans</h3><p>Stock-specific pools, customer-group allocation and lending portfolios.</p></article>
  <article><h3>Collateral &amp; risk</h3><p>Portfolio valuation, margin ratios, thresholds and customer alerts.</p></article>
  <article><h3>Product configuration</h3><p>Margin-product terms, interest rates, fees, limits and risk parameters.</p></article>
  <article><h3>Customer policies</h3><p>Customer groups, assigned policies, credit limits and trading permissions.</p></article>
  <article><h3>Loan operations</h3><p>Loan creation, interest, payments, term changes, overdue handling and collection.</p></article>
  <article><h3>Reporting</h3><p>Operational activity, portfolio exposure, business performance and compliance reporting.</p></article>
  <article><h3>Service tooling</h3><p>Searchable loan information and clear detail views for customer-support teams.</p></article>
</div>

**The key design decision was separating product policy from loan state.**

<div class="delivery-grid">
  <article><h3>Product policy</h3><p>Defines rates, terms, limits and extension pricing for a margin product.</p></article>
  <article><h3>Loan state</h3><p>Records one customer's balances, accrued interest, extension count and current status.</p></article>
</div>

This separated product configuration from the record of each active loan.
Service teams could see both the applicable policy and the customer's current
obligations, making the resulting charges easier to explain.

## How margin fits into the platform

Margin lending depended on capabilities owned by other teams. I planned
integrations around the customer action each dependency needed to support.

| Connected capability | What the margin journey needed |
|---|---|
| Account registration | Open a margin account for an eligible customer. |
| Balance information | Read cash and asset balances as inputs to purchasing power. |
| Money movement | Deduct cash for repayment and confirm that the movement was reflected in the core system. |

My team owned the margin-specific decisions built on those inputs: how much
a customer could buy, how a loan was serviced and when risk actions were needed.
The integration plan made responsibilities and confirmation points explicit.

## Purchasing power

Purchasing power is where margin lending becomes visible to the customer:
it tells them how much they can buy. It uses cash balances and the lending
value of eligible assets, subject to the customer's margin policy and
applicable limits.

Accuracy matters in both directions. Understating purchasing power can block
a trade the customer is entitled to make. Overstating it can allow exposure
beyond the account's permitted capacity. This made balance inputs, asset
eligibility and policy application central to the product design.

## Funding, stock and customer limits

Lending capacity operates at several levels. The platform needed to connect
funding-source capacity with stock availability, customer-group allocations
and individual limits.

<div class="migration-grid">
  <article><span>01 · Source</span><h3>Funding pool</h3><p>Define available capacity and the commercial terms attached to a funding source.</p></article>
  <article><span>02 · Market</span><h3>Stock pool</h3><p>Control how much financing is available for an eligible security.</p></article>
  <article><span>03 · Segment</span><h3>Customer group</h3><p>Apply group-level allocation and policy consistently to a defined segment.</p></article>
  <article><span>04 · Customer</span><h3>Individual limit</h3><p>Expose the correct available capacity after the relevant policies are applied.</p></article>
</div>

Each level constrains what is available to the customer. The product challenge
was to expose a usable purchasing-power figure while keeping the underlying
allocation and policy understandable to business teams.

## Margin calls and forced liquidation

The risk model connected outstanding debt with changes in collateral value.
It covered initial margin, maintenance requirements and liquidation conditions.
Customer and service views needed to explain the account's ratio, status and
available action together.

<div class="feature-grid">
  <article><h3>Monitor</h3><p>Recalculate the account's margin position as asset values change.</p></article>
  <article><h3>Notify</h3><p>Use in-app and SMS reminders to explain when the customer needs to add cash or reduce exposure.</p></article>
  <article><h3>Restore</h3><p>Apply forced liquidation when the account remains below the required level and the applicable conditions are met.</p></article>
</div>

Two product decisions shaped forced liquidation:

- **Target the amount needed to restore the required ratio.** The design aimed
  to retain as much of the customer's portfolio as possible while addressing
  the account's shortfall.
- **Prioritise liquid assets.** The selection approach favoured assets that
  were easier to sell. Execution still depended on market conditions and
  available liquidity.

Clear warnings and visible next steps helped customers understand the
consequences before a forced action. Company-specific thresholds, timing
rules and liquidation logic are omitted from this public case study.

## Loan servicing and repayment

Repayment crossed the loan-management capability owned by my team,
money movement owned by another team, and the core system.

<ol class="journey journey-five">
  <li><span>01</span><strong>Request</strong><small>Customer submits a repayment</small></li>
  <li><span>02</span><strong>Deduct</strong><small>Request the cash movement</small></li>
  <li><span>03</span><strong>Confirm</strong><small>Confirm the deduction in the core system</small></li>
  <li><span>04</span><strong>Apply</strong><small>Update the loan after confirmation</small></li>
  <li><span>05</span><strong>Notify</strong><small>Show the customer the result</small></li>
</ol>

**The key decision was to reduce the loan only after the cash deduction was
confirmed.** This addressed the risk of showing a loan as repaid before the
money had left the account. The intended outcome was consistent loan balances,
account balances and repayment status.

In the product model, payments were allocated to fees and penalties first,
then interest, then principal. An explicit allocation order made it possible
to show which obligations a payment settled and what remained outstanding.

### Extension pricing

Customers could extend a loan instead of fully repaying and closing it.
The product used tiered extension pricing, with successive extensions
applying a higher rate to unpaid interest.

The design made the applicable pricing policy and extension count visible
together. Service teams could explain the cost of another extension using
the customer's actual loan state. Specific rates and pricing formulas are
not included here.

### Rate adjustments with approval

Wealth managers could request an interest-rate adjustment for an individual
loan and choose its effective date. Each adjustment required approval before
taking effect and was recorded in the loan's action history.

This supported client-specific pricing decisions while making the approved
change, its timing and its effect on the loan traceable.

## Debt-management experience

I created prototypes for service teams managing loans. The experience
separated portfolio-wide search and triage from the detail needed to resolve
one customer's case.

<div class="delivery-grid">
  <article><h3>List view</h3><p>Filter by loan ID, account, product, pricing policy, status and dates. Identify overdue, due, current and closed loans, then open details or relevant actions.</p></article>
  <article><h3>Detail view</h3><p>See status first, followed by principal, interest and fees split into original, paid and remaining amounts. Review dates, remaining term, pricing policy and available actions.</p></article>
</div>

Three decisions made the tool useful for daily servicing:

1. **Put status first.** Service teams need to identify which loans require
   attention before inspecting every field.
2. **Show paid and remaining amounts.** Separate principal, interest and fees
   so users can explain what a customer still owes without manual calculation.
3. **Keep actions traceable.** Place rate adjustment, extension and collection
   actions within reach, with an action history for reviewing changes.

These were product experiences for an internal audience whose work directly
affected the customer's understanding of their loan.

## Migration and seven-team delivery

Approximately 900,000 customers moved to the new platform in a single
cutover. The objective was to preserve correct margin and loan information
and access to essential actions from the first trading session on the new
platform.

<div class="delivery-grid">
  <article><h3>Market-aware cutover</h3><p>Schedule the transition outside trading hours, with a weekend verification window before trading resumed.</p></article>
  <article><h3>Rollback readiness</h3><p>Prepare a rollback plan in advance. The migration completed without using it.</p></article>
  <article><h3>Shared product model</h3><p>Use common module and loan-state definitions to align seven delivery teams.</p></article>
  <article><h3>Explicit integration ownership</h3><p>Work through complete journeys, agree on dependencies and assign an owner to each capability.</p></article>
</div>

The public case study describes the delivery approach and outcome at a high
level. Detailed cutover procedures and recovery mechanisms are omitted.

## Outcomes and lessons

In seven months, the programme redesigned the margin domain within a
microservices platform and migrated approximately 900,000 customers across
seven teams in a single cutover. No rollback was required.

The work reinforced four product lessons:

1. **Start with the capability model.** Clear boundaries between funding,
   product policy, customer rules, risk and loan state make a complex platform
   easier to plan and deliver.
2. **Make risk explainable.** Pair ratios and warnings with the reason for
   the change and the action available to the user.
3. **Treat service teams as product users.** Search, triage, loan details and
   action history shape how well teams can support customers.
4. **Define success through customer continuity.** A platform transition
   needs correct financial information and usable customer journeys as well
   as technical completion.

<div class="confidentiality">
  This case study is based on my margin-system product requirements and project
  experience. Capability descriptions are generalised. Company-specific
  thresholds, pricing values, allocation formulas, internal architecture,
  detailed migration procedures and customer information are omitted.
</div>
