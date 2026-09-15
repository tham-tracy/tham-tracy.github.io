---
layout: case-study
title: "TCBS margin lending platform redesign"
org: "Techcom Securities"
permalink: /work/tcbs-loan-management/
description: "Redesigning a margin lending platform across product policy, purchasing power, risk, loan servicing and migration, with approximately 900,000 customers moved across seven teams."
summary: >-
  A seven-month redesign of the margin lending platform, from domain discovery
  and loan servicing to purchasing power, risk controls and migration.
  Approximately 900,000 customers moved across seven teams with no rollback required.
meta:
  - ["Role", "Product Owner"]
  - ["Duration", "7 months"]
  - ["Scale", "≈900,000 customers"]
  - ["Delivery", "7 teams"]
  - ["Migration", "No rollback required"]
---

<style>
.case-visual-tcbs .orbit-wrap {
  container-type: inline-size;
  width: 100%;
  max-width: 30rem;
  min-width: 0;
  justify-self: center;
  margin: 0;
}
.case-visual-tcbs .system-orbit {
  --rx: clamp(5.8rem, 36cqi, 10.4rem);
  --ry: var(--rx);
  --core: clamp(4rem, 24cqi, 7.5rem);
  height: calc(var(--ry) * 2 + 3.5rem);
  position: relative;
}
.case-visual-tcbs .system-orbit::before {
  position: absolute;
  top: 50%;
  left: 50%;
  width: calc(var(--rx) * 2);
  height: calc(var(--ry) * 2);
  border: 1px solid rgba(57,230,203,.34);
  border-radius: 50%;
  transform: translate(-50%, -50%);
  content: "";
}
.case-visual-tcbs .system-orbit::after { display: none; }
.case-visual-tcbs .system-orbit strong { width: var(--core); }
.case-visual-tcbs .system-orbit span {
  left: calc(50% + var(--rx) * var(--x));
  top: calc(50% + var(--ry) * var(--y));
  width: max-content;
  max-width: 9rem;
  padding: .42rem .7rem;
  border: 1px solid rgba(57,230,203,.55);
  color: #eafffb;
  background: #12403f;
  font-size: .72rem;
  line-height: 1.2;
  white-space: normal;
  text-align: center;
}
.case-module-grid { grid-template-columns: repeat(4, 1fr); }
@container (max-width: 25rem) {
  .case-visual-tcbs .system-orbit { --ry: calc(var(--rx) * 1.45); }
  .case-visual-tcbs .system-orbit strong { font-size: .85rem; }
  .case-visual-tcbs .system-orbit span { max-width: 5.4rem; padding: .3rem .5rem; font-size: .62rem; }
}
@container (max-width: 19rem) {
  .case-visual-tcbs .system-orbit span { max-width: 4.8rem; font-size: .58rem; }
}
@media (max-width: 64rem) {
  .case-module-grid { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 42rem) {
  .case-module-grid { grid-template-columns: 1fr; }
}
</style>

<div class="case-visual case-visual-tcbs">
  <div>
    <p class="eyebrow">Financial infrastructure</p>
    <p class="display-title">From vendor dependency<br>to product control.</p>
  </div>
  <figure class="orbit-wrap">
    <div class="system-orbit" role="img" aria-label="Margin system modules: lending pools, stock capacity, customer groups, product configuration, asset management, risk and margin calls, loan management and reporting">
      <span style="--x:0;--y:-1">Lending pools</span>
      <span style="--x:0.7071;--y:-0.7071">Stock capacity</span>
      <span style="--x:1;--y:0">Customer groups</span>
      <span style="--x:0.7071;--y:0.7071">Product configuration</span>
      <span style="--x:0;--y:1">Asset management</span>
      <span style="--x:-0.7071;--y:0.7071">Risk &amp; margin calls</span>
      <span style="--x:-1;--y:0">Loan management</span>
      <span style="--x:-0.7071;--y:-0.7071">Reporting</span>
      <strong>Margin<br>system</strong>
    </div>
  </figure>
</div>

<div class="overview" markdown="1">
**Product.** The core margin lending platform at Techcom Securities, covering lending capacity, purchasing power, collateral risk, repayment and loan servicing.

**Challenge.** Replace a tightly coupled, vendor-dependent platform with capabilities internal teams could own and evolve, while preserving the financial behaviour customers already relied on.

**My scope.** Product Owner for margin lending, responsible for the product model, lending and risk logic, customer and service journeys, cross-team integration requirements and migration readiness.
</div>

## Discovery - redesigning the margin domain

During the volatile stock-market conditions of 2021-2022, higher activity exposed limitations in the existing platform. Feature changes were slow, operational visibility was limited and critical margin behaviour depended heavily on a closed-source vendor system.

I started by analysing the existing product, documenting its strengths and constraints, researching alternative approaches and mapping the domain into capabilities that could be owned independently without breaking the end-to-end lending journey.

<div class="feature-grid case-module-grid">
  <article><h3>Lending pools</h3><p>Funding-source capacity, configurable limits, commercial terms and utilisation.</p></article>
  <article><h3>Stock capacity</h3><p>Security-level financing availability, allocation and lending portfolios.</p></article>
  <article><h3>Customer groups</h3><p>Customer tiers with assigned policies, credit limits and trading permissions.</p></article>
  <article><h3>Product configuration</h3><p>Terms, interest rates, fees, limits and risk parameters for each lending product.</p></article>
  <article><h3>Asset management</h3><p>Cash and securities used as collateral and as inputs to purchasing power.</p></article>
  <article><h3>Risk &amp; margin calls</h3><p>Margin ratios, thresholds, customer warnings and recovery actions.</p></article>
  <article><h3>Loan management</h3><p>The loan lifecycle from creation to collection, including servicing tools for internal teams.</p></article>
  <article><h3>Reporting</h3><p>Operational activity, portfolio exposure, business performance and compliance reporting.</p></article>
</div>

### Separate product policy from loan state

One of the most important modelling decisions was separating the rules of a lending product from the state of an individual customer's loan.

<div class="delivery-grid">
  <article><h3>Product policy</h3><p>Defines how the product behaves: rates, terms, limits, fees, extension rules and other configurable conditions.</p></article>
  <article><h3>Loan state</h3><p>Records what is happening to one loan: principal, accrued interest, payments, extension count, dates and current status.</p></article>
</div>

This gave business teams more control over product configuration while keeping each customer's active loan understandable and traceable for service teams.

## Loan management - make every loan explainable

A major part of the redesign was the internal debt-management experience. Service teams needed to find the right loan quickly, understand what the customer owed and take the next action without reconstructing the account from multiple systems.

<div class="tcbs-wireframes">
  <p class="tcbs-wireframes-note">English mockups with illustrative customer, loan and pricing data. Select a screen to open the full-size image in a new tab.</p>
  <figure>
    <a href="{{ '/assets/img/tcbs/loan-management-list-view.png' | relative_url }}" target="_blank" rel="noopener" aria-label="Open loan list mockup at full size in a new tab">
      <img src="{{ '/assets/img/tcbs/loan-management-list-view.png' | relative_url }}" width="2048" height="739" loading="eager" alt="Loan management list mockup with search filters, loan balances, statuses and servicing actions">
    </a>
    <figcaption><strong>List view - search and triage.</strong> Filters narrow the portfolio, status surfaces the loans that need attention and actions stay close to the selected record.</figcaption>
  </figure>
  <figure>
    <a href="{{ '/assets/img/tcbs/loan-management-detail-view.png' | relative_url }}" target="_blank" rel="noopener" aria-label="Open loan detail mockup at full size in a new tab">
      <img src="{{ '/assets/img/tcbs/loan-management-detail-view.png' | relative_url }}" width="2048" height="1414" loading="lazy" alt="Loan detail mockup showing loan status, principal and interest paid and remaining, dates, pricing and servicing actions">
    </a>
    <figcaption><strong>Detail view - explain and act.</strong> Status and servicing actions come first; balances, dates, pricing and fees provide the context needed to explain the loan.</figcaption>
  </figure>
</div>

<div class="feature-grid">
  <article><h3>Status first</h3><p>Overdue, due, current and closed states make triage the first step rather than forcing users to inspect every field.</p></article>
  <article><h3>Paid vs. remaining</h3><p>Principal, interest and fees are separated into what was charged, what was paid and what is still outstanding.</p></article>
  <article><h3>Traceable actions</h3><p>Extensions, collections and rate changes remain accessible from the loan, with history showing what changed.</p></article>
</div>

The principle was simple: internal tools are part of the customer experience. If a service user can understand a loan quickly, they can give the customer a clearer and more reliable answer.

## Purchasing power - turn layered controls into one usable number

For the customer, margin complexity becomes visible as one number: **how much can I buy now?** Behind that figure, the platform had to apply several layers of funding capacity and policy consistently.

<div class="migration-grid">
  <article><span>01 · Source</span><h3>Funding pool</h3><p>Available lending capacity and the commercial terms attached to a funding source.</p></article>
  <article><span>02 · Market</span><h3>Stock capacity</h3><p>How much financing is available for an eligible security.</p></article>
  <article><span>03 · Segment</span><h3>Customer group</h3><p>The allocation and lending policy applied to a defined customer segment.</p></article>
  <article><span>04 · Customer</span><h3>Individual limit</h3><p>The customer's available capacity after the relevant policies and limits are applied.</p></article>
</div>

The design challenge was to keep those controls explicit for business teams while exposing one reliable figure to the customer. Understating purchasing power could incorrectly block a trade; overstating it could allow exposure beyond the permitted capacity.

## Risk - intervene progressively before forced liquidation

The risk flow connected outstanding debt with changing collateral value. Rather than treating liquidation as a single event, the product moved through a progression of monitoring, warning and recovery.

<div class="feature-grid">
  <article><h3>Monitor</h3><p>Recalculate the account's margin position as collateral values and outstanding obligations change.</p></article>
  <article><h3>Notify</h3><p>Tell the customer when action is required and make the available next steps clear.</p></article>
  <article><h3>Restore</h3><p>Apply forced liquidation only when the account remains outside the required risk conditions.</p></article>
</div>

Two product decisions shaped forced liquidation:

- **Sell only what is needed to restore the required position.** Address the shortfall without liquidating more of the customer's portfolio than necessary.
- **Prioritise more liquid assets.** Favour assets that are easier to execute, reducing the risk that the recovery action itself fails or creates unnecessary market impact.

The wider principle was explainability: a margin ratio should not appear as an isolated number. Customers and service teams need to understand the account value, outstanding obligations, current status and available action together.

## Repayment - keep cash movement and loan state consistent

Repayment crossed the loan-management capability owned by my team, money movement owned by another team and the core system.

<ol class="journey journey-five">
  <li><span>01</span><strong>Request</strong><small>Customer submits a repayment</small></li>
  <li><span>02</span><strong>Deduct</strong><small>Request the cash movement</small></li>
  <li><span>03</span><strong>Confirm</strong><small>Confirm the deduction in the core system</small></li>
  <li><span>04</span><strong>Apply</strong><small>Update the loan after confirmation</small></li>
  <li><span>05</span><strong>Notify</strong><small>Show the customer the result</small></li>
</ol>

**The loan was reduced only after the cash deduction was confirmed.** This prevented the lending system from showing a repayment that had not actually moved money and kept the loan balance, account balance and repayment status aligned.

Payments followed an explicit allocation order: fees and penalties first, then interest, then principal. Making the order visible also made the remaining debt easier for service teams to explain.

## Pricing and servicing controls

The platform needed enough flexibility to handle real customer cases without turning individual loans into unmanaged exceptions.

<div class="delivery-grid">
  <article><h3>Extension pricing</h3><p>Customers could extend a loan instead of closing it. The applicable product policy and extension count were shown together so the resulting pricing could be explained from the actual loan state.</p></article>
  <article><h3>Rate adjustment with approval</h3><p>Wealth managers could request a customer-specific rate and effective date, but the change required approval and remained recorded in the loan's action history.</p></article>
</div>

The product principle was to allow controlled flexibility while keeping every material change explainable and auditable.

## Cross-team integration

Margin lending depended on services owned by other teams. I defined each integration around what the customer journey needed to complete and where confirmation was required.

| Connected capability | What the margin journey needed |
|---|---|
| Account registration | Open a margin account for an eligible customer. |
| Balance information | Read cash and asset balances as inputs to purchasing power. |
| Money movement | Deduct cash for repayment and confirm that the movement was reflected in the core system. |

My team owned the margin-specific decisions built on those inputs: how much a customer could buy, how a loan was serviced and when risk actions were required. Explicit ownership and confirmation points helped seven teams work from the same end-to-end journey rather than isolated service requirements.

## Migration and seven-team delivery

Approximately 900,000 customers moved to the new platform in a single cutover. The customer outcome was continuity: correct margin and loan information and access to essential actions from the first trading session on the new platform.

<div class="delivery-grid">
  <article><h3>Market-aware cutover</h3><p>Schedule the transition outside trading hours and use the weekend verification window before trading resumed.</p></article>
  <article><h3>Rollback readiness</h3><p>Prepare the rollback approach before migration. The cutover completed without needing to use it.</p></article>
  <article><h3>Shared product model</h3><p>Use common capability, policy and loan-state definitions so seven teams worked with the same product language.</p></article>
  <article><h3>Journey-led planning</h3><p>Validate dependencies through complete journeys such as account registration, purchasing power and repayment.</p></article>
</div>

---

## Outcomes and lessons

In seven months, the programme redesigned the margin lending domain within a microservices platform and migrated approximately 900,000 customers across seven teams in one cutover, without rollback.

Three principles stood out from the work:

1. **Start with the product model.** Clear boundaries between product policy, customer rules, limits, risk and loan state make a complex financial platform easier to change.
2. **Make financial logic explainable.** Customers and service users need to understand not only the result, but why the system reached it and what action is available next.
3. **Treat platform migration as a product outcome.** Architecture and scalability matter, but success is ultimately whether customers retain correct information and working journeys through the transition.

<div class="confidentiality">
  This case study is based on my margin-system product requirements and project experience. The English mockups use demonstration customer, loan and pricing data. Product descriptions are generalised. Company-specific thresholds, pricing values, allocation formulas, proprietary decision rules, internal architecture, detailed migration procedures and customer information are omitted.
</div>
