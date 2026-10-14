
## Run 2026-10-12T07:15:32+00:00 - OK
| code cell | wall time | status |
|---|---|---|
| 1 |    0.9s | ok |
| 2 |    0.0s | ok |
| 3 |    0.2s | ok |
| 4 |    2.0s | ok |
| 5 |    0.6s | ok |
| 6 |    3.5s | ok |
| 7 |   33.7s | ok |
| 8 |    1.3s | ok |
| 9 |    0.0s | ok |
| 10 |    0.0s | ok |

## Review notes on run 1 (kept on purpose; superseded outputs are in archive/run1_superseded/)
* **Wrong prose claim:** Part 3 markdown said the n=40 design has power "≈ 0.52"; the exact value computed in Part 4 is 0.424. Prose corrected; numbers in prose should be read from computed output.
* **Weak illustration:** the first replicate with naive p<0.01 (true Δ=0) was *also* significant under the cluster-aware test (p=0.0415), so that single example did NOT show a flipped verdict. Added the conditional frequency (share of naive "discoveries" that disappear under correct analysis) and a representative example chosen by a stated rule.
* **Surprising result flagged:** heavy-tailed scenario S1 showed higher power (0.588) than the normal baseline (0.414). Added a cross-check with scipy.stats.ttest_ind and a diagnostic (median sample SD) before interpreting.
* **Baseline Welch type-I = 0.040 (2000 reps, MCSE 0.004)** is 2.3 MCSE below 0.05, while the independent 4000-rep grid cell at n=40 gave 0.056. Treated as Monte-Carlo noise, not as evidence of conservativeness; not "fixed" by re-seeding.

## Run 2026-10-12T07:17:40+00:00 - OK
| code cell | wall time | status |
|---|---|---|
| 1 |    1.0s | ok |
| 2 |    0.0s | ok |
| 3 |    0.2s | ok |
| 4 |    1.7s | ok |
| 5 |    0.5s | ok |
| 6 |    3.3s | ok |
| 7 |   30.5s | ok |
| 8 |    0.9s | ok |
| 9 |    0.0s | ok |
| 10 |    0.0s | ok |

## Run 2026-10-12T07:21:36+00:00 - OK
| code cell | wall time | status |
|---|---|---|
| 1 |    1.0s | ok |
| 2 |    0.0s | ok |
| 3 |    0.2s | ok |
| 4 |    2.1s | ok |
| 5 |    0.5s | ok |
| 6 |    3.6s | ok |
| 7 |   31.3s | ok |
| 8 |    1.1s | ok |
| 9 |    0.0s | ok |
| 10 |    0.0s | ok |
