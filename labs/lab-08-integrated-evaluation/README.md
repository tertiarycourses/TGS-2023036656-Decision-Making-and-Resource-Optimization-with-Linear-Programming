# Lab 8 — Integrated Resource-Allocation Evaluation & KPIs

**Topic:** 3  ·  **Maps to:** A8, A9, K3 — synthesise a defensible ranking and convert the criteria weights into resource-management KPIs

**Workbook:** `integrated_eval.xlsx`  ·  **Data:** `data/integrated_eval.csv`

## Objective
Combine the AHP criteria priorities with per-criterion scores for three resource-allocation plans to produce a final synthesised ranking, then turn the criteria weights into monitoring KPIs.

## You will build
A synthesis table ranking Plan P (0.393) above Plan R (0.309) and Plan Q (0.299), plus a KPI dashboard weighting Cost 40%, Flexibility 30%, Delivery 22%, Quality 8%.
*Tools: Microsoft Excel.*

## How the lab runs
1. **Bring in criteria weights** — Reuse the AHP priorities: Cost 0.398, Quality 0.085, Delivery 0.218, Flexibility 0.299.
2. **Score plans per criterion** — Normalised local scores for Plans P, Q, R on each criterion (each column sums to 1).
3. **Synthesise** — Global score = Σ criteria weight × local score.
4. **Rank the plans** — Highest global score is the recommended allocation (Plan P).
5. **Set KPIs** — Reuse the criteria weights as the weights of the monitoring KPIs.

## Step-by-step (click-by-click)
1. **Open the workbook**
   Open labs/lab-08-integrated-evaluation/integrated_eval.xlsx → Synthesis sheet.
2. **Enter the criteria weights**
   From Lab 7: Cost 0.398, Quality 0.085, Delivery 0.218, Flexibility 0.299 in the weight row.
3. **Enter the local scores**
   For each criterion, the normalised scores of Plans P/Q/R (each criterion column sums to 1). Cost: 0.54/0.30/0.16; Quality: 0.16/0.54/0.30; Delivery: 0.30/0.16/0.54; Flexibility: 0.33/0.33/0.34.
4. **Synthesise each plan**
   Global score =SUMPRODUCT(criteria weights, plan's local scores): P=0.393, Q=0.299, R=0.309.
5. **Rank and recommend**
   Plan P ranks first (0.393). Confirm the three global scores sum to ~1.00.
6. **Build the KPI dashboard**
   Convert the criteria priorities to KPI weights (Cost 40%, Flexibility 30%, Delivery 22%, Quality 8%) and list a measurable KPI for each: cost variance, on-time delivery %, utilisation %, defect rate.
7. **Add a monitor & review note**
   State the review cadence (e.g. monthly) and the threshold that would trigger a re-allocation — closing the plan-monitor-review loop (A5, A6, A8).

## Expected outputs
- **Global — Plan P:** 0.393  ← rank 1
- **Global — Plan R:** 0.309
- **Global — Plan Q:** 0.299
- **KPI weights:** Cost 40% · Flex 30% · Delivery 22% · Quality 8%
- **Loop:** Plan → monitor → review → re-allocate

## Test it
The synthesis table ranks Plan P = 0.393 first, then Plan R = 0.309 and Plan Q = 0.299 (sum ≈ 1.000); the KPI dashboard carries the AHP-derived weights (Cost 40%, Flexibility 30%, Delivery 22%, Quality 8%) each mapped to a measurable KPI.

## If it doesn't work — diagnostics
- **Global scores do not sum to ~1** → Either the criteria weights or a local-score column does not sum to 1. Re-normalise before synthesising.
- **A plan wins on one criterion but loses overall** → That is correct behaviour — synthesis balances all criteria by weight, not a single strength.
- **KPI weights ignore AHP** → Derive KPI weights from the AHP priorities so monitoring reflects the same priorities used to choose the plan.
- **No trigger threshold set** → A KPI without a threshold cannot prompt review. Define the value that forces re-allocation (A8).

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
