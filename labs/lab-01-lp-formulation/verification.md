# Lab 1 — Verification & Diagnostics

## Verify
The worksheet shows a single objective cell (E6) and four constraint LHS cells (E9:E12), each a SUMPRODUCT of coefficients and the changing cells. With X1=X2=0 the objective reads 0 and every constraint LHS reads 0.

## Failure diagnostics

- **Objective is a fixed number, not a formula** → You typed the profit instead of =SUMPRODUCT(...). Solver can only optimise a cell that depends on the changing cells.
- **Constraint uses absolute vs relative refs wrongly** → Lock the changing cells with $C$4:$D$4 so the formula copies down correctly.
- **A resource limit is on the wrong side** → The limit (RHS) is a constant in column G; the used amount (LHS) is the SUMPRODUCT in column E. Do not swap them.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).