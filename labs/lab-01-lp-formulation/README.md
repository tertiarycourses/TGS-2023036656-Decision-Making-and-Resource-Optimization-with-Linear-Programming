# Lab 1 — Formulate a Linear Programming Model

**Topic:** 1  ·  **Maps to:** A1, A3, K1 — develop an allocation strategy by translating a resource problem into an LP model

**Workbook:** `lucys_cupcakes.xlsx`  ·  **Data:** `data/lucys_cupcakes.csv`

## Objective
Turn Lucy's Cupcakes resource problem into a Linear Programming model: name the decision variables, write the profit objective, and express every resource limit as a linear constraint.

## You will build
A complete LP model (objective + four constraints) laid out on a formula-driven Excel worksheet, ready to solve.
*Tools: Microsoft Excel, lab CSV data.*

## How the lab runs
1. **Read the problem** — List products, profit per unit, and every scarce resource with its limit.
2. **Name variables** — Define X1, X2 — the units of each product to bake.
3. **Write the objective** — Max Z = 2·X1 + 3·X2 (total profit).
4. **Write constraints** — One linear inequality per resource and per demand cap.
5. **Lay out the sheet** — Coefficients, SUMPRODUCT for the objective and each constraint LHS.

## Step-by-step (click-by-click)
1. **Open the starter workbook**
   Open labs/lab-01-lp-formulation/lucys_cupcakes.xlsx and read the Problem sheet — 2 products, baking powder 10 kg, 10 man-hours, demand caps 25 and 60.
2. **Define the decision variables**
   In cells C4 and D4 (the yellow changing cells) enter a trial value of 0 for Vanilla (X1) and Chocolate (X2). These are what Solver will choose.
3. **Enter the profit coefficients**
   In C6 type 2 (profit per vanilla) and in D6 type 3 (profit per chocolate).
4. **Build the objective cell**
   In E6 enter =SUMPRODUCT(C6:D6,C4:D4). This computes total profit Z = 2·X1 + 3·X2.
5. **Enter the baking-powder constraint**
   Row 9: C9=0.1, D9=0.2; in E9 enter =SUMPRODUCT(C9:D9,$C$4:$D$4); G9=10 (kg available).
6. **Enter the man-hours constraint**
   Row 10: C10=0.05, D10=0.1; E10 =SUMPRODUCT(C10:D10,$C$4:$D$4); G10=10 (hours).
7. **Enter the demand constraints**
   Row 11 (Vanilla): C11=1, D11=0, E11 =SUMPRODUCT(...), G11=25. Row 12 (Chocolate): C12=0, D12=1, G12=60.
8. **Add a slack column**
   In H9:H12 enter =G9-E9 (drag down). Slack = limit − used; it shows spare capacity once the model is solved.

## Expected outputs
- **Objective form:** Max Z = 2·X1 + 3·X2
- **Baking powder:** 0.1·X1 + 0.2·X2 ≤ 10
- **Man-hours:** 0.05·X1 + 0.1·X2 ≤ 10
- **Demand:** X1 ≤ 25, X2 ≤ 60, X1,X2 ≥ 0

## Test it
The worksheet shows a single objective cell (E6) and four constraint LHS cells (E9:E12), each a SUMPRODUCT of coefficients and the changing cells. With X1=X2=0 the objective reads 0 and every constraint LHS reads 0.

## If it doesn't work — diagnostics
- **Objective is a fixed number, not a formula** → You typed the profit instead of =SUMPRODUCT(...). Solver can only optimise a cell that depends on the changing cells.
- **Constraint uses absolute vs relative refs wrongly** → Lock the changing cells with $C$4:$D$4 so the formula copies down correctly.
- **A resource limit is on the wrong side** → The limit (RHS) is a constant in column G; the used amount (LHS) is the SUMPRODUCT in column E. Do not swap them.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
