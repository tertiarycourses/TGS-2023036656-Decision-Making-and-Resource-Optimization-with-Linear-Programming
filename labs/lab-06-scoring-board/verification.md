# Lab 6 — Verification & Diagnostics

## Verify
The weighted totals read Supplier A = 42, Supplier B = 41, Supplier C = 40, so Supplier A ranks first; raising the Price weight shifts the ranking toward Supplier B.

## Failure diagnostics

- **All suppliers score the same** → The weights are all equal or all 1. Differentiate the weights to reflect real priorities.
- **Ratings on different scales** → Keep every criterion on the same 1-5 scale, or normalise first — mixing scales silently biases the total.
- **Ranking feels arbitrary** → Scores are close (42/41/40). That fragility is exactly why AHP's pairwise weighting is used next.
- **A 'lower is better' criterion inflates the score** → Reverse the scale for cost-type criteria (5 = cheapest) or the total rewards the wrong option.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).