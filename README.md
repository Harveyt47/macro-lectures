# Macro lectures: Cass-Koopmans to HANK, and behavioural macro

Nine Jupyter notebooks, numbered in the order they are meant to be read. Each notebook runs on its own and is saved with its outputs, and each links to the others by filename, so keep the filenames as they are.

## Part A: Solving macro models with Newton's method (Lectures 1-5)

1. [`01_cass_koopmans_competitive_equilibrium.ipynb`](01_cass_koopmans_competitive_equilibrium.ipynb) - Cass-Koopmans planning problem and competitive equilibrium, solved as a stacked system with Newton's method; Part II solves the decentralised economy directly.
2. [`02_adjustment_costs.ipynb`](02_adjustment_costs.ipynb) - capital and labour adjustment costs with elastic labour supply, solved as a CGE-style price system and checked against the planner.
3. [`03_sticky_prices.ipynb`](03_sticky_prices.ipynb) - sticky prices, a natural-rate policy rule, markups, the output gap and a cost-push shock.
4. [`04_two_agent_new_keynesian.ipynb`](04_two_agent_new_keynesian.ipynb) - a two-agent (TANK) version with hand-to-mouth households: monetary transmission, distribution and the cost-push trade-off.
5. [`05_two_asset_hank.ipynb`](05_two_asset_hank.ipynb) - a two-asset HANK economy (liquid deposits, illiquid fund) solved with the sequence-space Jacobian (fake-news algorithm) and a quasi-Newton iteration.

## Part B: Behavioural macro (Lectures 6-9)

6. [`06_present_bias.ipynb`](06_present_bias.ipynb) - behavioural economics, quasi-hyperbolic discounting, and what present bias does to saving and capital in the Lecture 1 economy.
7. [`07_bayesian_overconfidence.ipynb`](07_bayesian_overconfidence.ipynb) - Bayes' rule as a benchmark; overprecision, asymmetric updating, estimating updating rules by maximum likelihood.
8. [`08_overconfident_firms.ipynb`](08_overconfident_firms.ipynb) - overconfident managers in the Lecture 2 investment model: boom, bust, and who loses.
9. [`09_overconfident_households.ipynb`](09_overconfident_households.ipynb) - overprecise households facing income risk in a one-asset HANK-style economy: precautionary saving, MPCs and welfare.

Dependencies between lectures: 1 -> 2 -> 3 -> 4 -> 5 is a chain. Lecture 6 needs Lecture 1 (and refers to 5 in its discussion). Lecture 7 follows 6. Lecture 8 needs 2 and 7. Lecture 9 needs 5 and 7.

## Running

```
pip install -r requirements.txt
jupyter lab
```

float64 is enabled inside each notebook.

`hank_ss_cache.npz` (created by Lecture 5 when it calibrates) stores the HANK calibration (discount factor and liquidity premium). Keep it next to Lecture 5 to skip the calibration step; delete it, or call `setup(..., recalibrate=True)`, to recalibrate (a couple of minutes on a laptop).

## Licence and attribution

Lecture 1 adapts QuantEcon's "Cass-Koopmans Competitive Equilibrium" by Thomas J. Sargent and John Stachurski, licensed CC BY-SA 4.0; the series is shared under the same licence ([CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)).

The Newton solver used throughout is adapted from QuantEcon's "Using Newton's Method to Solve Economic Models" (https://python.quantecon.org/newton_method.html), also licensed CC BY-SA 4.0.
