# Valuation-to-Option Pricing Lab v2

This is an integrated analytical build:

- `valuation_option_lab.ipynb` performs the analysis and validation.
- The notebook writes `docs/model_results.json`.
- `docs/index.html` reads the generated JSON and renders the dashboard.
- GitHub Actions executes the notebook before every deployment.
- Deployment fails if the notebook fails or does not produce dashboard data.

## Publish
Upload all contents to the repository root, including `.github/workflows/deploy-pages.yml`. In repository Settings > Pages, select GitHub Actions.

## Extended analysis (v3)
- `docs/analysis.html` is a supplementary dashboard built from the same `docs/model_results.json` (new results live under the `extended` key, so `docs/index.html` is unchanged).
- New in the notebook: distribution diagnostics, an explicit DCF build from `data/dcf_inputs.csv`, scenario-weight sensitivity, a KDE-simulated belief value with a bootstrap interval, a Black-Scholes benchmark, implied volatility and mispricing metrics, sensitivity tables, maturity-alignment and model-risk flags, a source-documentation audit, and dated input snapshots in `docs/snapshots/`.
- `data/dcf_inputs.csv` ships with template assumptions. Replace them, and fill `source_url` and `retrieval_date` in `data/source_documentation.csv`, with researched values.
- Protected infrastructure (workflow, `requirements.txt`, CRR function, validation assertions, `docs/index.html`) is unchanged.
