# FinDiligent Repository — Returns and Cash Definitions

Version 1.0 · 1 Nov 2026 · Author: CA Ayush Bansal

The last of the four definition families: returns on capital, cash conversion and capital expenditure. It follows the conventions of the Earnings, Working Capital and Debt and Value definitions. INR million throughout.

## R1 — Return ratios

Four return ratios are kept, each with a fixed name, all on average capital (opening plus closing, halved) and on the same lease basis as the earnings figure (Phase 2, area 5).

| Ratio | Formula | Purpose | Origin |
| --- | --- | --- | --- |
| ROCE | EBIT ÷ average capital employed | Return after depreciation on the capital the business uses | [GAAP]; [Claude] (D3a) |
| Gross cash return | House EBITDA ÷ average (gross block excl. land + NWC) | The book's ROCE, renamed; compares old and new assets without the distortion of accumulated depreciation | [Book, corrected] p.62 |
| Asset turnover | Revenue ÷ average gross block excl. land | Revenue generated per rupee of fixed assets | [Claude] |
| ROE | PAT ÷ average total equity | Return to shareholders | [Book, corrected] p.60 ("Return on Earnings" typo, D3b) |

```latex
\text{Capital employed} = \text{Net fixed assets (PPE + intangibles, excl. CWIP)} + \text{NWC} \qquad \text{ROCE} = \frac{\text{EBIT}}{\tfrac{1}{2}(\text{CE}_{open} + \text{CE}_{close})}
```

**Lease pairing.** On the pre-Ind AS 116 basis, EBIT is after rent and capital employed excludes right-of-use assets; on the post-116 basis, EBIT is before rent and ROU assets are included in both capital employed and gross block.

**Exclusions.** CWIP is excluded because it produces no return yet; it is reported separately as capital awaiting deployment. Goodwill is shown in an inclusive and an exclusive variant. Land is excluded from gross block; where land cannot be separated from buildings, the ratio is computed with it and labelled "including land (not separable)", following the author's rule for gross margin.

**Worked example (book pp.19, 21; FY26).** EBIT = 34 − 9 = 25. Capital employed (net PPE and intangibles excluding CWIP, plus NWC) is 1,112 at Mar-25 and 1,130 at Mar-26, average 1,121, so ROCE is 2.2% (5.2% in FY25). Gross cash return, with land and building not separable: 34 ÷ (2,115 + 196) = 1.5% (2.9% in FY25). Asset turnover 1,000 ÷ 2,115 = 0.47x. ROE: PAT 8 ÷ average equity 1,059 = 0.8%. Returns roughly halved in one year while capital employed barely moved, so the decline is an earnings problem, not over-investment ([Book] p.62 correlation logic).

## R2 — Cash conversion

The headline measure is operating cash flow from the cash flow statement divided by house EBITDA, on the same lease basis. It answers the book's central question of whether reported earnings turn into cash ([Book] pp.12–13; author decision).

```latex
\text{Cash conversion} = \frac{\text{Net cash from operating activities}}{\text{House EBITDA}}
```

**What sits inside operating cash flow.** It is after income tax paid and after working-capital movements, so conversion below 100% is normal; the question is why and whether it is stable. Under Ind AS 7, Indian non-financial companies usually show interest paid in financing activities, and under Ind AS 116 lease principal and interest also sit in financing. The classification policy is read from the notes and recorded.

**Lease pairing.**

- Post-Ind AS 116 basis: reported operating cash flow ÷ post-116 house EBITDA.
- Pre-Ind AS 116 basis (default): (operating cash flow − cash lease payments shown in financing) ÷ pre-116 house EBITDA. Without this, rent leaves the denominator but not the numerator, and conversion is overstated. Where the cash flow statement does not show lease payments, use the post-116 basis, labelled.

**Worked example (hypothetical).** Operating cash flow 95; cash lease payments 10 in financing; post-116 EBITDA 110 and pre-116 EBITDA 100. Post-116 conversion is 86%; pre-116 conversion is (95 − 10) ÷ 100 = 85%. The two agree once rent is treated consistently; using 95 ÷ 100 = 95% would mix bases.

