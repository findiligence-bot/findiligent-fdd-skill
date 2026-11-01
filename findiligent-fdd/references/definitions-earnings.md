# FinDiligent Repository — Earnings Definitions

Version 1.0 · 1 Nov 2026 · Author: CA Ayush Bansal

The earnings vocabulary every pattern and consuming project uses: one definition per term, with formula, inputs, book reference and a worked example from the book's own figures. It applies the Phase 2 corrections and the house decisions D16–D25 and D36. INR million throughout.

## Conventions

Five rules apply to every definition below.

1. **Units.** INR million; original reported amounts and units are preserved alongside.
2. **Periods.** Fiscal label plus calendar months, e.g. "Q3 FY26 (Oct–Dec 2025)"; Indian fiscal years run April to March.
3. **Origin labels.** **[Book]** with page · **[GAAP]** generally accepted principle · **[Claude]** proposed here. A **[Book, corrected]** tag marks a Phase 2 correction.
4. **Statements basis.** Consolidated by default (D13); standalone where only standalone is published, labelled.
5. **Indicative, not foolproof (D36).** Every adjustment is a starting hypothesis to test against evidence, never a definitive figure. An adjustment whose amount has no evidence is shown as "NQ" with the evidence needed; it is never estimated. Where a component of a metric cannot be separated, the metric is still computed without it and labelled with what it excludes (E2).

## E1 — Revenue and growth

Revenue means Schedule III "Revenue from operations", net of GST; every growth figure must name its basis, because the book's "approximately 20%" (p.19) is a CAGR, not total growth.

| Term | Definition | Origin |
| --- | --- | --- |
| Revenue | Revenue from operations, including other operating revenue; excludes other income and GST | [GAAP]; book p.19 |
| YoY growth | Change on the prior year, same period length | [Book] p.19 |
| CAGR | Compound annual growth over n years | [Book] p.19 |
| Cumulative growth | Total change from start to end of the window | [Book, corrected] p.19 (A4) |
| LTM revenue | Last four reported quarters summed; labelled with the quarter it ends on | [Claude] (F3) |

```latex
\text{YoY}_t = \frac{R_t}{R_{t-1}} - 1 \qquad \text{CAGR} = \left(\frac{R_{end}}{R_{start}}\right)^{1/n} - 1 \qquad \text{Cumulative} = \frac{R_{end}}{R_{start}} - 1
```

**Worked example (book p.19):** revenue 700 / 870 / 1,000 for FY24–FY26. YoY 24.3% (FY25) and 14.9% (FY26); CAGR 19.5%; cumulative 42.9%. A consuming project that reports "revenue grew 20%" without a basis is ambiguous by a factor of two.

**Edge cases.** Acquisitions in the window: show reported and like-for-like growth separately, with the acquired contribution named. Restated prior years: use the restated figure and note the restatement. A fiscal-year change: annualise only with an explicit flag.

## E2 — Material margin and gross margin

Two margins are kept: material margin, comparable across every company, and sector gross margin, which also deducts the direct costs that deliver revenue in each sector — doctor cost in healthcare, packaging in consumer.

| Term | Definition | Origin |
| --- | --- | --- |
| Material cost | Cost of materials consumed + purchases of stock-in-trade + changes in inventories of finished goods, WIP and stock-in-trade | [GAAP] Schedule III lines |
| Material margin | Revenue − material cost; the cross-sector comparable | [Book, corrected] pp.19, 27 (D1) |
| Sector direct costs | Costs, other than materials, that directly deliver or scale with revenue in a sector (table below) | [Book] p.44 for doctors; author's sector guidance |
| Sector gross margin | Revenue − material cost − sector direct costs | [Book] + author's sector guidance |

