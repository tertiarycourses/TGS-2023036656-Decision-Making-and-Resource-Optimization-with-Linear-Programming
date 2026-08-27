# Lab 7 — AHP — Criteria Priorities and Consistency

**Topic:** 3  ·  **Maps to:** A8, K3 — refine the plan by deriving defensible criteria weights and checking their consistency

**Workbook:** `ahp_criteria.xlsx`  ·  **Data:** `data/ahp_criteria.csv`

## Objective
Use the Analytic Hierarchy Process to weight four resource-management criteria by pairwise comparison on Saaty's 1-9 scale, derive priority weights, and verify judgement consistency with the Consistency Ratio.

## You will build
Criteria priorities Cost 0.398, Quality 0.085, Delivery 0.218, Flexibility 0.299, with lambda_max=4.185, CI=0.062 and CR=0.068 (consistent).
*Tools: Microsoft Excel.*

## How the lab runs
1. **Build the pairwise matrix** — Compare each pair of criteria on the 1-9 scale; reciprocals fill the lower triangle.
2. **Normalise the columns** — Divide each cell by its column total.
3. **Derive priorities** — Priority of a criterion = the average of its normalised row.
4. **Compute lambda_max** — Weighted-sum vector ÷ priorities, averaged.
5. **Check consistency** — CR = CI/RI must be ≤ 0.10 to accept the weights.

## Step-by-step (click-by-click)
1. **Open the workbook**
   Open labs/lab-07-ahp-consistency/ahp_criteria.xlsx → Pairwise sheet. Criteria order: Cost, Quality, Delivery, Flexibility.
2. **Enter the pairwise judgements**
   Upper triangle: Cost vs Quality=3, Cost vs Delivery=2, Cost vs Flexibility=2, Quality vs Delivery=1/4, Quality vs Flexibility=1/4, Delivery vs Flexibility=1/2. Diagonal = 1.
3. **Fill the reciprocals**
   Lower triangle = 1/upper (e.g. Quality vs Cost =1/3). Use =1/cell so the matrix stays reciprocal.
4. **Sum each column**
   In the totals row enter =SUM(column). Totals: 2.333, 12, 5.25, 3.75.
5. **Normalise the matrix**
   In a second block divide each cell by its column total (=cell/column_total).
6. **Derive the priority vector**
   Priority =AVERAGE(normalised row): Cost 0.398, Quality 0.085, Delivery 0.218, Flexibility 0.299 (they sum to 1).
7. **Compute the weighted-sum vector**
   Multiply the ORIGINAL matrix by the priority vector (=MMULT) to get the weighted sum for each criterion.
8. **Compute lambda_max**
   Divide each weighted-sum entry by its priority and average: lambda_max = 4.185.
9. **Compute CI and CR**
   CI = (lambda_max − n)/(n − 1) = (4.185 − 4)/3 = 0.062. With RI(4)=0.90, CR = CI/RI = 0.068.
10. **Accept or revise**
   CR = 0.068 ≤ 0.10, so the judgements are consistent and the weights are accepted.

## Expected outputs
- **Priority — Cost:** 0.398
- **Priority — Quality:** 0.085
- **Priority — Delivery:** 0.218
- **Priority — Flexibility:** 0.299
- **lambda_max / CI / CR:** 4.185 / 0.062 / 0.068 ✓

## Test it
The priority vector reads Cost 0.398, Quality 0.085, Delivery 0.218, Flexibility 0.299 (sum 1.000); lambda_max = 4.185, CI = 0.062, CR = 0.068 which is ≤ 0.10, so the criteria weights are consistent and usable.

## If it doesn't work — diagnostics
- **Priorities do not sum to 1** → You averaged the raw matrix, not the column-normalised matrix. Normalise each column first, then average the rows.
- **CR is above 0.10** → Judgements conflict (e.g. A≫B, B≫C but A≈C). Revisit the largest inconsistency and re-judge that pair.
- **Matrix is not reciprocal** → Every lower-triangle cell must be 1/(its mirror). Enter reciprocals with =1/cell, never by hand.
- **Wrong RI used** → RI depends on n: RI(3)=0.58, RI(4)=0.90, RI(5)=1.12. Using the wrong RI makes CR meaningless.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
