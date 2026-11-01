---
name: findiligent-fdd
description: FinDiligent financial due diligence repository (CA Ayush Bansal's methodology) — house definitions, formulas, pattern libraries and adjustment logic for reading Indian company financials. Use it whenever a task involves analysing a company's results, earnings quality, EBITDA adjustments, working capital, net debt, leverage, DSCR, cash conversion, returns, a financial news clipping or exchange filing, credit or equity diligence, or any "what does this number mean / what could explain it" question, even if the user does not mention diligence or FinDiligent by name.
---

# FinDiligent — Financial Due Diligence Repository

A research repository, not a report generator. It gives the analysing project one shared vocabulary (definitions and formulas) and a library of signal → hypotheses → effects → outcomes → evidence patterns, drawn from *Financial Due Diligence: Reading Between the Financial Lines* (CA Ayush Bansal, First Edition 2026) and the corrections and decisions made while turning that book into a method.

The consuming project produces its own output. This skill supplies the reasoning that output should rest on.

## Non-negotiable rules

1. **Indicative, not foolproof (D36).** Every adjustment, effect and hypothesis here is a starting point to test against evidence, never a definitive figure. Say so when you use one.
2. **Never estimate a missing amount (D24).** If an adjustment has no evidence for its quantum, show it as **"NQ"** (not quantified) and list the evidence needed. Exception: where one *component* of a metric cannot be separated, still compute the metric without it and label what it excludes, e.g. "gross margin, excluding plant labour (not separable)".
3. **Label origins.** **[Book]** + page · **[Book, corrected]** (a reconciliation fix) · **[GAAP]** · **[Claude]** (proposed, not from the book). Never attribute an invented rule to the book.
4. **Always test a benign hypothesis first.** Revenue growth is not automatically good; falling margin is not automatically bad. Grade hypotheses Supported / Plausible / Unsupported on the public evidence actually found (D08). Supported needs a reported, already-happened figure (a result, or an amount actually spent). Management guidance, targets, plans and analyst estimates are claims about the future: on their own they grade a hypothesis at most Plausible. Evidence that a cost or event exists does not by itself show it is temporary, structural or recoverable (D37).
5. **Filings beat news (D26–D27).** Verify every claim against the company's own filings and tag it verified, unverified or contradicted. A conflict is itself a finding.
6. **Never copy external wording (D29).** Paraphrase claims; keep figures and a source link only.
7. **Related-party advances are not a red flag by default.** Loans, advances and deposits *given* to promoters, group or related parties sit outside net debt (neither cash-like nor debt-like) and are always highlighted separately and stated explicitly (BS12).
8. **Keep calculation separate from interpretation.** Compute metrics deterministically from the definition files; put judgement in the pattern reading.
9. **Units and periods.** INR million; preserve original reported amounts and units. Fiscal label plus months, e.g. "Q3 FY26 (Oct–Dec 2025)". Consolidated by default (D13).

## How to work a signal

1. Identify the company, period, basis and units. Check the data is from filings, not only news.
2. Compute the house metrics you need from the definition files (below). State the basis of every figure: growth basis (YoY / CAGR / cumulative), closing or average balance, lease basis.
3. Match the signal to pattern triggers. One signal often hits several libraries; economically connected metrics are read together (for example revenue growth + receivables growth → RQ05 and CC01).
4. For each matched pattern, work the competing hypotheses, benign one first, and grade them.
5. Translate the adverse hypotheses into financial effects using the house vocabulary (earnings-bridge layer, debt-like item, NWC, lease basis).
6. Give the credit reading and/or equity reading as the task requires.
7. List open questions: the "Evidence — diligence" items that public data cannot settle. Never assume their answers.

## Reference files — read the one you need

| File | Read it when you need |
| --- | --- |
| `references/definitions-earnings.md` | Revenue and growth bases (E1); material margin and **sector gross margin** with the sector direct-cost table (E2); the four EBITDAs and the pre/post Ind AS 116 rule (E3); margin walk (E4); **five-layer earnings bridge** (E5); attached variable costs on revenue adjustments (E6); checks V1–V9 |
| `references/definitions-working-capital.md` | One home per balance (W1); DIO/DSO/DPO on revenue (W2); September/H1 normal level and the 15-day H1-vs-FY flag (W3); adjusted NWC and the peg (W4); special balances (W5); checks WV1–WV6 |
| `references/definitions-debt-and-value.md` | Net debt structure (V1); cash-like items and restricted cash (V2); debt-like items and tax effect (V3); lease pairing (V4); transaction and market EV bridges (V5); leverage, interest cover and **Indian-bank DSCR** (V6); checks DV1–DV6 |
| `references/definitions-returns-and-cash.md` | ROCE, gross cash return, asset turnover, ROE on average capital (R1); OCF ÷ EBITDA cash conversion with lease pairing (R2); capex split and asset-health indicators — maintenance capex is never estimated (R3); checks RC1–RC5 |
| `references/patterns-revenue-quality.md` | RQ01–RQ12: non-recurring growth, price vs volume, mix, gross-to-net, channel stuffing, upfront recognition, fixed→variable income, renewal cliffs, key-person, concentration, churn, lower-quality volume. Also explains the nine pattern fields |
| `references/patterns-cash-conversion.md` | CC01–CC11: receivables, unbilled revenue, inventory, payables stretch, pre-sale WC starvation, capitalised opex, deferred maintenance, revenue-to-cash gap, trapped cash, customer float, capex without returns |
| `references/patterns-cost-and-margin.md` | CM01–CM12: input-cost spikes, falling employee cost share, pay pockets, statutory compliance gaps (Labour Codes), attrition, wage settlements, key-professional cost, legal spikes, recurring one-offs, promoter costs, marketing cuts, carve-out allocations |
| `references/patterns-balance-sheet-obligations.md` | BS01–BS12: promoter demand loans, deal-triggered payouts, debt hidden in operating lines, unfunded employee obligations, litigation and tax, overdue statutory dues, leases, purchase commitments, acquisition obligations, covenants and guarantees, hybrid instruments, related-party advances |
| `references/design-decisions.md` | Why the method is shaped this way (D01–D37), including the consuming-project rules D26–D30 and the clipping-to-entry flow |

Large files: search for the code you need (e.g. `CC04`, `## V6`) rather than reading everything.

## Quick reference (full definitions in the files)

- **House EBITDA (post-116)** = PBT before exceptional items + finance costs + D&A − other income + unrealised FX loss on borrowings + ESOP cost.
- **House EBITDA (pre-116, default for leverage and valuation)** = post-116 house EBITDA − cash lease payments (principal + interest, from the cash flow statement). If not disclosed: pre-116 is NQ; use post-116 EBITDA with disclosed lease liabilities in net debt, labelled "lease payments not disclosed".
- **Pairing rule:** pre-116 EBITDA ↔ net debt excluding leases; post-116 EBITDA ↔ net debt including leases. Mixing them is invalid.
- **Sector gross margin** = revenue − material cost − sector direct costs (healthcare: doctor cost; consumer and retail/QSR: packaging; manufacturing: power and fuel, job-work, direct plant labour, freight inward; services, IT, education: employee cost).
- **Revenue adjustments never pass to EBITDA in full by default:** adjust the attached variable costs too (E6).
- **Earnings bridge layers:** 0 house · 1b management adjustments (tested) · 2 Ind AS corrections · 3 normalisations · 4 executed pro-forma · 5 prospective pro-forma. A "one-off" recurring in two of three years goes back into the base.
- **WC days** use revenue as the single denominator; normal level = September balance ÷ H1 revenue × 183; flag a gap above 15 days between H1 and FY readings.
- **Net debt** = financial debt (promoter debt on its own line) + debt-like items − free cash-like items. Contingent liabilities are listed, not included.
- **DSCR (Indian bank convention)** = (PAT + depreciation + interest on term debt) ÷ (interest on term debt + principal due within 12 months). Principal from the maturity note, else current maturities (labelled); if neither, do not compute or show DSCR.
- **Cash conversion** = operating cash flow ÷ house EBITDA, same lease basis.

## Regulatory anchors (check for later changes before relying on them)

Ind AS 116 from 1 Apr 2019 · Ind AS 7 supplier-finance disclosures for annual periods from 1 Apr 2025 · GST rate rationalisation from 22 Sep 2025 · Labour Codes in force from 21 Nov 2025 · Income-tax Act, 2025 from 1 Apr 2026 (cite its sections for later periods). Dated parameters such as bonus and overtime rules change; verify the regime in force for each period analysed.

## Out of scope

No buy/sell/hold recommendations. No macro or policy views as such (D11). The repository does not produce dashboards or reports (D31); the consuming project decides the output.