| Sector | Above gross margin, besides materials | Where it sits in Indian filings | Status |
| --- | --- | --- | --- |
| Healthcare (hospitals, IVF, diagnostics) | Doctor cost: retainers, minimum guarantees, revenue share (p.44); salaried and consultant doctors both | Professional or consultancy fees in other expenses; salaried doctors in employee cost; split from notes or MIS | Confirmed by author |
| Consumer | Packaging and packing materials | Inside materials consumed, or as packing material in other expenses | Confirmed by author |
| Manufacturing | Power and fuel; job-work and subcontracting; direct plant labour; freight inward | Power and fuel and job-work in other expenses; plant wages inside employee cost (notes or segment data); freight inward often already capitalised into materials consumed — check before deducting | Confirmed by author |
| Retail / QSR | Packaging | Inside materials consumed, or as packing material in other expenses | Confirmed by author |
| Services, IT, education | Cost of service: employee cost | Employee benefits expense line in the P&L | Confirmed by author |

```latex
\text{Material margin} = R - (\text{materials consumed} + \text{stock-in-trade purchases} + \Delta\text{inventories})
```

```latex
\text{Sector gross margin} = R - \text{material cost} - \text{sector direct costs}
```

**Worked example (book p.19):** material margin 320 / 420 / 400; as % of revenue 45.7% / 48.3% / 40.0%. The FY26 fall of 830 bps on FY25 is the main driver of the book's margin decline (E4).

**Worked example — healthcare (hypothetical).** Hospital revenue 1,000; consumables 220; doctor cost 250. Material margin is 78.0%; sector gross margin is 53.0%. The 25-point gap is the cost a buyer or lender must underwrite for each rupee of revenue, which material margin alone hides.

**Edge cases.** Doctor cost split between employee cost and professional fees must be summed from the notes; any part that cannot be identified stays below gross margin. Packaging already inside materials consumed is not deducted twice. Sector gross margins are compared only within the same sector definition. Where a sector direct cost (doctor cost, plant labour, packaging) cannot be separated, gross margin is still computed with that cost left below it, and the margin is labelled with what it excludes, e.g. "gross margin, excluding plant labour (not separable)". Outside services, IT and education, total employee cost is never deducted as a proxy for plant labour or doctor cost.

## E3 — EBITDA

Four EBITDA figures are stored side by side, never merged; the pre-Ind AS 116 house figure is the default for leverage and valuation ratios (D18), and printed and house figures are both kept (D21).

| Term | Definition | Use | Origin |
| --- | --- | --- | --- |
| Printed EBITDA | The company's own EBITDA as shown in results or presentations, with its stated definition recorded | Reference; never recomputed | [Claude] (D21) |
| House EBITDA (post-Ind AS 116) | Built from Schedule III lines with the house exclusions below | Comparability across companies | [Claude] (D17) |
| House EBITDA (pre-Ind AS 116) | Post-116 house EBITDA − cash lease payments | Default for leverage and valuation | [Book] pp.14–15; [Claude] (D18) |
| Management adjusted EBITDA | Management's own adjusted figure, as layer 1b of the bridge, each adjustment tested | Tested, never accepted as given | [Book] p.74 (D22) |

```latex
\text{House EBITDA}_{post116} = \text{PBT before exceptional items} + \text{finance costs} + \text{D\&A} - \text{other income} + \text{unrealised FX loss on borrowings} + \text{ESOP cost}
```

```latex
\text{House EBITDA}_{pre116} = \text{House EBITDA}_{post116} - (\text{principal} + \text{interest paid on lease liabilities})
```

**House exclusions (D17).** Other income; unrealised forex on borrowings ([Book] p.38), where it sits in other expenses; ESOP cost, shown as a separate line; exceptional items as the company labels them, sitting below the starting line by construction. **Safeguard:** if the same exceptional category appears in two of three years, it is flagged as recurring and shown as a candidate to bring back into EBITDA ([Book] p.37 logic on recurring fines and write-downs).

**Worked example (book p.19):** PBT 44 / 57 / 26 + finance costs 5 / 8 / 9 + D&A 6 / 9 / 9 − other income 5 / 9 / 10 = house EBITDA 50 / 65 / 34, matching the book's EBITDA (no ESOP, FX or exceptional items in the example). Margin 7.1% / 7.5% / 3.4%.

**Worked example (book p.14):** post-116 EBITDA 100; cash lease payments 10; pre-116 house EBITDA 90.

