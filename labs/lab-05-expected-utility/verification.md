# Lab 5 — Verification & Diagnostics

## Verify
EV_A = EV_B = 50, but EU_A = 7.035 > EU_B = 6.325 and CE_A = 49.5 > CE_B = 40.0, so the risk-averse choice is Project A; Project B carries a $10k risk premium versus A's $0.5k.

## Failure diagnostics

- **Both projects tie** → You compared EV, not expected utility. With equal EV the tie-break is EU / certainty equivalent, not EV.
- **Utility applied to the EV instead of each outcome** → Apply U(x) to every outcome first, then average — U(E[x]) ≠ E[U(x)] (that gap is exactly the risk premium).
- **Certainty equivalent exceeds EV** → For a risk-averse (concave) utility, CE ≤ EV always. A CE above EV means the inverse was applied wrongly.
- **Risk-seeking result** → √x is concave (risk-averse). A convex utility (e.g. x²) would flip the choice toward the risky project — pick the curve that matches the manager's attitude.

## Re-solve / re-check
Open the workbook and confirm the highlighted result cells match the Expected Outputs. Formulas recompute automatically; for the LP labs, reset the yellow changing cells to 0 and re-run Solver (Data → Solver, Simplex LP).