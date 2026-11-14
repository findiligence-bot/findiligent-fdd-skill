# FinDiligent Repository — Company Research Carousel (consuming-project guide)

Version 1.2 · 14 Nov 2026 · Author: CA Ayush Bansal

How a consuming project turns this repository's definitions and patterns into a published company carousel (Instagram, 1080 × 1350,
Ledger design). Settled in the author's review of the Ather Energy Q2 FY27 carousel (12–14 Nov 2026; decisions D38–D44). The repository
still produces no output itself (D31): this file travels with the skill as guidance for the project that does. Every figure stays
indicative, not foolproof (D36).

## C1 — Presentation rules

| # | Rule | Origin |
| --- | --- | --- |
| C1.1 | EBITDA always excludes other income and is shown **once**: never an "including other income" figure, an asterisk variant or a second EBITDA in a footnote | [Author] D42 |
| C1.2 | House EBITDA (E3) adds back the ESOP cost; liability or provision no longer required written back stays inside EBITDA as other operating income | [Author] D17, D38 |
| C1.3 | Net debt follows V1–V4; lien-marked deposits and deposits with lenders are treated as cash where the split between guarantee and borrowing security is not disclosed, with a small-font footnote; payables past their due date are debt-like | [Author] D39, D40 |
| C1.4 | Use "~" for indicative figures, and always when describing DSO, DPO or DIO days in general prose ("dealers pay in ~2 days, suppliers in ~83"). Exact filed figures stay exact | [Author] D43 |
| C1.5 | Check the accounting before calling anything a finding: costs capitalised in line with Ind AS (directly attributable development or plant cost under Ind AS 38, 16, 23) are not findings and get no "if expensed" figure. Ageing of CWIP or intangibles under development is not commented on; project-wise detail is not needed | [Author] D41 |
| C1.6 | The cover carries a provocative, thought-provoking hook that is not built on other income and not negative for its own sake. Cover and quarter commentary stop at EBITDA: no depreciation, finance cost, other income or PAT | [Author] D44 |
| C1.7 | Explain the business as if the reader does not know the industry: who pays whom, how revenue is earned, unit economics per unit | [Author] D44 |
| C1.8 | Add an "Insight" call-out wherever a number has a reading (for example, dispatches against registrations as the channel-stuffing test, RQ05; a falling subsidy share) | [Author] D44 |
| C1.9 | Plain language: any phrase that needs explaining ("growth releases cash", "a gain 3.6 times its size") is rewritten on the slide in plain words | [Author] D44 |
| C1.10 | Sources name only documents: annual reports, quarterly results, investor presentation, earnings calls, newspaper report. Never a code repository, a data pipeline or an AI tool | [Author] D44 |
| C1.11 | Amounts in INR million (per-unit figures in INR per unit). Where a project's own spreadsheet is labelled "million" but holds crore, convert ×10 and say so | [Author] |
| C1.12 | No buy, sell or hold view, price target or share-price commentary; the disclaimer goes on the last slide | [Author] (Out of scope) |
| C1.13 | Every slide number has a backup the author can tie to their own workings: a per-slide backup file with note references and balance-sheet ties | [Author] |

## C2 — Twelve-slide template

| # | Slide | Must contain |
| --- | --- | --- |
| 01 | Cover | Hook (C1.6); one-line company brief; quarter commentary to EBITDA; three headline numbers (units or volume, revenue growth, EBITDA) |
| 02 | How the industry works | The value chain top to bottom (suppliers → company → channel → customer) with when money moves (~days); subsidy and after-sale income; one insight |
| 03 | How the company makes money | Five steps (design, make, sell, earn, collect), one or two lines each; an Insight box; a per-unit takeaway |
| 04 | Unit economics | Two-period table per unit: revenue → material cost → material margin → employee → other expenses → EBITDA → D&A → finance cost → other income → PBT, tied to reported PBT |
| 05 | Revenue | Growth split into volume × price (YoY, basis stated, E1); revenue per unit as bars with **units as a line on the same chart**; two or three insight bullets |
| 06 | Margin walk | House EBITDA margin walk (E4), two decimals, closing to zero; sub-lines listed |
| 07 | Margin quality | Management-stated temporary items quantified; hypotheses graded, benign first (D08, D37); plain takeaway ("without X, EBITDA would be Y") |
| 08 | Lender and investor lens | Interest cover, DSCR (V6), net cash and years of burn, working-capital trend (~days); operating leverage, price and volume, debt to equity |
| 09 | Net debt walk | Opening net debt → CFO → capex → equity → net interest → lease payments → debt-like and other → closing; definition note; lien footnote (C1.3). "Other" stays small: a large balancing bar means a missing line |
| 10 | Cash bridge | From house EBITDA: non-cash items → before working capital → working-capital lines → CFO → capex → free cash flow; the latest half-year trend (W3) |
| 11 | Diligence insights | Four questions, each with its number, none of them compliant accounting (C1.5) |
| 12 | Closing | Five numbers to watch (latest value → what would confirm the turn); source line (C1.10); disclaimer |

## C3 — Workflow

1. Gather filings: two annual reports, quarterly results with half-year balance sheet and cash-flow statement, investor presentation, earnings-call transcripts.
2. Read the annual-report **notes**, not only the statements: borrowings, leases, other financial assets and bank balances (liens), provisions (warranty movement), trade-payables ageing and MSME dues, employee benefits (plan assets), other expenses, exceptional items, related parties, contingent liabilities and commitments, capitalisation transfers.
3. Compute house metrics deterministically from unrounded inputs (E3–E5, W2–W3, V1–V6, R1–R3); every walk closes.
4. Reconcile to the author's spreadsheet line by line (margin walk, cash-flow statement, net debt) and explain each difference.
5. Work the matched patterns, benign first, graded; list open questions (D24: NQ, never estimated).
6. Write the analysis file and the per-slide backup file.
7. Build, render and look at every slide; fix any overflow before publishing.

## C4 — Checks before publishing

| # | Check | Fails when |
| --- | --- | --- |
| CK1 | Walks close | The margin walk misses by more than rounding; the net-debt walk's "other" exceeds about 1% of its largest flow; unit economics does not tie to reported PBT |
| CK2 | One EBITDA | Any second EBITDA appears (C1.1) |
| CK3 | Sources | A source line names anything other than documents (C1.10) |
| CK4 | Indicative marks | A general days statement or an approximate figure lacks "~" (C1.4) |
| CK5 | Accounting | A compliant accounting treatment is presented as a finding, or CWIP or development ageing is commented on (C1.5) |
| CK6 | Cover | The cover hook rests on other income, or cover commentary goes below EBITDA (C1.6) |
| CK7 | Backup | A slide number has no traceable backup (C1.13) |
| CK8 | Layout | A slide overflows or a footnote collides with the footer |

## Sources

- Author review of the Ather Energy Q2 FY27 carousel, 12–14 Nov 2026 (versions 5 to 12), recorded as D38–D44 in `design-decisions.md`.
- Definition files E1–E6, W1–W5, V1–V6, R1–R3 and pattern libraries in this repository.