**Lease data.** Cash lease payments come from the cash flow statement (principal and interest on lease liabilities). Short-term, low-value and variable lease costs are already in other expenses and must not be deducted again. Where the cash flow statement does not show lease payments, pre-116 house EBITDA is "NQ" and every ratio falls back to the post-116 basis: post-116 EBITDA paired with the disclosed lease liabilities inside net debt, labelled "lease payments not disclosed".

**Pairing rule.** Pre-116 EBITDA pairs only with net debt excluding lease liabilities; post-116 EBITDA pairs only with net debt including them (Phase 2, area 3). A ratio that mixes them is invalid.

## E4 — Margin walk

A margin walk explains a margin change as the sum of each cost line's change in share of revenue; the steps must add up exactly to the total, or the walk is invalid ([Book] p.19).

```latex
\Delta \text{EBITDA margin} = -\sum_i \Delta\left(\frac{\text{Cost}_i}{R}\right) \quad \text{(in bps; one term per cost line)}
```

| Cost line | Change in share of revenue, FY24→FY26 | Effect on EBITDA margin (bps) |
| --- | --- | --- |
| Materials | Up | −571 |
| Employee cost | Down | +151 |
| Legal and professional | Up | −64 |
| Other expenses | Down | +94 |
| Corporate costs | Down | +16 |
| **Total** |  | **−374** |

On the book's figures, the 374 bps fall in EBITDA margin breaks down as materials −571, employees +151, legal and professional −64, other expenses +94 and corporate +16. The book reports the centre-level walk as −390 bps with legal at −60 using rounded percentages; computed from the rupee figures it is −64.

**Edge cases.** Walk on the same EBITDA definition at both ends (E3). When revenue changes mix or includes an acquisition, a walk explains the arithmetic, not the cause; causes come from the pattern library.

## E5 — Five-layer earnings bridge

Adjusted earnings are built from house EBITDA through five cumulative adjustment layers (1b to 5), management's first, then strongest to weakest evidence, with EBITDA reported after each; the book's three layers (p.74) are kept, with its middle and pro-forma layers split (Phase 2, N4). Every adjustment is indicative, not foolproof (D36).

| Layer | Name | Test for inclusion | Typical items (book pages) | Evidence strength |
| --- | --- | --- | --- | --- |
| 0 | House EBITDA | E3 definition applied to reported statements | — | Source |
| 1b | Management adjustments | Management's own add-backs, each tested for rationale, evidence and recurrence | Items in results presentations (p.74) | Varies; tested |
| 2 | Ind AS corrections | Would correct Ind AS treatment give a different number? | Under-accruals (p.76); cut-off (p.76); capitalised R&M or AMC (pp.7, 62); unearned revenue (pp.6, 52); rebate under-accrual (p.56); provisioning shortfalls (p.76); inventory overhead absorption (p.64) | Strongest |
| 3 | Normalisations | Correctly stated but non-recurring, non-operating or not at arm's length | One-off legal and deal costs (pp.11, 36); prior-period items (p.39); discontinued operations (p.76); promoter personal expenses (p.38); non-arm's-length related-party pay (p.29) | Medium; needs recurrence evidence |
| 4 | Executed pro-forma | Action already taken, annualised as if in place all year | Signed new rent (p.42); completed severance savings (p.46); vacancy filled (p.30) | Medium-weak; needs post-event cost data |
| 5 | Prospective pro-forma | Expected event not yet executed | Expected wage settlement (p.30); AMC after warranty expiry (p.7); restoring suppressed R&M to a normal run-rate (p.40); GST rate effect where input tax is a cost (p.77); post-deal promoter pay (p.77) | Weakest; assumption-driven |

**Reporting rule.** Store EBITDA after layers 0, 1b, 2, 3, 4 and 5 separately. Consuming projects choose which layer they rely on and say so; credit uses commonly stop at layer 3 or 4.

**Quantum rule.** An item without evidence is "NQ" with the evidence needed listed (D24), not estimated.

**Recurrence rule.** An item claimed as one-off that appears in two of three years moves from layer 3 back into the base (Phase 1, Concept 1).

## E6 — Revenue adjustments and attached variable costs

No revenue adjustment reaches EBITDA in full by default: the variable costs attached to the adjusted revenue (revenue-share payouts, commissions, royalties, consumables, freight) are adjusted alongside it for a like-for-like comparison, and those attached costs are analysed case by case.

