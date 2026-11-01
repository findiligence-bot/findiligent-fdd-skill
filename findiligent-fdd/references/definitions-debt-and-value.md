# FinDiligent Repository — Debt and Value Definitions

Version 1.0 · 1 Nov 2026 · Author: CA Ayush Bansal

The vocabulary for net debt, debt-like items and the bridge from enterprise value to equity value. It follows the conventions of the Earnings and Working Capital definitions (units, periods, origin labels, indicative-not-foolproof). INR million throughout.

## V1 — Net debt structure

Net debt is measured at a single date and has three parts: financial debt, debt-like items and cash-like items. Each balance belongs to exactly one part, under the same mapping as the Working Capital doc (W1) ([Book] pp.11, 78).

```latex
\text{Net debt} = \text{Financial debt} + \text{Debt-like items} - \text{Cash-like items}
```

| Part | Contents | Book reference |
| --- | --- | --- |
| Financial debt — third party | Term loans, cash credit and overdrafts, NCDs and bonds, ECBs, other bank borrowings, accrued interest on borrowings | [Book] pp.70, 79 |
| Financial debt — promoter and related party | All promoter, director and group loans, interest-bearing or not, shown on a separate line | [Book] pp.7, 70; author decision |
| Debt-like items | Obligations not presented as borrowings but settled in cash for the seller's period (V3) | [Book] pp.78–80 |
| Cash-like items | Freely available cash and qualifying liquid investments (V2) | [Book] pp.71, 78 |
| Lease liabilities | In net debt only on the post-Ind AS 116 basis (V4) | [Book] pp.14–15, 81 |

**Point in time.** Net debt is a balance at one date, unlike earnings, which are measured over a period ([Book] p.78). Year-end cash can be window-dressed; where half-year balances exist, a consuming project should compare September and March net debt (Working Capital doc, W3) before relying on the year-end figure.

**Worked example (book p.68).** Bank borrowings 100 plus a reverse-factoring facility of 50 held in trade payables: net debt is 150 on the book's (and repository's) treatment, not 100.

## V2 — Cash and cash-like items

Only cash that is freely available to the business reduces net debt. Restricted cash is excluded unless it is tied to a debt already counted ([Book] pp.22, 71, 79).

| Item | Treatment | Origin |
| --- | --- | --- |
| Cash and cash equivalents (Ind AS 7) | Cash-like | [GAAP]; [Book] p.78 |
| Bank deposits over 3 months, not lien-marked | Cash-like | author decision |
| Liquid and debt mutual funds (current investments) | Cash-like | author decision |
| Listed equity and other investments | Excluded from net debt; in the market EV bridge as investments (V5) | author decision |
| Lien-marked deposits and margin money for guarantees or letters of credit | Excluded (restricted) | [Book] pp.22, 79 |
| Debt service reserve (DSRA) or other cash pledged to a borrowing already in net debt | Kept in cash: excluding it while counting the debt penalises twice | [Book] p.71 |
| Loans, advances and deposits given to promoters, group companies or related parties | Outside net debt (neither cash-like nor debt-like); highlighted separately as a related-party exposure and stated explicitly | [Book] p.71 |
| Overseas cash subject to capital or dividend restrictions | Excluded where it cannot be upstreamed; flagged | [Book] p.71 |
| Accrued interest on deposits | Cash-like | [Book] p.79 |

**Rule for restricted cash ([Book, consolidated] pp.71, 79):** exclude by default; keep in cash only where the restriction secures a liability that is itself inside net debt and is released when that liability is settled.

**Edge cases.** Unclaimed-dividend and similar earmarked bank accounts are excluded along with the matching liability. Mutual funds are taken at the reported fair value and labelled as such.

## V3 — Debt-like items and other matters

A debt-like item is an obligation, not presented as borrowing, that will be settled in cash for a period before the valuation date. Each is shown gross and tax-effected (D20) and is indicative, not foolproof (D36) ([Book] pp.78–80).

