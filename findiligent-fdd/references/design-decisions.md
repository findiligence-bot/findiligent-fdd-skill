# FinDiligent Engine — Design Decisions

Version 1.1 · 1 Nov 2026 · Author: CA Ayush Bansal

Thirty-six decisions settled in the 1 November 2026 scoping session, plus D37 (grading evidence weight), added the same day after the first live clipping reading. Each is marked **Author** (the author's choice) or **Default** (set by Claude where the author had no preference). Together with the Phase 2 engine conventions (two of which were later superseded, as marked there) and the four definition docs, this is the base of the methodology specification. 

## Purpose and framing

The engine is a hypothesis repository, not a diligence calculator: it turns public signals into competing explanations, their effects and outcomes, and the evidence still needed.

| # | Decision | Choice | By |
| --- | --- | --- | --- |
| D01 | Engine role | Repository of signal → hypothesis → effect → outcome patterns, applied to news and public filings to reach financial conclusions and list unresolved questions | Author |
| D02 | Status of book cases | Hypothetical patterns used to build hypotheses, not procedures to run | Author |
| D03 | Book ownership | The book's author owns it; Phase 2 "change the book" items are the author's revision backlog | Author |
| D04 | Private-data methods (payroll, trial balance, SKU, invoice ageing) | Become "evidence needed" in each hypothesis, not calculations | Author (framing confirmed) |
| D05 | Audience | Other Claude projects that query the repository; no end-user output is generated here | Author |
| D06 | Pattern origin | Every pattern labelled Book (page), General principle, or Claude-proposed | Default (project instructions) |
| D07 | Pattern entry fields | Trigger · competing hypotheses (always including a benign one) · financial effects · possible outcomes · evidence, public · evidence, diligence · credit reading · equity reading · source and origin | Author + Default |
| D08 | Confidence grading | Supported / Plausible / Unsupported, by the weight of public evidence | Default |
| D37 | Grading evidence weight | Supported needs a reported, already-happened figure (a result, or an amount actually spent). Management guidance, targets, plans and analyst estimates are claims about the future: on their own they grade a hypothesis at most Plausible. Evidence that a cost or event exists does not by itself show it is temporary, structural or recoverable (refines D08) | Author |

### Delivery and contents

| # | Decision | Choice | By |
| --- | --- | --- | --- |
| D34 | Delivery | A Claude skill, loaded automatically by any project or chat facing a financial question, with a GitHub repository as the versioned master copy. Created on the author's instruction | Author |
| D35 | Contents | Pattern library (signal → hypotheses → effects → outcomes → checks) · definitions and formulas · adjustment playbook (QoE, net debt, NWC) · sector KPI guides | Author |
| D36 | Status of adjustments | Every adjustment is labelled indicative, not foolproof: a starting hypothesis that the consuming project must test against evidence, never a definitive figure | Author |

## Inputs and scope

The engine reads only public information about individual listed companies; nothing from private data rooms enters it.

| # | Decision | Choice | By |
| --- | --- | --- | --- |
| D09 | Input sources | Financial newspapers, exchange announcements (existing BSE RSS pipeline), earnings call transcripts and presentations, clippings the user pastes | Author |
| D10 | Data access | Public only; private data-room inputs (trial balances, MIS, registers) are not received. This replaced an earlier "All" answer | Author |
| D11 | Subject scope | Company-specific news only; policy and macro clippings are out of scope | Author |
| D12 | Sector modules from launch | Healthcare (hospitals, IVF, diagnostics) · manufacturing · retail, QSR and consumer · services, IT and education | Author |
| D13 | Reporting basis | Consolidated statements primary; standalone used for checks | Author |
| D14 | History | Three financial years plus the latest quarters (for LTM and seasonality) | Author |
| D15 | Units | INR million, original reported amounts and units preserved | Project instructions |

## House definitions and analytical rules

Printed and house-defined EBITDA are both stored, with every adjustment shown beneath them rather than folded in; consuming projects choose which to rely on (D21).

| # | Decision | Choice | By |
| --- | --- | --- | --- |
| D16 | Book vs mainstream conventions | Both shown side by side, each labelled, unless the author has chosen one basis (working-capital days: revenue basis only, per Working Capital W2) | Default |
| D17 | EBITDA exclusions | Other income; unrealised forex on borrowings; ESOP cost (shown as a separate line); company-labelled exceptional items, flagged when the same category recurs in two of three years | Author + safeguard |
| D18 | Lease basis | Pre-Ind AS 116 by default (EBITDA after cash lease payments; lease liabilities outside net debt); post-116 shown alongside | Author |
| D19 | Deferred revenue and customer advances | In NWC, flagged; debt-like alternative shown when material | Author |
| D20 | Debt-like items | Shown gross and tax-effected | Author |
| D21 | Headline earnings | Both stored as separate fields: the company's printed EBITDA and house-defined EBITDA (D17, D18 applied, no QoE adjustments); the five-layer bridge sits beneath; consuming projects choose | Default (O1) |
| D22 | Management adjusted EBITDA | Shown as layer 1b and tested item by item | Author |
| D23 | Materiality | Flag at 1% of EBITDA or a fixed rupee floor, whichever is lower | Default |
| D24 | Missing evidence | "NQ" with the evidence needed listed; no estimated figure | Default (book convention) |
| D25 | Scenarios | Base, upside, downside built by flexing named drivers from history (volume, price, margin, WC days) | Default |

## How a clipping becomes an insight

1. Take the clipping and identify the company, reporting period and basis (consolidated or standalone).
2. Extract each factual claim and paraphrase it (D29); keep figures and a source link only.
3. Check every claim against the company's own filings and tag it verified, unverified or contradicted (D26). Where a filing conflicts, the filing wins and the gap is itself a finding (D27).
4. Compute the relevant house metrics from the definition files (deterministic, no judgement).
5. Match the signal to one or more pattern-library triggers.
6. Grade each competing hypothesis Supported, Plausible or Unsupported on the public evidence (D08), benign hypothesis first. Guidance and estimates alone grade at most Plausible (D37).
7. List the open questions: the "Evidence — diligence" items public data cannot settle.
8. Store the result as an entry in that company's hypothesis file (D28); archive it after two quarters if unresolved (D30).

A claim is graded only after it has been checked against the company's filings, and graded entries are stored, not published; other projects read them from the repository, and open hypotheses stay in the company file until results confirm, refute or retire them.

## Guidance for consuming projects (carried in the skill)

These rules no longer govern this project; they travel inside the skill as instructions for any project that applies the repository to news or filings.

| # | Decision | Choice | By |
| --- | --- | --- | --- |
| D26 | Claim verification | Every claim cross-checked against filings and tagged verified, unverified or contradicted | Author |
| D27 | Conflicts | Filing wins; the discrepancy becomes a finding in its own right | Author |
| D28 | Output per clipping | A repository entry in that company's hypothesis file: paraphrased claims, verification tags, matched hypotheses, open questions; no insight note | Author |
| D29 | External wording | Never copy wording from external sources; store paraphrased claims, figures and a source link only | Author |
| D30 | Hypothesis lifetime | Unresolved hypotheses archived after 2 quarters; reopened with their history if the trigger recurs | Author (period) + Default (reopen) |
| D31 | Delivery format | None. Superseded: the repository produces no dashboard or report; consuming projects build their own outputs from it | Author |
| D32 | Review gate | Nothing is published from this project. Claude-proposed patterns stay in draft until the author approves them; book-sourced patterns are usable once written, labelled by origin (O8) | Author |
| D33 | Specification home | Specification drafted in this Project; delivered as a skill with a GitHub master copy (D34) | Default |

## Open items

All eight items are resolved or moved to consuming projects; drafting starts with definitions and formulas.

- [x] **O1 — Headline EBITDA.** Resolved by default: both figures stored (D21).
- [x] **O2 — Materiality floor.** Moved: a consuming-project setting; the skill will state the 1%-or-floor rule and leave the floor to each project.
- [x] **O3 — Pilot company.** Moved: a pilot belongs in a consuming project; this repository is tested against the book's own worked cases instead.
- [x] **O4 — Newspaper intake.** Moved: news intake is handled by consuming projects, not this repository.
- [x] **O5 — First library batch.** Resolved: definitions and formulas are drafted first, so every later pattern uses one vocabulary.
- [x] **O6 — Book revisions.** Resolved by default: the repository applies the Phase 2 corrections now; the book is revised later on the author's timeline.

* [x] **O7 — Cross-project access.** Project documents and project memory are not visible to other Claude projects. The repository needs a home those projects can reach: files uploaded to each consuming project, a shared Google Drive folder through the Drive connector, or the author's GitHub repository. Resolved: a Claude skill plus a GitHub master copy (D34).
* [x] **O8 — Library review.** Resolved by default: approval only for Claude-proposed patterns (D32).
