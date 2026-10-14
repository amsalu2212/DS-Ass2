# Assignment 2 – Inference and Uncertainty

**Name:** Amsalu Tessema Adgeh  
**Student ID Number:** 2026A8000929002  
**Course/Assignment:** Data Science – Assignment 2  

## What this project does
It quantifies uncertainty for a two-arm mean difference by simulation, instead of reporting a point estimate alone:

1. **Pre-specification** of the question, estimand (Δ), hypotheses (H0: Δ = 0), and minimum meaningful effect (0.4 SD), committed before any results.
2. **Sampling distribution** of the estimator by simulation (20,000 replicates).
3. **Inference methods:** Welch interval/test, percentile bootstrap, permutation test.
4. **Power analysis** over sample size, noise and effect size (120 cells), checked against exact noncentral-t power.
5. **Counterexample:** cluster-randomised data analysed as if independent, plus heavy-tail and unequal-variance stress tests.

## Main results (all from the executed notebook)
- Simulated SE matches √(2/n); log-log slope −0.501 (theory −0.5).
- Worked example (n = 40 per arm): power 0.42; Welch 95% CI [0.023, 0.854].
- 80% power at the minimum meaningful effect needs **100 per arm**.
- Clustered data analysed as independent: false-positive rate **31.5%** (theory 30.8%); 85% of such "discoveries" disappear under a cluster-aware analysis.
- Negative results are reported, for example the cluster bootstrap stays liberal with 6 clusters per arm (10.2%), and the permutation test is invalid for means under unequal variances and sizes (35%).

## Repository contents
| Path | Purpose |
|---|---|
| `PREREGISTRATION.md` | Question, estimand, hypotheses, MME, simulation budget (first commit, before results) |
| `inference_uncertainty.ipynb` | Executable notebook with stored outputs (source: `inference_uncertainty.py`) |
| `Assignment2_Inference_Uncertainty.pdf` / `.docx` | Written report: method note, figures, counterexample, verification |
| `results/` | `seeds.json`, `summary.json`, `power_grid.csv`, `scenario_matrix.csv`, `sampling_distribution.csv`, `verification_checks.csv`, `manifest_sha256.json` |
| `figures/` | Sampling distribution, intervals, power, counterexample |
| `AI_USE_LOG.md` | AI tool/task disclosure, accepted and rejected advice, verification |
| `SUBMISSION_SUMMARY.md` | 150–300-word summary for the platform |
| `RUN_LOG.md`, `archive/` | Every run, including the flawed first run and the problems found in it |
| `tools/` | Notebook runner and report builders |
| `requirements.txt` | Pinned dependencies |

## How to reproduce
```bash
python -m venv .venv && source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute inference_uncertainty.ipynb   # about 2–3 minutes
```
- **Seeds:** one master seed (20261012) split into independent streams with `SeedSequence.spawn` (see `results/seeds.json`).
- **Data:** none external. All data are simulated (generator version `dgp-v1`, defined in the notebook).
- **Environment used for the stored results:** Python 3.12.3, NumPy 2.4.4, SciPy 1.17.1, pandas 3.0.2, matplotlib 3.10.8.
- Compare your results with the stored ones using tolerances, not the last digit, because random streams can differ slightly across NumPy versions.

## Honest provenance notes
- The stored outputs were produced in a sandbox without Jupyter, using `tools/run_notebook.py`, which runs the cells top to bottom and stores real outputs. Running with `nbconvert` has [not yet been tested / been tested by me on (date) with result: ____].
- The report uses a Times-compatible font (Liberation Serif) in the PDF; the Word file uses Times New Roman.
- The verification checks were written by the same AI that wrote the code (see `AI_USE_LOG.md`).
- All conclusions apply to the simulated settings only. No real data were analysed, and no credentials or personal data are stored.