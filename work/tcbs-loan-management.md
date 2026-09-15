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
**Product.** Techcom Securities' core margin lending platform, covering lending capacity, purchasing power, risk, repayment and loan servicing.

**Challenge.** Replace a vendor-dependent platform with capabilities internal teams could own and evolve without disrupting existing financial behaviour.

**My scope.** Product Owner for margin lending, covering the product model, lending and risk logic, service journeys, integrations and migration readiness.
</div>

## Discovery - redesigning the margin domain

Higher market activity exposed slow product changes, limited operational visibility and heavy dependence on a closed-source vendor system.

I analysed the existing product and mapped the domain into capabilities teams could own independently while preserving the end-to-end lending journey.

<div class="feature-grid case-module-grid">
  <article><h3>Lending pools</h3><p>Funding capacity, limits, commercial terms and utilisation.</p></article>
  <article><h3>Stock capacity</h3><p>Security-level financing availability and allocation.</p></article>
  <article><h3>Customer groups</h3><p>Customer tiers, policies, limits and permissions.</p></article>
  <article><h3>Product configuration</h3><p>Terms, rates, fees, limits and risk parameters.</p></article>
  <article><h3>Asset management</h3><p>Cash and securities used for collateral and purchasing power.</p></article>
  <article><h3>Risk &amp; margin calls</h3><p>Margin ratios, thresholds, warnings and recovery actions.</p></article>
  <article><h3>Loan management</h3><p>Loan lifecycle and servicing tools from creation to collection.</p></article>
  <article><h3>Reporting</h3><p>Operational, exposure, business and compliance reporting.</p></article>
</div>

### Separate product policy from loan state

A key decision was separating product rules from each customer's active loan.

<div class="delivery-grid">
  <article><h3>Product policy</h3><p>Rates, terms, limits, fees and extension rules.</p></article>
  <article><h3>Loan state</h3><p>Principal, interest, payments, extensions, dates and status.</p></article>
</div>

This let business teams manage product configuration while service teams could still explain each active loan clearly.

## Loan management - make every loan explainable

Service teams needed to find the right loan quickly, understand what the customer owed and take the next action without piecing information together across systems.

<div class="tcbs-wireframes">
  <p class="tcbs-wireframes-note">English mockups with illustrative customer, loan and pricing data.</p>
  <figure>
    <a href="{{ '/assets/img/tcbs/loan-management-list-view.png' | relative_url }}" target="_blank" rel="noopener" aria-label="Open loan list mockup at full size in a new tab">
      <img src="{{ '/assets/img/tcbs/loan-management-list-view.png' | relative_url }}" width="2048" height="739" loading="eager" alt="Loan management list mockup with search filters, loan balances, statuses and servicing actions">
    </a>
    <figcaption><strong>List view - search and triage.</strong> Filters, status and actions help service teams find and handle the right loan quickly.</figcaption>
  </figure>
  <figure>
    <a href="{{ '/assets/img/tcbs/loan-management-detail-view.png' | relative_url }}" target="_blank" rel="noopener" aria-label="Open loan detail mockup at full size in a new tab">
      <img src="{{ '/assets/img/tcbs/loan-management-detail-view.png' | relative_url }}" width="2048" height="1414" loading="lazy" alt="Loan detail mockup showing loan status, principal and interest paid and remaining, dates, pricing and servicing actions">
    </a>
    <figcaption><strong>Detail view - explain and act.</strong> Status, balances, dates, pricing and actions provide the context needed to resolve a case.</figcaption>
  </figure>
</div>

<div class="feature-grid">
  <article><h3>Status first</h3><p>Surface overdue, due, current and closed loans quickly.</p></article>
  <article><h3>Paid vs. remaining</h3><p>Separate what was charged, paid and still outstanding.</p></article>
  <article><h3>Traceable actions</h3><p>Keep extensions, collections, rate changes and history together.</p></article>
</div>

Two servicing actions needed flexibility without losing control:

<div class="delivery-grid">
  <article><h3>Extension pricing</h3><p>Show product policy with extension count so the resulting price can be explained from the loan's actual state.</p></article>
  <article><h3>Rate adjustment with approval</h3><p>Allow a customer-specific rate and effective date, with approval and action history.</p></article>
