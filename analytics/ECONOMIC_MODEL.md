# Reconciled Economic Model

This document defines the **public, internally consistent economic model** for the academic modernization case study.

It does not replace the defended thesis. Instead, it separates arithmetic that can be reproduced from historical thesis-reported KPI values that were calculated under assumptions not fully preserved in the public artifacts.

## Source values retained from the project materials

The project materials contain the following business-case inputs:

- traditional annual operating cost: **€430,000**;
- optimized annual operating cost: **€262,000**;
- avoided annual incident/loss effect: **€247,000**;
- implementation investment range: **€180,000–€220,000**.

The defense materials also report **€175,000 direct savings**, **€422,000 annual economic effect**, **28% ROI** and **1.4-year payback**. Those four values are retained as thesis-reported historical values, but they are not treated as outputs of the reconciled model because they do not all follow from the same published inputs.

## Reconciled OPEX calculation

Annual operating-cost saving:

```text
€430,000 - €262,000 = €168,000 per year
```

OPEX reduction:

```text
€168,000 / €430,000 = 0.390697...
                       ≈ 39.1%
```

Therefore the public portfolio may describe the OPEX reduction as **approximately 39%**, or as **approximately 40%** when clearly labeled as a rounded value.

The previously reported **€175,000 direct-saving** value is not used in the reconciled arithmetic because it differs by €7,000 from the explicit €430,000 and €262,000 operating-cost figures.

## Reconciled annual economic effect

Using the explicit OPEX saving and the project assumption for avoided incident losses:

```text
OPEX saving                  €168,000
Avoided incident/loss effect €247,000
                             --------
Gross annual economic effect €415,000
```

The public reconciled annual effect is therefore **€415,000/year**.

The thesis-reported **€422,000/year** value can be reproduced only by using the separate €175,000 direct-saving figure:

```text
€175,000 + €247,000 = €422,000
```

Because €175,000 conflicts with the explicit €430,000 → €262,000 OPEX calculation, €422,000 remains a **legacy thesis-reported value**, not the canonical public-model result.

## Payback calculation

For a simple undiscounted payback calculation:

```text
Payback = Initial investment / Annual economic effect
```

Using the reconciled €415,000 annual effect:

```text
€180,000 / €415,000 = 0.434 years ≈ 5.2 months
€220,000 / €415,000 = 0.530 years ≈ 6.4 months
```

Therefore the reconciled full-effect case gives a simple payback range of approximately **0.43–0.53 years**.

A more conservative OPEX-only view, excluding avoided incident losses, gives:

```text
€180,000 / €168,000 = 1.07 years
€220,000 / €168,000 = 1.31 years
```

This explains why payback is highly dependent on which benefit categories are included, but the published inputs still do not reproduce exactly **1.4 years**. The 1.4-year value remains **thesis-reported** unless its original cash-flow assumptions are recovered.

## ROI calculation

The repository uses one explicit simple first-year ROI definition for the reconciled scenario:

```text
ROI = (Annual economic effect - Initial investment) / Initial investment × 100%
```

Using €415,000 annual effect and the €180,000–€220,000 investment range:

```text
At €180,000 investment:
ROI = (€415,000 - €180,000) / €180,000 × 100%
    ≈ 130.6%

At €220,000 investment:
ROI = (€415,000 - €220,000) / €220,000 × 100%
    ≈ 88.6%
```

The reconciled first-year simple ROI range is therefore approximately **88.6%–130.6%**.

The thesis-reported **28% ROI** cannot be reproduced from the same €415,000 annual effect and €180,000–€220,000 investment range using this formula. It is retained only as a historical thesis metric until its original ROI definition, time horizon and cash-flow inputs are available.

## Canonical public KPI set

For the GitHub portfolio, use the following internally consistent values:

- annual operating-cost baseline: **€430,000**;
- optimized annual operating cost: **€262,000**;
- annual OPEX saving: **€168,000**;
- OPEX reduction: **39.1% (~40% rounded)**;
- avoided-loss assumption: **€247,000/year**;
- reconciled gross annual economic effect: **€415,000/year**;
- investment range: **€180,000–€220,000**;
- simple full-effect payback: **0.43–0.53 years**;
- simple first-year ROI: **88.6%–130.6%**.

These are **academic case-study calculations**, not Cisco product benchmarks and not audited corporate financial forecasts.

## Legacy thesis-reported values

The following values may still be mentioned when discussing the defended thesis, but they must be labeled as historical thesis-reported figures rather than outputs of the reconciled public model:

- direct savings: **€175,000/year**;
- annual effect: **€422,000/year**;
- ROI: **28%**;
- payback: **1.4 years**.

## Publication rule

When a README, presentation or portfolio description uses an economic KPI, it should either:

1. use the reconciled public model above; or
2. explicitly label the number as **thesis-reported / legacy** and avoid mixing it into the reconciled calculation chain.
