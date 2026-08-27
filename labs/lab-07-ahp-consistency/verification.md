# Lab 7 — Verification & Diagnostics

## Verify
The priority vector reads Cost 0.398, Quality 0.085, Delivery 0.218, Flexibility 0.299 (sum 1.000); lambda_max = 4.185, CI = 0.062, CR = 0.068 which is ≤ 0.10, so the criteria weights are consistent and usable.

## Failure diagnostics

- **Priorities do not sum to 1** → You averaged the raw matrix, not the column-normalised matrix. Normalise each column first, then average the rows.
- **CR is above 0.10** → Judgements conflict (e.g. A≫B, B≫C but A≈C). Revisit the largest inconsistency and re-judge that pair.
- **Matrix is not reciprocal** → Every lower-triangle cell must be 1/(its mirror). Enter reciprocals with =1/cell, never by hand.
- **Wrong RI used** → RI depends on n: RI(3)=0.58, RI(4)=0.90, RI(5)=1.12. Using the wrong RI makes CR meaningless.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).