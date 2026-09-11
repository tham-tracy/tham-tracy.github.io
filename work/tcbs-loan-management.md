---
layout: case-study
title: "TCBS margin & loan management system"
org: "Techcom Securities"
permalink: /work/tcbs-loan-management/
description: "A product case study on redesigning TCBS's core margin platform and coordinating a large-scale customer migration."
summary: >-
  Redesigning the core platform behind margin lending - from funding pools and
  collateral to risk monitoring and loan servicing - while coordinating the
  migration of approximately 900,000 customers across seven teams.
meta:
  - ["Role", "Product Manager"]
  - ["Scope", "Core margin platform"]
  - ["Scale", "≈900,000 customers"]
  - ["Delivery", "7 cross-functional teams"]
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
**Product.** The core system used to configure, operate and monitor margin
lending at Techcom Securities - from funding capacity and customer policies to
collateral, interest, repayment and reporting.

**My role.** Product Manager responsible for analysing the existing system,
defining the target capability model and aligning requirements across a
seven-team programme.

**Scale.** Approximately 900,000 customers moved to the new platform.
</div>

## Context and product problem

During the volatile stock-market conditions of 2021-2022, increased activity
exposed limitations in the existing margin platform. Its closed-source model
created strong vendor dependency, made feature changes slow and limited the
team's control over performance and future development.

The redesign needed to address five connected product needs:

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

## Discovery and system decomposition

I began by analysing the existing margin system, documenting its strengths
and limitations, researching industry approaches and comparing alternative
solutions. I then decomposed the domain into modules so requirements could be
owned and delivered without losing the end-to-end lending journey.

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

The capability map helped separate configurable product policy from individual
loan state. That distinction allowed business teams to define how a product
should behave while service teams could still understand what was happening
with one customer's loan.

## Funding, stock and customer limits

Margin lending capacity operates at several levels. The system needed a clear
relationship between funding sources, daily capacity, stock-specific
availability and the amount assigned to customer groups or individual
customers.

<div class="migration-grid">
  <article><span>01 · Source</span><h3>Funding pool</h3><p>Define available capacity and the commercial terms attached to a funding source.</p></article>
  <article><span>02 · Market</span><h3>Stock pool</h3><p>Control how much financing is available for an eligible security.</p></article>
  <article><span>03 · Segment</span><h3>Customer group</h3><p>Apply group-level allocation and policy consistently to a defined segment.</p></article>
  <article><span>04 · Customer</span><h3>Individual limit</h3><p>Expose the correct available capacity after the relevant policies are applied.</p></article>
</div>

The public portfolio intentionally omits real limits, pricing values,
allocation formulas and internal approval rules.

## Risk and collateral model

The risk module connects a customer's outstanding loan with the changing value
of their collateral portfolio. The product model covered initial margin,
maintenance margin and liquidation thresholds, together with alerts when a
portfolio moved into a higher-risk state.

The key design principle was explainability. A ratio should not appear as an
isolated number: users and service teams need to understand the portfolio
value, outstanding obligation, current status and available action associated
with it. Threshold values and escalation procedures remain confidential.

## Loan servicing and repayment

Once a loan is active, the system supports the information and actions needed
throughout its life: interest calculation, payment tracking, term changes,
early repayment, overdue handling and closure.

<ol class="journey journey-five">
  <li><span>01</span><strong>Initiate</strong><small>Customer starts a repayment</small></li>
  <li><span>02</span><strong>Retrieve</strong><small>Load the relevant loan details</small></li>
  <li><span>03</span><strong>Validate</strong><small>Check the request and available funds</small></li>
  <li><span>04</span><strong>Update</strong><small>Apply payment to loan and account</small></li>
  <li><span>05</span><strong>Confirm</strong><small>Show the completed result</small></li>
</ol>

The flow was designed around one customer promise: after repayment, the loan
balance, account balance and status must tell the same story.

## Debt-management experience

I created prototypes for the internal debt-management experience. The first
view prioritised search and filters so service users could quickly locate a
customer or loan and compare key information. The detail view then presented
the selected loan's policy, terms, current state and available actions.

<div class="delivery-grid">
  <article><h3>List view</h3><p>Search, filter and scan essential loan information across the portfolio.</p></article>
  <article><h3>Detail view</h3><p>Understand one loan's terms, policy, balance, status and relevant actions.</p></article>
</div>

Separating overview from detail kept the high-volume workflow efficient
without compressing every policy and action into one table.

## Migration and seven-team delivery

Approximately 900,000 customers were moved to the new platform. The
customer-facing objective was continuity: preserve access to correct margin
and loan information while moving to a system with greater product control
and scalability.

<div class="delivery-grid">
  <article><h3>Shared capability model</h3><p>Common module and state definitions gave seven teams one product language.</p></article>
  <article><h3>Journey-led planning</h3><p>Dependencies were discussed through complete customer and service journeys.</p></article>
  <article><h3>Clear ownership</h3><p>Each capability and cross-team dependency had an accountable delivery owner.</p></article>
  <article><h3>Customer readiness</h3><p>Release decisions remained anchored to continuity of essential customer actions.</p></article>
</div>

Detailed migration procedures, system architecture and control mechanisms are
not included in this public portfolio.

## Outcomes and lessons

The programme combined a broad domain redesign with the migration of
approximately 900,000 customers across seven teams. The work reinforced four
product lessons:

1. **Start with the capability model.** A complex financial platform becomes
   easier to plan when funding, product policy, customer rules, risk and loan
   state have clear boundaries.
2. **Make risk explainable.** Ratios and warnings are useful only when users
   understand what changed and what they can do next.
3. **Design for service users as well as customers.** Search, filtering and a
   clear loan-detail view are essential product experiences, not secondary
   administration.
4. **Treat platform change as a customer outcome.** Product control and
   scalability matter only if customers can continue using the service
   confidently.

<div class="confidentiality">
  This case study is based on my earlier margin-system product requirements.
  Real policy thresholds, pricing, allocation logic, internal architecture,
  migration procedures and customer information are omitted or generalised.
</div>
