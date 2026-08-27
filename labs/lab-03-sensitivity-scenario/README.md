# Lab 3 — Sensitivity and Scenario Analysis

**Topic:** 1  ·  **Maps to:** A2, A3, A6 — review sufficiency and optimal utilisation using the Sensitivity Report and what-if scenarios

**Workbook:** `sensitivity_scenario.xlsx`  ·  **Data:** `data/scenarios.csv`

## Objective
Read the Solver Sensitivity Report to value each resource (shadow prices) and find the ranges over which the plan holds, then run what-if scenarios that change a resource limit or a profit rate.

## You will build
A Sensitivity Report with shadow prices and allowable ranges, plus a small scenario table comparing profit as baking powder and profit rates change.
*Tools: Microsoft Excel, Solver add-in, Scenario Manager / Data Table.*

## How the lab runs
1. **Re-solve with the report** — Generate the Sensitivity Report alongside the Answer Report.
2. **Value the resources** — Shadow price = extra profit per one more unit of a binding resource.
3. **Read the ranges** — Allowable increase/decrease shows how far data can move before the basis changes.
4. **Run scenarios** — Change baking powder or a profit rate and re-solve to see the plan shift.
5. **Recommend** — Buy more of the resource with the highest shadow price, within its range.

## Step-by-step (click-by-click)
1. **Re-run Solver with the Sensitivity Report**
   Data → Solver → Solve → in Reports select both Answer and Sensitivity → OK. A new 'Sensitivity Report' sheet is created.
2. **Read the shadow prices**
   In the Constraints table, the Shadow Price column values the binding resources: baking powder ≈ $15 per kg; man-hours = $0 (spare capacity).
3. **Read the RHS ranges**
   Allowable Increase / Decrease show how far each limit can move before the shadow price changes — the range over which the price is valid.
4. **Read the objective ranges**
   In the Variable Cells table, Allowable Increase / Decrease on the profit coefficients show how much a price can change before the optimal plan changes.
5. **Set up a scenario**
   Copy the baking-powder limit G9 to a scenario area. Using Scenario Manager (Data → What-If Analysis → Scenario Manager) add scenarios: G9 = 8, 10, 12 kg.
6. **Compare scenarios**
   Show each scenario and record the new optimal profit from E6 to see the value of extra baking powder.
7. **Stress a profit rate**
   Change the chocolate profit D6 from 3 to 2.5 and re-solve; note whether the optimal mix changes.
8. **Write the recommendation**
   Recommend acquiring the binding resource with the highest shadow price, but only up to its allowable increase.

## Expected outputs
- **Baking powder shadow price:** ≈ $15 / kg (binding)
- **Man-hours shadow price:** $0 (slack 5 hr)
- **+2 kg baking powder:** Profit rises ≈ $30 (within range)
- **Recommendation:** Buy baking powder, not man-hours

## Test it
The Sensitivity Report shows baking powder with a positive shadow price and man-hours with a $0 shadow price; increasing baking powder within its allowable increase raises profit by about $15 per kg, and the scenario table shows profit rising as the baking-powder limit increases.

## If it doesn't work — diagnostics
- **No Sensitivity Report is produced** → You must select Simplex LP; the GRG Nonlinear engine gives a different report. Re-solve with Simplex LP.
- **All shadow prices are zero** → No constraint is binding — the solution is interior or the model is under-constrained. Re-check the resource limits.
- **Shadow price used outside its range** → A shadow price is only valid within the allowable increase/decrease. Beyond it, re-solve rather than extrapolate.
- **Scenario profit does not change** → The changed resource was not binding (had slack), so more of it adds no value — spend on the binding resource instead.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