```latex
\Delta\text{EBITDA} = \Delta\text{Revenue} - \Delta\text{Attached variable costs}
```

| Revenue adjustment | Attached variable costs to test | Book example | Origin |
| --- | --- | --- | --- |
| Under-accrued rebates, schemes, discounts | Distributor commissions or incentives computed on net sales; sales-linked royalties | p.56: rebates 120 actual vs 50 accrued | [Book, corrected] |
| Insurer / TPA disallowances | Doctor revenue share where computed on billed or collected revenue | p.53 | [Book, corrected] |
| Price concessions reclassified from opex to revenue | None: EBITDA unchanged, revenue and margins restated | p.53 provision in other expenses | [Book, corrected] (B4) |
| Sales returns | Cost of returned goods if resaleable; freight; commission reversal; write-down if not resaleable | p.56: returns 10 → 30 | [Book, corrected] (A11) |
| Revenue timing (packages, multi-year fees) | Costs to fulfil that move with the deferred revenue, e.g. doctor share and consumables on packages; applied to the change in the unearned balance, not the closing balance | pp.6, 52 | [Book, corrected] (N2) |
| Unbilled revenue reversal | Variable costs accrued on the accrued revenue, e.g. doctor share; costs of care already delivered stay | p.54 | [Book, corrected] |
| Discontinued operations | All direct and variable costs of the line; allocated overheads stay as stranded cost | p.76 | [Book] |

**Worked examples (hypothetical).** *Rebates:* an under-accrual of 70 with a 2% distributor commission on net sales lowers commission by 1.4, so EBITDA falls by 68.6, not 70. *Disallowances:* 100 disallowed where doctors earn 30% of collections lowers doctor cost by 30, so EBITDA falls by 70. *Timing:* unearned package revenue rises from 25 to 30, so revenue falls by 5; with a 30% doctor share deferred alongside, EBITDA falls by 3.5. Deducting the full closing balance of 30 instead would overstate the revenue adjustment sixfold.

**Worked example — returns (hypothetical).** Returns rise by 20 at revenue value. With a 40% contribution margin and goods fully resaleable, EBITDA falls by 8, not 20; if half the goods must be written off at a cost of 6, EBITDA falls by 14.

## Validation rules

Nine checks guard every earnings figure a consuming project draws from this repository; each traces to an error found in the book or a Phase 2 convention.

| # | Check | Fails when | Traces to |
| --- | --- | --- | --- |
| V1 | Casting | A schedule's lines do not sum to its total | A8 (p.37) |
| V2 | Narrative vs table | A figure in text differs from its table | A1, A2 (pp.10–11) |
| V3 | Growth basis stated | A growth figure has no YoY / CAGR / cumulative label | A4 (p.19) |
| V4 | Ratio named by numerator and denominator | A ratio's label does not match its computation | A5 (p.27) |
| V5 | Margin walk closes | Steps do not sum to the margin change | E4 |
| V6 | Lease pairing | A ratio mixes pre- and post-Ind AS 116 bases | E3 |
| V7 | Revenue–EBITDA reconciliation | A revenue adjustment has no documented analysis of its attached variable costs | E6 |
| V8 | Recurring one-off | A one-off category appears in two of three years | E3, E5 |
| V9 | Tax rate outlier | Effective tax rate moves more than 10 pp year on year without explanation | F6 (p.19: 27% / 26% / 69%) |

Rounding: compute from unrounded inputs and round only for display; a difference within ±0.5 pp or ±1 unit is a rounding note, not an error (A6).

## Sources

- *Financial Due Diligence: Reading Between the Financial Lines*, CA Ayush Bansal, First Edition 2026 (project file): pp.6–7, 10–11, 14–15, 19, 27, 29–30, 36–39, 42, 46, 52–56, 62, 64, 74–77.
- FDD Book Audit — Critical Reconciliation (FinDiligent project file; not bundled): register IDs A1–A8, B4, D1, F6, N2, N4 and focus areas 2, 3, 7, 9.
- FinDiligent Engine — Design Decisions (FinDiligent project file; not bundled): D13, D16–D25, D36.
