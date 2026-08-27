# Lab 2 — Verification & Diagnostics

## Verify
The changing cells read X1=25 and X2=37.5, the objective E6 reads 162.5, and the Answer Report lists baking powder and vanilla-demand as Binding (slack 0) while man-hours and chocolate-demand are Not Binding (slack 5 and 22.5).

## Failure diagnostics

- **Solver is not on the Data tab** → The add-in is not loaded — repeat the Add-ins step and tick 'Solver Add-in'.
- **'Solver could not find a feasible solution'** → A constraint is impossible or a sign is reversed. Check every LHS ≤ RHS and that the RHS limits are positive.
- **'The Objective Cell values do not converge' (unbounded)** → A binding resource constraint is missing, so profit can grow without limit. Add the omitted constraint.
- **Fractional answer 37.5 looks wrong** → LP allows divisible outputs; 37.5 batches is valid here. Add an integer constraint only if the product is truly indivisible.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).