| Debt-like item | What is measured | Book reference |
| --- | --- | --- |
| Employee compliance arrears | Accumulated unpaid PF, ESI, bonus, minimum wage, overtime | p.79 |
| Unfunded gratuity and leave | Obligation less plan assets, if a deficit | pp.34, 80 |
| Unpaid dividends | Declared, not yet paid | p.79 |
| Capital creditors | Payables for capex | p.79 |
| Redeemable preference shares | Principal plus accrued unpaid dividend | pp.79, 83 |
| Deferred maintenance capex | One-time backlog only; recurring maintenance capex belongs in valuation, not here | pp.13, 79 (Phase 2 area 4) |
| Stretched payables | Excess over normal contractual terms | p.80 |
| Net current tax | Provision for tax less advance tax | p.80 |
| Reverse factoring / supplier finance | Facility balance | pp.67–68 |
| Transaction-related costs | Unpaid deal fees; usually "NQ" at diligence stage | p.80 |
| Change-of-control and retention payments | Contractual amounts triggered by the deal | pp.9, 31 |
| Wage settlement arrears | Retrospective element of a pending settlement | p.30 |
| Probable tax and legal exposures | Estimated settlement amount | p.80 |
| Overdue statutory dues | Portion beyond statutory due dates | p.69 |

**Tax effect.** Items deductible only on payment (gratuity, bonus, leave, some wage arrears) are shown gross and net of the tax saving. Hypothetical: an unfunded gratuity deficit of 40 at a 25.17% rate is 29.9 net. Any statutory section cited for periods from 1 April 2026 must refer to the Income-tax Act, 2025 (Phase 2, R9).

**Other matters: listed, not in net debt.**

- **Contingent liabilities:** listed with amounts and nature from the notes; the consuming project judges probability ([Book] p.81; author decision).
- **Growth capex commitments:** disclosed for negotiation, not debt-like ([Book] p.81).
- **Lease liabilities:** in net debt only on the post-Ind AS 116 basis (V4).
- **Low-impact tax matters:** listed ([Book] p.78).

## V4 — Lease bases and the pairing rule

Leases are counted once: either through rent deducted above EBITDA, or through the lease liability in net debt, never both ([Book] p.15). The pre-Ind AS 116 basis is the default for leverage and valuation (D18).

| Basis | EBITDA used | Net debt | Default use |
| --- | --- | --- | --- |
| Pre-Ind AS 116 (default) | House EBITDA after cash lease payments | Excludes lease liabilities | Leverage, valuation, comparisons with I-GAAP-style metrics |
| Post-Ind AS 116 | House EBITDA as reported | Includes lease liabilities | Comparisons with companies and multiples quoted on this basis |

**Pairing rule.** A ratio or valuation built from one basis's EBITDA must use the same basis's net debt and a multiple drawn from comparables on that basis. Mixing them is invalid. Cash lease payments are taken from the cash flow statement; where it does not show them, pre-116 figures are "NQ" and the post-116 basis is used, with disclosed lease liabilities in net debt, labelled "lease payments not disclosed".

**Why the multiple matters.** Using the same multiple on both bases gives equal equity value only if the lease liability happens to equal the multiple times annual rent. Hypothetical: rent of 10 with 5 years left at 9% gives a lease liability of 38.9; at the same 22x, equity on the post-116 basis is 10.8% higher than pre-116. The consistent post-116 multiple in that case is about 20.2x, not 22x (Phase 2, area 3).

**Lease-term check.** Where leases are near expiry, the reported liability understates the ongoing obligation; a consuming project should flag it rather than rely on the short liability ([Book] p.81).

## V5 — Enterprise value to equity value

There are two bridges, run in opposite directions. The transaction bridge starts from earnings and arrives at equity; the market bridge starts from market capitalisation and arrives at enterprise value. Both must use the same net debt and lease basis.

### Transaction bridge

```latex
\text{EV} = \text{Adjusted EBITDA} \times \text{Multiple} \qquad \text{Equity value} = \text{EV} - \text{Net debt} \pm (\text{Closing NWC} - \text{NWC peg})
```

| Step | Book p.10 example (INR m) |
| --- | --- |
| Adjusted EBITDA | 110 |
| × Multiple | 22x |
| Enterprise value | 2,420 |
| − Net debt | (500) |
| EV less net debt | 1,920 |
| ± NWC adjustment vs peg | (20) |
| Equity value | 1,900 |

The book's text reports 1,920 and its table 1,900; both are right for their stage, so the repository names the intermediate "EV less net debt" (Phase 2, A2).

### Market bridge (listed companies)

```latex
\text{EV} = \text{Market capitalisation} + \text{Net debt} + \text{Non-controlling interest} - \text{Investments in associates and JVs} - \text{Other non-operating investments}
```

