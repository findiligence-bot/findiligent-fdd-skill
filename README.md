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
    └── design-decisions.md              D01–D37
```

## Install

Download `findiligent-fdd.skill` from a release (or zip the `findiligent-fdd/` folder) and upload it to Claude as a skill.

## Changing the method

Edit the files on a branch and open a pull request. Keep deterministic definitions (definition files) separate from interpretation (pattern files), label every rule's origin ([Book], [Book, corrected], [GAAP], [Claude]), and record new decisions in `design-decisions.md`.

## Planned

Sector KPI guides and the adjustment playbook (QoE, net debt, NWC).

## Version

1.1 — 1 November 2026. Adds D37: guidance and estimates alone grade a hypothesis at most Plausible.

1.0 — 1 November 2026.
