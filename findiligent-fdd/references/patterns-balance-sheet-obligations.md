# FinDiligent Pattern Library — Balance-Sheet Obligations

Version 1.0 · 1 Nov 2026 · Author: CA Ayush Bansal

Twelve patterns on obligations a buyer or lender inherits that the headline balance sheet may not show as debt. They use the same nine fields as the Revenue Quality library and the vocabulary of the four definition docs, especially Debt and Value. Every hypothesis and effect is indicative, not foolproof.

## BS01 — Promoter loans repayable on demand

| Field | Content |
| --- | --- |
| Trigger | Significant borrowings from promoters, directors or group companies; loans repayable on demand; interest at or above market, or none |
| Competing hypotheses | (a) Patient, subordinated support that will stay in the business. (b) A liquidity risk: repayment can be demanded at any time (book: INR 20 crore at 9%, repayable on demand, p.7). (c) A route to extract cash through interest or repayment ahead of other creditors |
| Financial effects | Financial debt, always included and shown separately from third-party debt (V1); counts as due within 12 months for DSCR (V6) |
| Possible outcomes | Sudden repayment demand; refinancing need; related-party leakage |
| Evidence — public | Borrowings note split by lender; related-party transactions (loans, interest); maturity analysis |
| Evidence — diligence | Loan agreements: term, security, subordination, intended post-deal treatment (p.7) |
| Credit reading | Require subordination or conversion to equity; restrict repayment by covenant |
| Equity reading | Settle or convert at completion; price it as debt either way |
| Source | [Book] pp.7, 22, 70 |

## BS02 — Deal-triggered payouts

| Field | Content |
| --- | --- |
| Trigger | Change of control, a stake sale or a listing in prospect; senior management contracts with retention, loyalty, golden-parachute or severance terms |
| Competing hypotheses | (a) No transaction-linked terms. (b) Payouts triggered on change of control (book: loyalty bonuses on sale of a retail chain, p.9; INR 50 m to senior management, p.31) |
| Financial effects | Debt-like items reducing equity value (V3); not visible in the financial statements until triggered |
| Possible outcomes | Cash outflow at or after completion; management exits if payouts are not honoured |
| Evidence — public | Key managerial remuneration terms; ESOP schemes with accelerated vesting; related disclosures in offer documents |
| Evidence — diligence | Employment agreements of key staff (p.31) |
| Credit reading | Confirm acquisition or refinancing debt covers the payout |
| Equity reading | Deduct from price, rupee for rupee |
| Source | [Book] pp.9, 31 |

## BS03 — Debt hidden in operating lines

| Field | Content |
| --- | --- |
| Trigger | Trade payables, capital creditors or customer advances growing unusually; supplier-finance or channel-financing arrangements; vendor-financed capex |
| Competing hypotheses | (a) Ordinary trade credit on normal terms. (b) Reverse factoring sitting in payables (book: INR 50 m inside INR 120 m payables, p.68). (c) Capex funded by suppliers on deferred terms (p.79). (d) Advances from related parties presented as customer advances |
| Financial effects | Net debt understated; moving these to debt-like reduces equity value rupee for rupee (V3) and must leave the NWC peg too (W4) |
| Possible outcomes | Default on a financing bank rather than a supplier dispute (p.67); value leakage for a buyer |
| Evidence — public | Ind AS 7 supplier-finance disclosures; capital creditors; MSME dues; operating vs financing cash flow classification |
| Evidence — diligence | Financing agreements; payables ageing against terms; advance counterparties |
| Credit reading | Include in leverage and cross-default analysis |
| Equity reading | Deduct as debt; check the book's alternative view (only financing cost is debt-like, p.68) is not double counted |
| Source | [Book] pp.67–68, 79 |

## BS04 — Unfunded employee obligations

| Field | Content |
| --- | --- |
| Trigger | Large gratuity or leave obligations with small plan assets; employees transferring in a carve-out; the Labour Codes extending gratuity to fixed-term staff after one year |
| Competing hypotheses | (a) Fully funded plans with realistic assumptions. (b) An unfunded deficit (book: unfunded gratuity is debt-like, p.34). (c) Optimistic actuarial assumptions understating the obligation (p.69). (d) Transferred staff carrying accumulated benefits (book: \~280 staff in the Paytm–Zomato carve-out, p.16) |
| Financial effects | Deficit is debt-like, shown gross and tax-effected (V3); kept out of NWC because timing is uncertain (p.80) |
| Possible outcomes | Cash outflow as employees leave or retire; higher ongoing cost if assumptions are corrected |
| Evidence — public | Employee benefits note: obligation, plan assets, discount rate, salary escalation, attrition; headcount reconciliation |
| Evidence — diligence | Actuarial report reconciled to the books and to payroll headcount (p.31) |
| Credit reading | Treat the deficit as senior to equity in recovery analysis |
| Equity reading | Deduct from price; check assumptions against peers |
| Source | [Book] pp.16, 31, 34, 69, 80 |

