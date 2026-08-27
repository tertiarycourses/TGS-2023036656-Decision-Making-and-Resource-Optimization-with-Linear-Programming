# Lab 3 — Verification & Diagnostics

## Verify
The Sensitivity Report shows baking powder with a positive shadow price and man-hours with a $0 shadow price; increasing baking powder within its allowable increase raises profit by about $15 per kg, and the scenario table shows profit rising as the baking-powder limit increases.

## Failure diagnostics

- **No Sensitivity Report is produced** → You must select Simplex LP; the GRG Nonlinear engine gives a different report. Re-solve with Simplex LP.
- **All shadow prices are zero** → No constraint is binding — the solution is interior or the model is under-constrained. Re-check the resource limits.
- **Shadow price used outside its range** → A shadow price is only valid within the allowable increase/decrease. Beyond it, re-solve rather than extrapolate.
- **Scenario profit does not change** → The changed resource was not binding (had slack), so more of it adds no value — spend on the binding resource instead.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).