</div>

Internal tools are part of the customer experience: clearer servicing leads to clearer customer answers.

## Purchasing power - turn layered controls into one usable number

Purchasing power starts from the customer's cash and eligible securities, then applies four layers of capacity and policy.

<div class="migration-grid">
  <article><span>01 · Source</span><h3>Lending pool</h3><p>Available capacity and the terms attached to the funding source.</p></article>
  <article><span>02 · Market</span><h3>Stock capacity</h3><p>Financing available for an eligible security.</p></article>
  <article><span>03 · Segment</span><h3>Customer group</h3><p>Allocation and lending policy for the segment.</p></article>
  <article><span>04 · Customer</span><h3>Individual limit</h3><p>Available capacity after all relevant limits are applied.</p></article>
</div>

The goal was to keep the controls explicit for business teams while exposing one reliable figure to the customer.

## Risk - intervene progressively before forced liquidation

The product moved through monitoring, warning and recovery as collateral value changed relative to debt.

<div class="feature-grid">
  <article><h3>Monitor</h3><p>Recalculate the account's margin position as values change.</p></article>
  <article><h3>Notify</h3><p>Tell the customer when action is required and what they can do next.</p></article>
  <article><h3>Restore</h3><p>Apply forced liquidation only when the account remains outside required conditions.</p></article>
</div>

Two decisions shaped forced liquidation:

- **Sell only what is needed to restore the required position.**
- **Prioritise more liquid assets** to improve execution reliability.

## Repayment - keep cash movement and loan state consistent

Repayment crossed loan management, money movement and the core system.

<ol class="journey journey-five">
  <li><span>01</span><strong>Request</strong><small>Customer submits a repayment</small></li>
  <li><span>02</span><strong>Deduct</strong><small>Request the cash movement</small></li>
  <li><span>03</span><strong>Confirm</strong><small>Confirm the deduction in the core system</small></li>
  <li><span>04</span><strong>Apply</strong><small>Update the loan after confirmation</small></li>
  <li><span>05</span><strong>Notify</strong><small>Show the customer the result</small></li>
</ol>

**The loan was reduced only after the cash deduction was confirmed.** This kept loan balance, account balance and repayment status aligned.

Payments were allocated to fees and penalties first, then interest, then principal.

## Cross-team integration

Margin lending depended on services owned by other teams, so each integration was defined around the customer journey and its confirmation points.

| Connected capability | What the margin journey needed |
|---|---|
| Account registration | Open a margin account for an eligible customer. |
| Balance information | Read cash and asset balances for purchasing power. |
| Money movement | Deduct cash for repayment and confirm it in the core system. |

My team owned the margin-specific decisions built on those services: purchasing power, loan servicing and risk actions.

## Migration and seven-team delivery

Approximately 900,000 customers moved to the new platform in a single cutover, with correct loan information and essential journeys available from the first trading session.

<div class="delivery-grid">
  <article><h3>Market-aware cutover</h3><p>Transition outside trading hours with a weekend verification window.</p></article>
  <article><h3>Rollback readiness</h3><p>Prepare rollback in advance. It was not required.</p></article>
  <article><h3>Shared product model</h3><p>Align seven teams around common capability, policy and loan-state definitions.</p></article>
  <article><h3>Journey-led planning</h3><p>Validate dependencies through complete customer journeys.</p></article>
</div>

---

## Outcomes and lessons

In seven months, the programme redesigned the margin lending domain and migrated approximately 900,000 customers across seven teams in one cutover, without rollback.

Three principles stood out:

1. **Start with the product model.** Clear boundaries make a complex financial platform easier to change.
2. **Make financial logic explainable.** Users should understand both the result and the reason behind it.
3. **Treat migration as a product outcome.** Success means customers keep correct information and working journeys through the transition.

<div class="confidentiality">
  This case study is based on my margin-system product requirements and project experience. The English mockups use demonstration customer, loan and pricing data. Product descriptions are generalised. Company-specific thresholds, pricing values, allocation formulas, proprietary decision rules, internal architecture, detailed migration procedures and customer information are omitted.
</div>
