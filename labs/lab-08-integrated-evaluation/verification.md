# Lab 8 — Verification & Diagnostics

## Verify
The synthesis table ranks Plan P = 0.393 first, then Plan R = 0.309 and Plan Q = 0.299 (sum ≈ 1.000); the KPI dashboard carries the AHP-derived weights (Cost 40%, Flexibility 30%, Delivery 22%, Quality 8%) each mapped to a measurable KPI.

## Failure diagnostics

- **Global scores do not sum to ~1** → Either the criteria weights or a local-score column does not sum to 1. Re-normalise before synthesising.
- **A plan wins on one criterion but loses overall** → That is correct behaviour — synthesis balances all criteria by weight, not a single strength.
- **KPI weights ignore AHP** → Derive KPI weights from the AHP priorities so monitoring reflects the same priorities used to choose the plan.
- **No trigger threshold set** → A KPI without a threshold cannot prompt review. Define the value that forces re-allocation (A8).

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).