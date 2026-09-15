---
layout: case-study
title: "TCBS margin lending platform redesign"
org: "Techcom Securities"
permalink: /work/tcbs-loan-management/
description: "Product ownership of a margin lending redesign covering purchasing power, risk controls, loan servicing and internal service tools, with approximately 900,000 customers migrated across seven teams."
summary: >-
  Product ownership of a seven-month redesign of margin lending, from purchasing
  power and risk controls to loan servicing and service-team tools. Approximately
  900,000 customers migrated across seven teams in one cutover, with no rollback required.
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
  <figure class="orbit-wrap">
    <div class="system-orbit" role="img" aria-label="Margin system: my team owned purchasing power, product policy, risk and margin calls, and loan servicing, connected to account, balance and money-movement services owned by other teams">
      <span class="orbit-link" style="--x:0;--y:-1">Accounts</span>
      <span class="orbit-own" style="--x:.7818;--y:-.6235">Product policy</span>
      <span class="orbit-own" style="--x:.9749;--y:.2225">Purchasing power</span>
      <span class="orbit-link" style="--x:.4339;--y:.901">Balances</span>
      <span class="orbit-own" style="--x:-.4339;--y:.901">Loan servicing</span>
      <span class="orbit-link" style="--x:-.9749;--y:.2225">Money movement</span>
      <span class="orbit-own" style="--x:-.7818;--y:-.6235">Risk &amp; margin calls</span>
      <strong>Margin<br>system</strong>
    </div>
    <figcaption class="orbit-legend"><i class="key-own" aria-hidden="true"></i>My team's scope <i class="key-link" aria-hidden="true"></i>Connected services</figcaption>
  </figure>
</div>

<div class="overview" markdown="1">
**Product.** The core margin lending platform at Techcom Securities, connecting purchasing power, lending capacity, collateral risk, repayment and loan servicing.

**Users.** Customers trading with margin, service teams managing loans, and business teams configuring products, limits and pricing.

**My ownership.** Product model and margin logic, customer and service journeys, product decisions, cross-team integration requirements, and migration readiness for the margin domain.
</div>

## Loan management mockups

<div class="tcbs-wireframes">
  <p class="tcbs-wireframes-note">English mockups with illustrative customer, loan and pricing data. Select a screen to open the full-size image in a new tab.</p>
  <figure>
    <a href="{{ '/assets/img/tcbs/loan-management-list-view.png' | relative_url }}" target="_blank" rel="noopener" aria-label="Open loan list mockup at full size in a new tab">
      <img src="{{ '/assets/img/tcbs/loan-management-list-view.png' | relative_url }}" width="2048" height="739" loading="eager" alt="Loan management list mockup with search filters, loan balances, statuses and actions for details, extension, collection, rate adjustment and action history">
    </a>
    <figcaption><strong>List view - search and triage.</strong> Filters narrow the loan portfolio, the highlighted overdue row draws attention, and loan actions are available alongside the selected record.</figcaption>
  </figure>
  <figure>
    <a href="{{ '/assets/img/tcbs/loan-management-detail-view.png' | relative_url }}" target="_blank" rel="noopener" aria-label="Open loan detail mockup at full size in a new tab">
      <img src="{{ '/assets/img/tcbs/loan-management-detail-view.png' | relative_url }}" width="2048" height="1414" loading="eager" alt="Loan detail mockup showing overdue status, principal and interest paid and remaining, dates, tiered pricing, fees and servicing actions">
    </a>
    <figcaption><strong>Detail view - explain and act.</strong> Status and servicing actions appear at the top. Paid and remaining balances, dates, pricing tiers and fees help service teams explain the loan and choose the next action.</figcaption>
  </figure>
</div>

## Context and product problem

During the volatile stock-market conditions of 2021-2022, increased activity exposed limitations in the existing margin platform. Its closed-source model created strong vendor dependency, slowed feature changes and limited the team's control over performance and future development.

The redesign was therefore more than a technology migration. The product needed to become easier to change, easier to operate and able to scale without breaking the customer journey.

<div class="feature-grid">
  <article><h3>Scale reliably</h3><p>Support a growing customer base and periods of higher market activity without degrading the experience.</p></article>
  <article><h3>Change faster</h3><p>Reduce the effort required to introduce or adjust lending products, policies and controls.</p></article>
  <article><h3>Own the product</h3><p>Move critical margin logic into capabilities the internal teams could develop and maintain.</p></article>
  <article><h3>Operate clearly</h3><p>Give service and business teams clearer visibility into loans, pricing, limits and customer status.</p></article>
</div>

For me, success meant preserving the financial behaviour customers already depended on while redesigning the domain into clearer product capabilities that multiple teams could own and evolve.

## My role as Product Owner

I was the Product Owner for margin lending. I owned the margin logic, the end-to-end flows and the product decisions behind them. My team's scope included purchasing power, loan servicing, margin calls and forced liquidation, while connected services such as accounts, balances and money movement were owned by other teams.

