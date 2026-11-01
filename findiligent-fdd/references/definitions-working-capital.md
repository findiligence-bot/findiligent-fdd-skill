# FinDiligent Repository — Working Capital Definitions

Version 1.0 · 1 Nov 2026 · Author: CA Ayush Bansal

The working-capital vocabulary for every pattern and consuming project. It follows the conventions of the Earnings Definitions doc (units, periods, origin labels, indicative-not-foolproof) and the author's decisions of 1 November 2026. INR million throughout.

## W1 — One home per balance

Every balance-sheet line is mapped to exactly one bucket, and the same mapping applies to every period compared; this is what prevents an item being counted in both working capital and net debt ([Book] pp.82–83; Phase 2, area 8).

| Bucket | Contents | Book reference |
| --- | --- | --- |
| Core working capital | Inventories + trade receivables − trade payables | [Book] pp.21, 82 |
| Other operating items | Employee payables, statutory dues within due date, operating prepayments and advances, customer advances and deferred revenue (D19, flagged) | [Book] pp.69, 82 |
| Net working capital (NWC) | Core working capital + other operating items | [Book, corrected] p.21 "Trade working capital" = p.82 "Reported Net-working capital" (D6) |
| Net debt — financial debt | Borrowings, accrued interest on borrowings | [Book] pp.70, 78–79 |
| Net debt — debt-like | All debt-like items in Debt and Value V3, including capital creditors, stretched payables above normal terms, unpaid dividends, unfunded gratuity, net current tax, overdue statutory dues, employee compliance arrears and reverse factoring | [Book] pp.67–68, 78–80 |
| Net debt — cash-like | Free cash and equivalents, accrued interest on deposits; restricted cash only where linked to a debt already included | [Book] pp.71, 79 |
| Excluded | Capital advances (to capex), long-term investments, deferred tax, equity; related-party loans, advances and deposits given (highlighted separately) | [Book] pp.69, 83 |

```latex
\text{Core WC} = \text{Inventories} + \text{Trade receivables} - \text{Trade payables} \qquad \text{NWC} = \text{Core WC} + \text{Other operating assets} - \text{Other operating liabilities}
```

**Worked example (book p.21):** core working capital 40 / 130 / 145 and NWC 130 / 202 / 190 for Mar-24 to Mar-26.

**Contested items** (customer advances and deferred revenue, lease liabilities, reverse factoring) sit in their default bucket, flagged, with the alternative computed beside them; they are never placed in two buckets at once.

## W2 — Working-capital days

All three days metrics use revenue from operations as the single denominator, as in the book; that makes them add up exactly to core working-capital days ([Book] p.21; author decision, overriding the Phase 2 two-family proposal).

```latex
\text{DIO} = \frac{\text{Inventories}}{R} \times d \qquad \text{DSO} = \frac{\text{Trade receivables}}{R} \times d \qquad \text{DPO} = \frac{\text{Trade payables}}{R} \times d
```

```latex
\text{Core WC days} = \text{DIO} + \text{DSO} - \text{DPO} = \frac{\text{Core WC}}{R} \times d \qquad \text{NWC days} = \frac{\text{NWC}}{R} \times d
```

where R is revenue for the period and d is the days in that period (365 for a year, 183 for April–September).

**Which balance.** Where quarterly or monthly balances exist, use the average of the period-end balances across the last 12 months (opening plus each quarter-end); this removes seasonal and year-end distortion. Otherwise use the closing balance (book method). The basis used is always stated.

**Worked example (book p.21, closing balances):**

| Days | Mar-24 | Mar-25 | Mar-26 |
| --- | --- | --- | --- |
| DIO | 52 | 50 | 33 |
| DSO | 31 | 38 | 55 |
| DPO | 63 | 34 | 35 |
| Core WC days | 21 | 55 | 53 |

