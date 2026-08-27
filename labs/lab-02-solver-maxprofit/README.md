# Lab 2 — Solve for Maximum Profit with Excel Solver

**Topic:** 1  ·  **Maps to:** A2, K1 — develop an allocation plan that maximises profit using the Excel Solver

**Workbook:** `solver_maxprofit.xlsx`  ·  **Data:** `data/solver_targets.csv`

## Objective
Run the Simplex LP engine in Excel Solver on the Lucy's Cupcakes model to find the profit-maximising production plan and produce the Answer Report.

## You will build
The optimal plan X1=25, X2=37.5 giving Z=$162.50, plus a Solver Answer Report showing binding and non-binding constraints.
*Tools: Microsoft Excel, Solver add-in.*

## How the lab runs
1. **Set the objective** — Point Solver at the profit cell E6 and choose Max.
2. **Set changing cells** — The units C4:D4 are what Solver may vary.
3. **Add constraints** — E9:E12 ≤ G9:G12, and variables ≥ 0.
4. **Pick the engine** — Simplex LP — the model is linear.
5. **Solve & report** — Keep the solution and generate the Answer Report.

## Step-by-step (click-by-click)
1. **Load the Solver add-in**
   File → Options → Add-ins → Manage: Excel Add-ins → Go → tick 'Solver Add-in' → OK. Solver now appears on the Data tab.
2. **Open Solver**
   Data tab → Solver.
3. **Set the objective**
   Set Objective: $E$6. To: Max.
4. **Set the changing cells**
   By Changing Variable Cells: $C$4:$D$4.
5. **Add the resource constraints**
   Add → Cell Reference $E$9:$E$10 → <= → Constraint $G$9:$G$10 (baking powder and man-hours). OK.
6. **Add the demand constraints**
   Add → $E$11:$E$12 → <= → $G$11:$G$12 (vanilla and chocolate demand caps). OK.
7. **Force non-negativity**
   Tick 'Make Unconstrained Variables Non-Negative' — this is the X1,X2 ≥ 0 constraint.
8. **Choose Simplex LP**
   Select a Solving Method: Simplex LP (the model is linear).
9. **Solve**
   Click Solve. When 'Solver found a solution' appears, select Reports → Answer, then Keep Solver Solution → OK.
10. **Read the result**
   C4 shows 25 (vanilla), D4 shows 37.5 (chocolate), E6 shows 162.5 — the maximum profit.

## Expected outputs
- **X1 (Vanilla):** 25 units
- **X2 (Chocolate):** 37.5 units
- **Max profit Z:** $162.50
- **Binding:** Baking powder, Vanilla demand
- **Not binding:** Man-hours (slack 5), Chocolate demand (slack 22.5)

## Test it
The changing cells read X1=25 and X2=37.5, the objective E6 reads 162.5, and the Answer Report lists baking powder and vanilla-demand as Binding (slack 0) while man-hours and chocolate-demand are Not Binding (slack 5 and 22.5).

## If it doesn't work — diagnostics
- **Solver is not on the Data tab** → The add-in is not loaded — repeat the Add-ins step and tick 'Solver Add-in'.
- **'Solver could not find a feasible solution'** → A constraint is impossible or a sign is reversed. Check every LHS ≤ RHS and that the RHS limits are positive.
- **'The Objective Cell values do not converge' (unbounded)** → A binding resource constraint is missing, so profit can grow without limit. Add the omitted constraint.
- **Fractional answer 37.5 looks wrong** → LP allows divisible outputs; 37.5 batches is valid here. Add an integer constraint only if the product is truly indivisible.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