A large part of my work was turning a tightly coupled legacy system into a shared product model that seven teams could build against.

<div class="delivery-grid">
  <article><h3>Product model</h3><p>Decompose the margin domain, define capability boundaries and make the relationship between products, policies, limits and active loans explicit.</p></article>
  <article><h3>Journey design</h3><p>Define customer and service flows for purchasing power, repayment, extension, risk handling and loan servicing.</p></article>
  <article><h3>Cross-team integration</h3><p>Specify what the margin journey needed from account, balance and money-movement services, including ownership and confirmation points.</p></article>
  <article><h3>Delivery and migration</h3><p>Align requirements across teams, protect critical journeys during cutover and help define the readiness and rollback approach.</p></article>
</div>

## Discovery and system decomposition

I started by analysing the existing margin system, documenting its strengths and limitations, researching industry approaches and comparing alternative solutions. I then decomposed the domain into eight modules so requirements could be owned independently without losing the end-to-end lending journey.

<div class="feature-grid">
  <article><h3>Lending pools</h3><p>Funding-source capacity, configurable limits, commercial terms and utilisation.</p></article>
  <article><h3>Stock capacity</h3><p>Security-level financing availability, allocation and lending portfolios.</p></article>
  <article><h3>Collateral &amp; risk</h3><p>Portfolio valuation, margin ratios, thresholds, customer warnings and recovery actions.</p></article>
  <article><h3>Product configuration</h3><p>Terms, interest rates, fees, limits and risk parameters for each lending product.</p></article>
  <article><h3>Customer policies</h3><p>Customer groups, assigned policies, credit limits and trading permissions.</p></article>
  <article><h3>Loan operations</h3><p>Loan creation, interest, repayment, term changes, overdue handling and collection.</p></article>
  <article><h3>Reporting</h3><p>Operational activity, portfolio exposure, business performance and compliance reporting.</p></article>
  <article><h3>Service tooling</h3><p>Search, loan detail, servicing actions and action history for internal teams.</p></article>
</div>

### A key modelling decision: product policy vs. loan state

One of the most important design decisions was separating the rules of a product from the state of an individual customer's loan.

<div class="delivery-grid">
  <article><h3>Product policy</h3><p>Defines how the product behaves: rates, terms, limits, fees, extension rules and other configurable conditions.</p></article>
  <article><h3>Loan state</h3><p>Records what is happening to one loan: principal, accrued interest, payments, extension count, dates and current status.</p></article>
</div>

This gave business teams more control over product configuration without changing individual loans, while service teams could still see the exact policy and loan state behind what a customer was being charged.

## Key product decisions

### 1. Turn layered lending rules into one usable purchasing-power figure

Purchasing power is where the complexity of margin lending becomes visible to the customer: it answers a simple question - **how much can I buy now?**

The answer depended on several layers of capacity and policy:

<div class="migration-grid">
  <article><span>01 · Source</span><h3>Funding pool</h3><p>How much lending capacity is available from a funding source and under what commercial terms.</p></article>
  <article><span>02 · Market</span><h3>Stock capacity</h3><p>How much financing is available for an eligible security.</p></article>
  <article><span>03 · Segment</span><h3>Customer group</h3><p>Which allocation and lending policy applies to a defined customer segment.</p></article>
  <article><span>04 · Customer</span><h3>Individual limit</h3><p>The customer's available capacity after the relevant policies and limits are applied.</p></article>
</div>

The product challenge was to keep those controls explicit for business teams while exposing a single, reliable purchasing-power figure to the customer. Understating it could incorrectly block a trade; overstating it could allow exposure beyond the customer's permitted capacity.

### 2. Make risk actions explainable before they become restrictive

The risk flow connected outstanding debt with changes in collateral value. The system continuously evaluated the customer's margin position and moved through three stages when risk increased.

<div class="feature-grid">
  <article><h3>Monitor</h3><p>Recalculate the account's margin position as collateral values and outstanding obligations change.</p></article>
  <article><h3>Notify</h3><p>Use customer alerts to explain that action is required and what the customer can do next.</p></article>
  <article><h3>Restore</h3><p>Apply forced liquidation only when the account remains outside the required risk conditions.</p></article>
</div>

Two decisions shaped forced liquidation:

- **Sell only what is needed to restore the required position.** The objective was to address the shortfall without liquidating more of the customer's portfolio than necessary.
- **Prioritise more liquid assets.** Assets that were easier to execute reduced the risk of the recovery action itself failing or creating additional market impact.

The wider principle was explainability: a ratio should not appear as an isolated number. Customers and service teams need to understand the account value, outstanding obligations, current status and available action together.

### 3. Change the loan only after money movement is confirmed

Repayment crossed three responsibilities: the loan-management capability owned by my team, money movement owned by another team, and the core system.

