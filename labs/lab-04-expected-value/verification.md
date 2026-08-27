# Lab 4 — Verification & Diagnostics

## Verify
The EV column shows Option 1 = 320, Option 2 = 345, Option 3 = 325; the best-EV flag points to Option 2; EVwPI reads 365 and EVPI reads 20 (all in $'000).

## Failure diagnostics

- **Probabilities do not sum to 1** → F4 must equal 1. A typo in C4:E4 skews every EV. Fix the probabilities first.
- **EV uses the wrong probability row** → Lock the probability range with $C$4:$E$4 so SUMPRODUCT always multiplies by the correct state probabilities.
- **EVPI comes out negative** → You subtracted in the wrong order or picked the wrong best EV. EVPI = EVwPI − best EV and is always ≥ 0.
- **EVwPI equals the best EV** → You averaged option rows instead of taking the best payoff in each state. Use MAX per column for the best-in-state row.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).