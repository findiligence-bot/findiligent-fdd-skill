# FinDiligent — Financial Due Diligence Repository

Master copy of the `findiligent-fdd` Claude skill: house definitions, formulas and pattern libraries for reading Indian company financials, drawn from *Financial Due Diligence: Reading Between the Financial Lines* (CA Ayush Bansal, First Edition 2026).

This is a research repository. It produces no reports or dashboards; other Claude projects load the skill and build their own outputs on it. Every adjustment is **indicative, not foolproof**.

## Layout

```
findiligent-fdd/
├── SKILL.md                     rules, workflow, index, quick reference
└── references/
    ├── definitions-earnings.md          E1–E6, V1–V9
    ├── definitions-working-capital.md   W1–W5, WV1–WV6
    ├── definitions-debt-and-value.md    V1–V6, DV1–DV6
    ├── definitions-returns-and-cash.md  R1–R3, RC1–RC5
    ├── patterns-revenue-quality.md      RQ01–RQ12
    ├── patterns-cash-conversion.md      CC01–CC11
    ├── patterns-cost-and-margin.md      CM01–CM12
    ├── patterns-balance-sheet-obligations.md  BS01–BS12
    ├── analyst-lenses.md                AL01–AL02: general lessons for every analysis
    ├── sector-hotels.md                 H1–H3: hotel KPIs, RevPAR reading, Q2 FY27 context
    ├── design-decisions.md              D01–D46
    └── consuming-project-carousel.md    C1–C4: company carousel rules, template, checks
```

## Install

Download `findiligent-fdd.skill` from a release (or zip the `findiligent-fdd/` folder) and upload it to Claude as a skill.

## Changing the method

Edit the files on a branch and open a pull request. Keep deterministic definitions (definition files) separate from interpretation (pattern files), label every rule's origin ([Book], [Book, corrected], [GAAP], [Claude]), and record new decisions in `design-decisions.md`.

## Planned

More sector KPI guides and the adjustment playbook (QoE, net debt, NWC).

## Version

1.3 — 21 November 2026. First weekly insights intake: analyst lenses AL01–AL02, the hotel sector guide, the [Author] origin label and D45–D46. New insights are logged in `insights-inbox.md` and added weekly.

1.2 — 14 November 2026. Adds D38–D44 from the Ather Energy carousel review (written-back income inside EBITDA, stretched payables measured, liens of undisclosed purpose, accounting check before findings, one EBITDA in outputs, "~" for indicative figures) and the consuming-project carousel guide.

1.1 — 1 November 2026. Adds D37: guidance and estimates alone grade a hypothesis at most Plausible.

1.0 — 1 November 2026.
