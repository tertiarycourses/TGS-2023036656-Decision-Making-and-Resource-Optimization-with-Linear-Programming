# Lab 6 — Weighted Scoring Board (MCDA)

**Topic:** 3  ·  **Maps to:** A7, K3 — propose improvements by ranking options against several weighted criteria

**Workbook:** `supplier_scoring.xlsx`  ·  **Data:** `data/supplier_scoring.csv`

## Objective
Rank three suppliers against five weighted criteria using a scoring board: weight each criterion, rate each supplier, and compute the weighted total score.

## You will build
A scoring board that ranks Supplier A (42) above B (41) and C (40), with a sensitivity check on the criterion weights.
*Tools: Microsoft Excel.*

## How the lab runs
1. **List criteria & weights** — Price, Quality, Lead time, Reliability, Support — weighted by importance.
2. **Rate each option** — Score every supplier 1-5 on each criterion.
3. **Weight the ratings** — Weighted cell = weight × rating.
4. **Total and rank** — Total score = Σ weight × rating; highest total wins.
5. **Sensitivity check** — Change a weight and see whether the ranking flips.

## Step-by-step (click-by-click)
1. **Open the workbook**
   Open labs/lab-06-scoring-board/supplier_scoring.xlsx → Scoring sheet.
2. **Enter the criterion weights**
   In the weight column enter Price 3, Quality 3, Lead time 2, Reliability 2, Support 1.
3. **Rate each supplier**
   Score 1 (poor) to 5 (excellent). Supplier A: 3,5,3,4,4. Supplier B: 5,3,4,3,3. Supplier C: 4,4,2,5,2.
4. **Compute the weighted total**
   Under each supplier enter =SUMPRODUCT($weights, ratings). A=42, B=41, C=40.
5. **Rank the options**
   Use =RANK or sort by total score. Supplier A ranks first.
6. **Run a weight sensitivity check**
   Raise the Price weight from 3 to 5 and watch the totals: the price-strong Supplier B can overtake A — showing how weight choices drive the result.
7. **Record the recommendation**
   Recommend Supplier A under the base weights, and note the weight at which the decision changes.

## Expected outputs
- **Supplier A total:** 42  ← rank 1
- **Supplier B total:** 41
- **Supplier C total:** 40
- **Sensitivity:** High Price weight favours B

## Test it
The weighted totals read Supplier A = 42, Supplier B = 41, Supplier C = 40, so Supplier A ranks first; raising the Price weight shifts the ranking toward Supplier B.

## If it doesn't work — diagnostics
- **All suppliers score the same** → The weights are all equal or all 1. Differentiate the weights to reflect real priorities.
- **Ratings on different scales** → Keep every criterion on the same 1-5 scale, or normalise first — mixing scales silently biases the total.
- **Ranking feels arbitrary** → Scores are close (42/41/40). That fragility is exactly why AHP's pairwise weighting is used next.
- **A 'lower is better' criterion inflates the score** → Reverse the scale for cost-type criteria (5 = cheapest) or the total rewards the wrong option.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