**Reading it.** Falling conversion with rising EBITDA is the book's "artificial lift" signal: EBITDA +20% while receivables +50% (p.13). The pattern library takes it from there, testing channel stuffing, extended credit and premature recognition. A single year can mislead; conversion is read over the three-year window and against the working-capital days in the Working Capital doc.

## R3 — Capex split and asset health

Capex is split only as far as the company's own disclosures allow; maintenance capex is never estimated (author decision), and any ratio that needs it is shown before maintenance capex, labelled.

| Component | Definition | Where it goes | Book reference |
| --- | --- | --- | --- |
| Recurring maintenance capex | Spend to keep existing assets at current capacity | Valuation, where disclosed | [Book] p.61 |
| Deferred maintenance backlog | Maintenance that was postponed and must be caught up | Net debt (debt-like) | [Book] pp.13, 79 |
| Growth capex | Spend for new capacity, capability or cost savings; can be deferred | Disclosed for negotiation | [Book] pp.61, 81 |
| Suppressed R&M (opex) | Repairs cut below a normal run-rate | Earnings layer 4 or 5 (pro-forma) | [Book] pp.40, 75 |

**When no split is disclosed.** Total capex is reported, with no maintenance figure. DSCR (Debt and Value doc, V6) follows the Indian bank convention and does not use maintenance capex.

**Asset health indicators.**

| Indicator | Formula | Signal | Book reference |
| --- | --- | --- | --- |
| Capex intensity | Capex ÷ revenue | Rising with flat revenue: failed project or long gestation | p.62 |
| Net / gross block by asset class | Net block ÷ gross block, excluding land | Low ratio with low R&M: under-investment | p.61 |
| R&M intensity | R&M ÷ gross block, excluding land | Low or falling: deferred maintenance or capitalised repairs | p.40 |
| Maintenance capex ÷ depreciation | Only where maintenance capex is disclosed | Below 1: assets consumed faster than replaced | p.62 |
| Intangible additions vs amortisation | Additions with no amortisation charge | Possible capitalised opex; or goodwill, which is not amortised | p.60; Phase 2 F7 |

**Worked example (book pp.40, 61).** R&M was 0.33% / 0.48% / 0.28% of gross block, but that gross block includes land and building of 960 that cannot be split. Labelled "including land and building (not separable)", the ratio understates true R&M intensity on maintainable assets; excluding all land and building, FY26 is 6 ÷ 1,171 = 0.51%.

## Validation rules

Five checks guard every return, cash and capex figure a consuming project draws from the repository.

| # | Check | Fails when | Traces to |
| --- | --- | --- | --- |
| RC1 | Ratio names | The book's EBITDA-on-gross-block ratio is labelled "ROCE" | R1; Phase 2 D3a |
| RC2 | Average capital | A return ratio uses a closing rather than average balance without saying so | R1 |
| RC3 | Lease pairing | Cash conversion or a return ratio mixes pre- and post-Ind AS 116 figures | R1, R2 |
| RC4 | No estimated maintenance capex | A maintenance figure appears that the company did not disclose | R3 |
| RC5 | Land label | A ratio on gross block includes land without the "not separable" label | R1, R3 |

## Sources

- *Financial Due Diligence: Reading Between the Financial Lines*, CA Ayush Bansal, First Edition 2026 (project file): pp.12–13, 19, 21, 40, 60–62, 75, 79, 81.
- FDD Book Audit — Critical Reconciliation (FinDiligent project file; not bundled): D3a, D3b, E1, F1, F7, N5, N7, focus areas 4 and 5.
- FinDiligent Engine — Design Decisions (FinDiligent project file; not bundled): D18, D36; returns and cash choices made on 1 Nov 2026 (OCF ÷ EBITDA headline, average capital employed, no maintenance capex estimate).