**Worked example — average balance (hypothetical).** Receivables of 90 (opening), 120, 140, 160 and 150 at the five quarter-ends; LTM revenue 1,000. Average balance 132 gives DSO of 48 days, against 55 on the closing balance. The 7-day gap is itself a signal of a year-end receivables build.

**Interpretation caveats.**

- On a revenue basis, DIO and DPO measure working capital per rupee of sales, not how long stock is held or suppliers are paid. Patterns must not read revenue-based DIO as "days of stock" ([Book, corrected] p.64).
- Receivables and payables include GST; revenue does not. At an 18% rate, DSO reads about 18% high relative to a GST-consistent measure. Compare companies and periods only where the GST mix is similar, and flag large changes in it.

## W3 — Half-year reading and normal working-capital level

Listed Indian companies publish balance sheets at September and March, so each year gives two readings: September balances against H1 revenue, and March balances against full-year revenue. Comparing them shows seasonality and year-end window dressing ([Book] pp.57, 83; author decision).

```latex
\text{Days}_{H1} = \frac{\text{September balance}}{R_{\text{Apr–Sep}}} \times 183 \qquad \text{Days}_{FY} = \frac{\text{March balance}}{R_{\text{Apr–Mar}}} \times 365
```

```latex
\text{Normal WC days} = \text{Days}_{H1} = \frac{\text{September balance}}{R_{\text{Apr–Sep}}} \times 183 \quad \text{(latest September reading)}
```

The normal level is the September reading alone, confirmed by the author (1 Nov 2026). The March reading is still computed, to test year-end positions against it.

**Worked example (hypothetical).** September receivables 140 on H1 revenue 480 give DSO of 53 days; March DSO is 55 (book p.21). The readings agree, so year-end receivables look representative. Had September DSO been 75, either the business is seasonal, which the pattern library tests against quarterly revenue, or March collections were pulled forward ([Book] p.72, working-capital starvation).

**Signal thresholds.** A gap of more than 15 days between the H1 and FY readings of the same metric is flagged for a seasonality-or-window-dressing test. The 15-day trigger is confirmed by the author (1 Nov 2026).

**Edge cases.** H1 revenue is often seasonally different from H2 revenue (e.g. the festive quarter falls in Q3); the H1 reading measures the September balance against its own half, which is the intended comparison. Acquisitions between September and March distort both readings; restate or flag.

## W4 — Adjusted NWC and the NWC peg

Adjusted NWC is reported NWC after pushing through the balance-sheet effect of earnings corrections and moving net-debt items out; the peg is the normal level of adjusted NWC a business needs ([Book] pp.82–83). Each adjustment is indicative, not foolproof (D36).

| Adjustment | Effect on NWC | Moves to | Book reference |
| --- | --- | --- | --- |
| Doubtful-debt under-provision | Reduces receivables | Earnings layer 2 | p.82 |
| Inventory write-off or obsolescence | Reduces inventories | Earnings layer 2 | p.82 |
| Under-accrued expenses, R&M | Increases other liabilities | Earnings layer 2 | p.82 |
| Cut-off (period) adjustments | Either direction, by nature | Earnings layer 2 | p.82 |
| Accrued interest on borrowings / on deposits | Removed from other liabilities / other assets | Net debt / cash-like | p.82 |
| Unpaid dividend | Removed from other liabilities | Net debt (debt-like) | p.82 |
| Capital creditors | Removed from trade payables | Net debt (debt-like) | p.82 |
| Stretched payables above normal terms | Excess removed from trade payables | Net debt (debt-like) | p.82 |
| Unfunded gratuity | Removed from provisions | Net debt (debt-like) | p.82 |
| Provision for tax / advance tax | Removed from liabilities / assets | Net debt (net current tax) | p.82 |
| Reverse factoring | Removed from trade payables | Net debt (debt-like) | [Book, corrected] pp.67–68 (E6) |

