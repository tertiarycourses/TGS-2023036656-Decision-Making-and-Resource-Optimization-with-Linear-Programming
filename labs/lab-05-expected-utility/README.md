# Lab 5 — Risk and Expected Utility

**Topic:** 2  ·  **Maps to:** A6, K2 — review sufficiency and optimal utilisation when outcomes carry risk

**Workbook:** `risk_utility.xlsx`  ·  **Data:** `data/risk_utility.csv`

## Objective
Compare two resource-allocation projects with the SAME expected value but different risk, using a utility function to separate the risk-averse choice from a risk-neutral one, and quantify the risk premium.

## You will build
A utility table showing that with U(x)=√x the safer Project A (certainty equivalent $49.5k) beats the risky Project B ($40.0k) even though both have EV=$50k.
*Tools: Microsoft Excel.*

## How the lab runs
1. **Set up two projects** — Same EV=$50k: Project A pays 40 or 60; Project B pays 10 or 90 (each 50/50).
2. **Choose a utility function** — Risk-averse U(x)=√x maps money to satisfaction with diminishing returns.
3. **Compute expected utility** — EU = Σ probability × U(payoff) for each project.
4. **Find certainty equivalents** — CE = U⁻¹(EU): the guaranteed amount worth the same as the gamble.
5. **Read off risk** — Risk premium = EV − CE; the bigger the spread, the bigger the premium.

## Step-by-step (click-by-click)
1. **Open the workbook**
   Open labs/lab-05-expected-utility/risk_utility.xlsx → Utility sheet. Two projects, two equally likely outcomes each (probability 0.5).
2. **Enter the payoffs ($'000)**
   Project A: 40 and 60. Project B: 10 and 90. In the probability cells enter 0.5 for each outcome.
3. **Confirm equal EV**
   EV_A =SUMPRODUCT(prob,payoff_A)=50; EV_B =SUMPRODUCT(prob,payoff_B)=50. Both projects have the same expected value.
4. **Add a utility column**
   For each payoff x compute U=SQRT(x): √40=6.325, √60=7.746, √10=3.162, √90=9.487.
5. **Compute expected utility**
   EU_A =SUMPRODUCT(prob,U_A)=7.035; EU_B =SUMPRODUCT(prob,U_B)=6.325.
6. **Compute certainty equivalents**
   Invert the utility: CE = EU². CE_A =7.035^2 = 49.5; CE_B = 6.325^2 = 40.0.
7. **Compute the risk premium**
   Risk premium = EV − CE. Project A ≈ 0.5; Project B = 10.0 — the risky project's premium is far larger.
8. **Recommend**
   A risk-averse manager chooses Project A: same EV, higher certainty equivalent, lower risk premium.

## Expected outputs
- **EV (both):** $50k
- **EU Project A:** 7.035  → CE $49.5k
- **EU Project B:** 6.325  → CE $40.0k
- **Risk premium B:** $10k
- **Choice:** Project A (risk-averse)

## Test it
EV_A = EV_B = 50, but EU_A = 7.035 > EU_B = 6.325 and CE_A = 49.5 > CE_B = 40.0, so the risk-averse choice is Project A; Project B carries a $10k risk premium versus A's $0.5k.

## If it doesn't work — diagnostics
- **Both projects tie** → You compared EV, not expected utility. With equal EV the tie-break is EU / certainty equivalent, not EV.
- **Utility applied to the EV instead of each outcome** → Apply U(x) to every outcome first, then average — U(E[x]) ≠ E[U(x)] (that gap is exactly the risk premium).
- **Certainty equivalent exceeds EV** → For a risk-averse (concave) utility, CE ≤ EV always. A CE above EV means the inverse was applied wrongly.
- **Risk-seeking result** → √x is concave (risk-averse). A convex utility (e.g. x²) would flip the choice toward the risky project — pick the curve that matches the manager's attitude.

---
*WSQ Decision-Making and Resource Optimization with Linear Programming (TGS-2023036656) · Tertiary Infotech Academy Pte Ltd.*
