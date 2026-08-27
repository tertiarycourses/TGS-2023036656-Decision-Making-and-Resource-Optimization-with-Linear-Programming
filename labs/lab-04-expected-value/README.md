# Lab 4 — Expected Value, EVwPI and EVPI

**Topic:** 2  ·  **Maps to:** A4, A5, K2 — determine resource needs and monitor usage by ranking options on expected payoff

**Workbook:** `kazo_decision.xlsx`  ·  **Data:** `data/kazo_decision.csv`

## Objective
Build a decision table for KAZO's expansion choice, compute the Expected Value of each option, then find the Expected Value with Perfect Information and the Expected Value of Perfect Information.

## You will build
A formula-driven decision table that ranks three options by EV (best EV=$345k), and computes EVwPI=$365k and EVPI=$20k.
*Tools: Microsoft Excel.*

## How the lab runs
1. **Structure the decision** — Three options × three market states with probabilities 0.3 / 0.5 / 0.2.
2. **Enter the payoffs** — A payoff for every option-and-state combination.
3. **Compute EV per option** — EV = Σ probability × payoff, using SUMPRODUCT.
4. **Pick the best EV** — The highest EV is the recommended option (Option 2, $345k).
5. **Value information** — EVwPI takes the best payoff in each state; EVPI = EVwPI − best EV.

## Step-by-step (click-by-click)
1. **Open the workbook**
   Open labs/lab-04-expected-value/kazo_decision.xlsx → Decision sheet. Rows = Option 1/2/3, columns = Favourable / Neutral / Unfavourable.
2. **Enter the probabilities**
   In C4:E4 enter the state probabilities 0.3, 0.5, 0.2. In F4 enter =SUM(C4:E4) and confirm it equals 1.
3. **Enter the payoffs ($'000)**
   Option 1 row: 400, 360, 100. Option 2 row: 350, 380, 250. Option 3 row: 300, 390, 200.
4. **Compute EV for each option**
   In the EV column enter =SUMPRODUCT($C$4:$E$4,C6:E6) for Option 1 and copy down for Options 2 and 3.
5. **Identify the best option**
   Use =MAX(EV range) and =INDEX(...,MATCH(...)) to flag the highest EV — Option 2 at $345k.
6. **Compute the best payoff per state**
   In a 'best-in-state' row enter =MAX(C6:C8) for Favourable and copy across for Neutral and Unfavourable → 400, 390, 250.
7. **Compute EVwPI**
   EVwPI =SUMPRODUCT(C4:E4, best-in-state row) = 0.3·400 + 0.5·390 + 0.2·250 = 365.
8. **Compute EVPI**
   EVPI = EVwPI − best EV = 365 − 345 = 20. This is the most KAZO should pay for perfect market information.

## Expected outputs
- **EV Option 1:** $320k
- **EV Option 2:** $345k  ← choose
- **EV Option 3:** $325k
- **EVwPI:** $365k
- **EVPI:** $20k

## Test it
The EV column shows Option 1 = 320, Option 2 = 345, Option 3 = 325; the best-EV flag points to Option 2; EVwPI reads 365 and EVPI reads 20 (all in $'000).

## If it doesn't work — diagnostics
- **Probabilities do not sum to 1** → F4 must equal 1. A typo in C4:E4 skews every EV. Fix the probabilities first.
- **EV uses the wrong probability row** → Lock the probability range with $C$4:$E$4 so SUMPRODUCT always multiplies by the correct state probabilities.
- **EVPI comes out negative** → You subtracted in the wrong order or picked the wrong best EV. EVPI = EVwPI − best EV and is always ≥ 0.
- **EVwPI equals the best EV** → You averaged option rows instead of taking the best payoff in each state. Use MAX per column for the best-in-state row.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
