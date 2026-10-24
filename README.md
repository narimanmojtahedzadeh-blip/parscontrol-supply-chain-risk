# parscontrol-supply-chain-risk
ower BI dashboard comparing Lean, Hybrid and Agile inventory policies under USD and gold shocks for an automotive electronics manufacturer. Interactive shock model, decision matrix and cost breakdown. SQL Server + DAX.

# ParsControl | Supply Chain Risk Under Currency Shocks

A four-page Power BI dashboard showing how USD and gold price swings raise operating costs for an automotive electronics manufacturer, and which inventory policy (Lean, Hybrid or Agile) limits the damage best.

## Problem
In 2026 the USD index rose about 114% and the gold index about 45%. Roughly 64% of raw materials are USD-linked and 40% gold-linked. Which inventory strategy keeps costs lowest when the exchange rate jumps?

## Dashboard pages
1. **Executive Overview** – fulfillment rate (94.76%), total stock, purchase cost change and monthly cost trend.
2. **Inflation & Cost Drivers** – USD and gold indices, material price changes, and actual purchase cost versus cost at base exchange rate.
3. **Agile vs Lean** – operating cost breakdown (holding, ordering, stoppage) plus target and safety stock per policy.
4. **Final Recommendation** – an interactive shock model with a USD shock slider (0–150%), a risk-elasticity slicer (100–300%), a cost-by-shock line chart, a cost breakdown, a decision matrix and an automatic verdict.

## Key finding
Lean is cheapest across the whole 0–150% shock range (about 2.09bn Toman with no shock, versus 2.85bn for Hybrid and 3.10bn for Agile), but it is the most exposed: at a 115% shock its cost rises 129%, against 80% for Hybrid and 77% for Agile. The gap between Lean and Hybrid narrows as the shock grows, so Lean works as the base policy and Hybrid as a hedge against severe shocks.

## Model logic
- Holding cost scales with the USD-linked share (64.33%).
- Ordering cost stays unchanged.
- Stoppage cost scales with shock × risk elasticity × safety-stock gap versus the best-covered policy.

## How to use
Open the .pbix file in Power BI Desktop, refresh the data from SQL Server, then move the shock and risk-elasticity sliders on page 4 to see the recommended policy change.

## Tech stack
SQL Server, Power BI Desktop, DAX.

## Repository structure
- `powerbi/` – the .pbix file
- `sql/` – table and data scripts
- `docs/` – proposal and page explanations
- `images/` – dashboard screenshots

## Limitations
Operating costs are simulated values, risk elasticity is not calibrated on real stoppage data, the shock covers USD only, and safety stock exists for five components.

## Author
[Your name]
