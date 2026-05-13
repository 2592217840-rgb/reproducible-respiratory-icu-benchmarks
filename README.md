# COPD/AECOPD respiratory ICU benchmark audit

This repository accompanies the manuscript:

**Toward reproducible respiratory ICU prediction benchmarks in COPD/AECOPD: auditing predictor admissibility, leakage, and target-population shift across MIMIC-IV and eICU**

It contains the code and public materials used for the MIMIC-IV to eICU audit. Patient-level data are not included. Credentialed users can use the scripts and manifests here to rerun the workflow after obtaining local MIMIC-IV and eICU access.

## Purpose

The study checks whether a respiratory ICU prediction task can be reconstructed from the reported cohort rules, endpoints, 12-hour landmark, predictor windows, proxy-variable handling, ABG complete-case rule, and cross-database endpoint notes. The repository keeps those rules visible alongside the aggregate results.

## What is included

- `protocol/`: protocol, task specifications, and statistical analysis plan.
- `scripts/`: cohort, outcome, feature, model, evaluation, bootstrap, literature-audit, and figure/table scripts.
- `metadata/`: cohort definitions, predictor provenance files, audit taxonomy, A3c subtype rules, endpoint notes, and extraction templates.
- `aggregate_outputs/`: result tables without patient-level rows.
- `figures/`: manuscript SVG figures.
- `figure_source_data/`: source tables used to draw figures, with no patient identifiers.
- `public_release/`: schemas, synthetic mock examples, and release checks.
- `submission_assets/`: polished main tables, figures, and supplementary table workbook.

## What is not included

This repository does not include:

- raw MIMIC-IV data;
- raw eICU-CRD data;
- patient-level intermediate extracts;
- patient-level feature matrices;
- patient-level predictions;
- row-level files derived from restricted clinical databases.

Credentialed users must obtain MIMIC-IV and eICU-CRD through PhysioNet and run the workflow locally under the applicable data-use agreements.

## Data access

MIMIC-IV and eICU-CRD are available to credentialed users through PhysioNet. Copy `dataset_paths_template.yaml` to a local path file that is not committed, then enter the local database locations.

## Quick start

```bash
conda env create -f environment.yml
conda activate copd-respiratory-bias-audit
python scripts/00_environment/check_readiness.py
```

Review `analysis_manifest.yml` for the run order. The workflow requires local MIMIC-IV and eICU-CRD access.

## Data boundary

This repository is enough to inspect the task definitions, predictor rules, aggregate outputs, and figure source data. It is not enough to regenerate patient-level cohorts or predictions without the restricted databases.

## Citation

If using this repository, cite the accompanying manuscript and this archived repository release.