Non-controlling interest is added because consolidated EBITDA includes 100% of subsidiaries' earnings; associates and other investments are subtracted because their earnings are not in EBITDA (author decision).

**Worked example (hypothetical).** Market capitalisation 5,000; net debt on the pre-Ind AS 116 basis 800; non-controlling interest 200; investments in associates 300. EV = 5,700; with pre-116 house EBITDA of 570, EV / EBITDA is 10.0x.

**Cheque-size principle.** Collecting receivables just before a sale leaves enterprise value unchanged but lowers net debt, so equity proceeds rise unless the NWC peg captures the working-capital shortfall it leaves behind ([Book] pp.12, 72). Repaying debt from existing cash changes neither.

## V6 — Leverage and coverage ratios

The book scopes credit diligence around debt-servicing capacity and leverage but does not define the ratios (p.18; Phase 2, F2). These definitions were proposed by Claude and reviewed by the author on 1 Nov 2026; DSCR follows the Indian bank convention. EBITDA-based ratios use the pre-Ind AS 116 basis by default.

| Ratio | Formula | Reads as |
| --- | --- | --- |
| Net leverage | Net debt ÷ house EBITDA | Years of EBITDA to repay net debt |
| Gross leverage | Financial debt ÷ house EBITDA | Leverage before cash, which may be trapped or spent |
| Interest cover | House EBITDA ÷ finance costs (excluding lease interest on the pre-116 basis) | Margin of safety on interest |
| DSCR | (PAT + depreciation + interest on term debt) ÷ (interest on term debt + principal instalments due in the next 12 months) | Cash accruals available to meet term-debt service (Indian bank convention) |
| Debt to equity | Financial debt ÷ total equity | Funding mix |

```latex
\text{DSCR} = \frac{\text{PAT} + \text{depreciation} + \text{interest on term debt}}{\text{interest on term debt} + \text{principal instalments due within 12 months}}
```

**Worked example (book pp.19, 21).** Net debt 35 / 63 / 69 against EBITDA 50 / 65 / 34 gives net leverage of 0.7x / 1.0x / 2.0x; interest cover falls from 10.0x to 8.1x to 3.8x. Leverage nearly tripled in two years because two moves compounded: net debt doubled while EBITDA fell by about a third.

**Edge cases.** Promoter loans repayable on demand count as due within 12 months for DSCR ([Book] p.7). Principal falling due comes from the borrowings maturity note or, failing that, from current maturities of long-term borrowings on the balance sheet, labelled as such; revolving working-capital lines are excluded. Where neither is available, DSCR is not computed and not shown. Interest on term debt excludes interest on revolving working-capital lines; where finance costs are not split, total finance costs are used and labelled. PAT, depreciation and interest are taken as reported, with any one-off items stated alongside.

## Validation rules

Six checks guard every debt and value figure a consuming project draws from the repository.

| # | Check | Fails when | Traces to |
| --- | --- | --- | --- |
| DV1 | Single home | A balance sits in net debt and in NWC, or in both debt and cash | V1; Working Capital WV1 |
| DV2 | Lease pairing | EBITDA, net debt and multiple are not all on the same lease basis | V4 |
| DV3 | Restricted cash | Restricted cash is counted as cash without a linked liability inside net debt | V2 |
| DV4 | Backlog vs recurring | A recurring maintenance capex need is counted as a debt-like item | V3; Phase 2 area 4 |
| DV5 | Bridge naming | "Equity value" is shown without stating whether the NWC adjustment is applied | V5; Phase 2 A2 |
| DV6 | Promoter debt | Promoter or related-party loans are netted, omitted or merged with third-party debt | V1 |

## Sources

- *Financial Due Diligence: Reading Between the Financial Lines*, CA Ayush Bansal, First Edition 2026 (project file): pp.7, 9–15, 18–22, 30–31, 34, 67–72, 78–83.
- FDD Book Audit — Critical Reconciliation (FinDiligent project file; not bundled): A2, E1, E4, E7, F2, R7–R9, focus areas 3, 4 and 8.
- FinDiligent Engine — Design Decisions (FinDiligent project file; not bundled): D18, D20, D36; debt and value choices made on 1 Nov 2026 (cash-like scope, contingent liabilities, market EV bridge, promoter debt).