## BS05 — Litigation and tax exposures

| Field | Content |
| --- | --- |
| Trigger | Contingent liabilities growing faster than the business; rising legal costs (CM08); tax demands or disputes in the news |
| Competing hypotheses | (a) Routine disputes with low probability of outflow. (b) Probable exposures not provided for (p.35). (c) Settlement already agreed but not recorded |
| Financial effects | Probable amounts are debt-like (V3); contingent liabilities are listed but not in net debt (author decision) |
| Possible outcomes | Settlement cash outflow; indemnity or escrow negotiation in a deal |
| Evidence — public | Contingent liabilities note over three years; provisions movement; auditor emphasis of matter; legal-cost trend |
| Evidence — diligence | Litigation schedule from legal diligence; tax diligence on probability and quantum (p.80) |
| Credit reading | Large contingencies can crystallise into cash claims ranking alongside lenders |
| Equity reading | Probable amounts reduce price; possible ones belong in indemnities or escrow (p.81) |
| Source | [Book] pp.35–36, 69, 80–81 |

## BS06 — Overdue statutory dues

| Field | Content |
| --- | --- |
| Trigger | TDS, GST, PF or ESI payable balances outstanding past due dates; auditor remarks on delayed deposits; interest on delayed statutory payments |
| Competing hypotheses | (a) Timing at the period end, paid within due dates. (b) The government used as a lender during liquidity stress. (c) Disputed amounts withheld |
| Financial effects | Overdue portion is debt-like (V3); interest and penalties add cost |
| Possible outcomes | Penalties, interest, recovery actions; a governance flag |
| Evidence — public | Auditor's report remarks on statutory dues; statutory liabilities note; interest on delayed payments |
| Evidence — diligence | Ageing of statutory dues against due dates; returns and challans (p.69) |
| Credit reading | A strong early sign of liquidity stress |
| Equity reading | Deduct overdue amounts and expected penalties |
| Source | [Book] p.69 |

## BS07 — Lease obligations

| Field | Content |
| --- | --- |
| Trigger | A lease-heavy model (stores, centres, aircraft, warehouses); many leases near expiry; foreign-currency leases; leases from promoters |
| Competing hypotheses | (a) Long, stable leases at market rent. (b) A short reported liability masking an ongoing need, because leases expire within two years (p.81). (c) Currency exposure raising cash rent (book: airline leases, p.41). (d) Promoter leases below market (CM10) |
| Financial effects | On the default pre-Ind AS 116 basis, cash rent is deducted from EBITDA; on the post-116 basis, the lease liability is in net debt (V4); never both |
| Possible outcomes | Rent escalation or relocation on renewal; FX-driven cost increases |
| Evidence — public | Lease liabilities maturity analysis; cash lease payments; short-term and variable lease costs; related-party leases |
| Evidence — diligence | Lease schedule: expiry, lock-in, escalation, lessor (p.41) |
| Credit reading | Lease payments rank like debt service in practice; include them in coverage tests on the pre-116 basis |
| Equity reading | Keep EBITDA, net debt and the multiple on one lease basis (V4 pairing rule) |
| Source | [Book] pp.14–15, 41, 81 |

## BS08 — Purchase commitments

| Field | Content |
| --- | --- |
| Trigger | Long-term supply contracts with minimum volumes or take-or-pay terms; demand weakening below committed volumes |
| Competing hypotheses | (a) Commitments comfortably below expected demand. (b) Shortfall penalties likely as demand falls (book: fixed raw-material volumes over three years, p.68) |
| Financial effects | Future cash outflow for unused volumes or penalties; may warrant a provision or a debt-like adjustment if probable |
| Possible outcomes | Penalty payments; excess inventory; renegotiation |
| Evidence — public | Commitments note; onerous contract provisions; volume trends against capacity |
| Evidence — diligence | Supply agreements: minimum volumes, penalty terms, remedies |
| Credit reading | Add probable shortfall payments to cash obligations |
| Equity reading | Seek valuation adjustment or indemnity where material (p.68) |
| Source | [Book] p.68 |

## BS09 — Acquisition-related obligations