<ol class="journey journey-five">
  <li><span>01</span><strong>Request</strong><small>Customer submits a repayment</small></li>
  <li><span>02</span><strong>Deduct</strong><small>Request the cash movement</small></li>
  <li><span>03</span><strong>Confirm</strong><small>Confirm the deduction in the core system</small></li>
  <li><span>04</span><strong>Apply</strong><small>Update the loan after confirmation</small></li>
  <li><span>05</span><strong>Notify</strong><small>Show the customer the result</small></li>
</ol>

**The key decision was to reduce the loan only after the cash deduction was confirmed.** This prevented the lending system from showing a repayment that had not actually moved money. After a successful repayment, the loan balance, account balance and repayment status could remain consistent.

Payments were allocated in a fixed order: fees and penalties first, then interest, then principal. Making that order explicit also made the remaining debt easier for service teams to explain.

### 4. Allow commercial flexibility without losing control

The platform needed to support real servicing cases without turning individual loans into unmanaged exceptions.

**Extension pricing.** Customers could extend a loan instead of closing it. The applicable product policy and the loan's extension count were visible together so service teams could explain the pricing based on the customer's actual loan state.

**Rate adjustment with approval.** Wealth managers could request an interest-rate adjustment for an individual loan and choose the effective date. Because the change affected what a customer paid, it required approval before taking effect and was recorded in the loan's action history.

The design principle was simple: allow controlled exceptions, but make every material change explainable and auditable.

## Designing for service teams, not only customers

I created prototypes for the internal debt-management experience. The tool separated portfolio-wide triage from the detail required to resolve an individual customer's case.

<div class="delivery-grid">
  <article><h3>List view</h3><p>Search and filter by loan ID, account, product, pricing policy, status and dates. Status is the primary signal so loans requiring attention are visible first.</p></article>
  <article><h3>Detail view</h3><p>Show loan status first, then principal, interest and fees split into original, paid and remaining amounts, followed by dates, pricing and servicing actions.</p></article>
</div>

<p><a href="#loan-management-mockups">View the loan list and detail mockups above.</a></p>

Three decisions made the experience useful for daily operations:

1. **Status first.** Service users need to identify which loans need attention before reading every field.
2. **Paid vs. remaining amounts.** Principal, interest and fees are separated so a service user can answer "what does this customer still owe, and why?" without manual calculation.
3. **Traceable actions.** Rate adjustments, extensions and collections remain accessible from the loan while action history records what changed.

This work reinforced that internal tools are part of the customer experience: the quality of the service team's information directly affects the quality of the explanation a customer receives.

## Cross-team integration model

Margin lending depended on capabilities owned by other teams. I planned each integration around the customer action the margin journey needed to complete.

| Connected capability | What the margin journey needed |
|---|---|
| Account registration | Open a margin account for an eligible customer. |
| Balance information | Read cash and asset balances as inputs to purchasing power. |
| Money movement | Deduct cash for repayment and confirm that the movement was reflected in the core system. |

My team owned the margin-specific decisions built on those inputs: how much a customer could buy, how a loan was serviced and when risk actions were required. Making ownership and confirmation points explicit helped seven teams work from the same end-to-end journey rather than isolated service requirements.

## Migration and seven-team delivery

Approximately 900,000 customers moved to the new platform in a single cutover. For customers, the objective was continuity: correct margin and loan information and access to essential actions from the first trading session on the new platform.

<div class="delivery-grid">
  <article><h3>Market-aware cutover</h3><p>Schedule the transition outside trading hours and use the weekend verification window before trading resumed.</p></article>
  <article><h3>Rollback readiness</h3><p>Prepare the rollback approach before migration. The cutover completed without needing to use it.</p></article>
  <article><h3>Shared capability model</h3><p>Use common module, policy and loan-state definitions so seven teams worked with the same product language.</p></article>
  <article><h3>Journey-led planning</h3><p>Validate dependencies through complete journeys such as account registration, purchasing power and repayment rather than service-by-service delivery alone.</p></article>
</div>

## Outcome and what I learned

In seven months, the programme redesigned the margin lending domain within a microservices platform and migrated approximately 900,000 customers across seven teams in one cutover, without rollback.

The project strengthened four principles I still use when working on financial products:

1. **Start with the product model.** Complex platforms become easier to plan when product policy, customer rules, limits, risk and transaction state have clear boundaries.
2. **Turn financial logic into understandable decisions.** A customer or service user should be able to understand not only the result, but why the system reached it and what action is available next.
3. **Design internal operations as product experiences.** Search, triage, loan detail and action history directly affect how effectively a financial product can be serviced.
4. **Measure platform change through customer continuity.** Architecture and scalability matter, but migration succeeds only when customers can continue using the product with correct financial information and essential journeys intact.

<div class="confidentiality">
  This case study is based on my margin-system product requirements and project experience. The English mockups illustrate the product design using demonstration customer, loan and pricing data. Product and capability descriptions are generalised. Actual company-specific thresholds, pricing values, allocation formulas, proprietary decision rules, internal architecture, detailed migration procedures and customer information are omitted.
</div>