**Items that never enter NWC:** employee compliance arrears, settled one-off expenses, restricted cash, preference shares, deferred maintenance capex, transaction costs and litigation ([Book] p.83).

```latex
\text{Adjusted NWC} = \text{Reported NWC} \pm \text{balance-sheet effect of earnings corrections} - \text{net-debt items reclassified}
```

**The peg.** In a transaction, the peg is the adjusted NWC the business is expected to be delivered with; a closing NWC above the peg raises the price and one below reduces it ([Book] p.82). For seasonal businesses the book uses a rolling 12-month average ([Book] p.83). On public data, a consuming project should use the normal WC days from W3, applied to the relevant revenue base, and label the result an indicative proxy for the peg, not a peg.

**Consistency rule.** The peg and the closing NWC must use the identical bucket mapping (W1) and identical adjustments in every period; an item removed at closing but left in the September reading is a double count.

## W5 — Special balances

Seven balances distort working-capital metrics if left inside them unexamined; each has a default treatment and a test.

| Balance | Default treatment | Test before relying on it | Book reference |
| --- | --- | --- | --- |
| Retention receivables | Carved out of trade receivables; shown as a separate operating asset outside DSO | Collection due 12–24 months out; contract milestone terms | [Book] p.66 |
| Unbilled revenue / contract assets | Inside receivables, flagged | Subsequent billing and collection; growth faster than revenue suggests premature recognition | [Book] pp.54, 65–66 |
| Customer advances and deferred revenue | NWC, flagged; debt-like alternative shown when material | Is it a genuine future performance obligation? Ageing of long-outstanding advances | [Book] pp.60, 69; D19 |
| Reverse factoring / supplier finance | Debt-like; out of payables and DPO | Ind AS 7 supplier-finance disclosures (annual periods from 1 April 2025) | [Book] pp.67–68; Phase 2 R8 |
| Capital creditors and capital advances | Out of NWC: creditors to net debt, advances excluded | Capex linkage | [Book] pp.69, 79 |
| Stretched payables | Excess over normal terms to net debt | Payables ageing against contractual terms; DPO jump before a transaction | [Book] pp.67, 80 |
| Overdue statutory dues | Overdue portion to net debt (debt-like) | Ageing beyond statutory due dates | [Book] p.69 |

**Payor segmentation.** Where receivables mix payor types with different cycles (TPA, government, corporate, self-pay in hospitals; government-sponsored students in education), blended DSO is reported only alongside the segments that the disclosures allow ([Book] pp.52, 65).

## Validation rules

Six checks guard every working-capital figure a consuming project draws from the repository.

| # | Check | Fails when | Traces to |
| --- | --- | --- | --- |
| WV1 | Single home | A balance appears in more than one bucket, or the mapping differs between periods compared | W1; Phase 2 area 8 |
| WV2 | Days add up | DIO + DSO − DPO does not equal core WC days on the same revenue and balance basis | W2 |
| WV3 | Basis stated | A days figure does not state closing vs average balance and annual vs half-year revenue | W2, W3 |
| WV4 | Label match | A total called "trade working capital" includes other operating items | [Book, corrected] p.21 (D6) |
| WV5 | H1 vs FY gap | The same metric differs by more than 15 days between the September and March readings without explanation | W3 |
| WV6 | Peg consistency | An item removed from closing NWC is left in the September reading used for the normal level | W4 |

## Sources

- *Financial Due Diligence: Reading Between the Financial Lines*, CA Ayush Bansal, First Edition 2026 (project file): pp.21–22, 52, 54, 57, 60, 64–72, 78–83.
- FDD Book Audit — Critical Reconciliation (FinDiligent project file; not bundled): D6, E6, N3, R8, focus areas 1 and 8.
- FinDiligent Engine — Design Decisions (FinDiligent project file; not bundled): D19, D36; working-capital choices made on 1 Nov 2026 (balance rule, half-year reading, revenue denominator for DPO).