| Field | Content |
| --- | --- |
| Trigger | Acquisition-led growth; large or rising goodwill; earn-outs or deferred consideration disclosed |
| Competing hypotheses | (a) Consideration fully paid, goodwill supported by performance. (b) Contingent or deferred consideration still payable (p.69). (c) Goodwill at risk of impairment where acquired units underperform |
| Financial effects | Unpaid deferred or contingent consideration is debt-like (V3); goodwill impairment hits reported profit and equity |
| Possible outcomes | Earn-out cash outflows; impairment charges |
| Evidence — public | Goodwill by acquisition; contingent consideration liabilities and their fair-value changes; impairment testing disclosures |
| Evidence — diligence | Acquisition agreements; recomputation of contingent consideration, probability and discounting (p.69) |
| Credit reading | Treat earn-outs as debt service competing for cash |
| Equity reading | Deduct; test acquired units' performance against the price paid |
| Source | [Book] pp.62, 69 |

## BS10 — Loan covenants, defaults and guarantees

| Field | Content |
| --- | --- |
| Trigger | Falling EBITDA against fixed leverage covenants; waivers obtained; loans reclassified as current; corporate guarantees or comfort letters for group companies |
| Competing hypotheses | (a) Ample headroom, clean history. (b) A breach or near-breach handled by waivers (p.70). (c) A change-of-control clause triggered by the deal (p.70). (d) Off-balance-sheet guarantees that could crystallise (p.70) |
| Financial effects | Debt may become repayable early; cross-default can spread across lenders; guarantees become debt if called |
| Possible outcomes | Accelerated repayment; refinancing at higher cost; liquidity crisis |
| Evidence — public | Borrowings note on breaches and reclassification; guarantees in contingent liabilities; credit rating actions; net leverage trend (V6) |
| Evidence — diligence | Financing agreements: covenants, waivers, change-of-control, cross-default, security (p.70) |
| Credit reading | Recompute covenant headroom on the lender's own EBITDA definition, not the company's |
| Equity reading | A change-of-control trigger can force refinancing at completion; price the cost |
| Source | [Book] pp.22, 70 |

## BS11 — Hybrid instruments in equity

| Field | Content |
| --- | --- |
| Trigger | Preference shares, compulsorily or optionally convertible instruments, or investor put rights presented within equity |
| Competing hypotheses | (a) Genuine equity with no fixed return. (b) Redeemable or fixed-return instruments with debt-like features (p.79). (c) Investor exit rights creating a future cash obligation |
| Financial effects | Redeemable preference shares and accrued unpaid dividends are debt-like (V3) even if classified in equity (p.83) |
| Possible outcomes | Redemption cash outflow; dilution on conversion |
| Evidence — public | Equity and other financial liabilities notes; terms of preference shares and convertibles; shareholder agreements in offer documents |
| Evidence — diligence | Full instrument terms: redemption, coupon, put and call rights |
| Credit reading | Treat redemption obligations as debt in leverage |
| Equity reading | Deduct redemption value; model dilution for convertibles |
| Source | [Book] pp.79, 83 |

## BS12 — Related-party advances and deposits

| Field | Content |
| --- | --- |
| Trigger | Loans, advances or security deposits given to promoters, group companies or related parties |
| Competing hypotheses | (a) Commercial advances or deposits at arm's length, e.g. for premises or supplies. (b) Cash moved out of the business (book: trapped cash through advances, p.71). (c) Recoverability doubtful (p.69) |
| Financial effects | Outside net debt: neither cash-like nor debt-like (V2); shown as a separate related-party exposure; recoverability tested, not assumed |
| Possible outcomes | Write-offs; governance findings |
| Evidence — public | Related-party transactions and balances; loans and advances notes; write-offs of deposits |
| Evidence — diligence | Agreements, commercial rationale, repayment history (p.69) |
| Credit reading | Highlight separately; exclude from collateral; monitor further advances |
| Equity reading | Highlight separately; settlement or any price treatment is a negotiation point, not an automatic deduction |
| Source | [Book] pp.69, 71 |

**Treatment rule.** Related-party loans, advances and deposits given are not presumed adverse. They sit outside net debt — neither cash-like nor debt-like — and are always highlighted as a separate related-party exposure and stated explicitly in every analysis, whatever the hypothesis grading (author decision, 1 Nov 2026).

## Sources

- *Financial Due Diligence: Reading Between the Financial Lines*, CA Ayush Bansal, First Edition 2026 (project file): pp.7, 9, 14–16, 22, 31, 34–36, 41, 62, 67–71, 79–83.
- FinDiligent Repository definition docs (FinDiligent project file; not bundled): Working Capital (W4), Debt and Value (V1–V4, V6).
- FDD Book Audit — Critical Reconciliation (FinDiligent project file; not bundled): R1, R7, R8.
- FinDiligent Engine — Design Decisions (FinDiligent project file; not bundled): D18, D36; contingent liabilities choice of 1 Nov 2026.
