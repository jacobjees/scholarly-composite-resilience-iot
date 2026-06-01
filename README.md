# A Composite Resilience Framework for Consumer IoT: Quantifying Exposure, Detection, and Recovery Against Adaptive Adversaries

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status: pre-submission](https://img.shields.io/badge/status-pre--submission-orange.svg)]()

This repository contains the reproducible artifacts for the paper:

> **A Composite Resilience Framework for Consumer IoT: Quantifying Exposure, Detection, and Recovery Against Adaptive Adversaries**  
> Jeesmon Jacob (2026). Submitted to *IEEE Access*.

The work proposes a composite, normalized resilience score for consumer IoT ecosystems
that combines six dimensions — attack-surface exposure, adversary autonomy, defensive
control strength, detection responsiveness, recovery preparedness, and ecosystem
dependency — into a single device-level value in [0, 1]. The framework is empirically
validated on the public CICIoT2023 benchmark (46.78 million network flows, 33 attack
types) across three intrusion detectors and three defense profiles.

## Key results at a glance

| Defense profile | Composite resilience R_d (Random Forest) |
|---|---|
| Baseline (default OEM settings) | **0.400** |
| Hardened (patches + segmentation + auth) | **0.581** |
| Resilient (+ rollback, anomaly det., zero-trust) | **0.725** |

**Control-family ranking by marginal contribution to R_d** (ablation from HARDENED profile):

- **Segmentation**: +0.0583  *(NIST SP 800-207 §3.2, §3.4.1)*
- **Secure updates**: +0.0437  *(NIST SP 800-193 §4; OWASP IoT Top 10 A4)*
- **Recovery & rollback**: +0.0417  *(NIST SP 800-193 §4.4)*
- **Credential hardening**: +0.0396  *(NIST SP 800-207 §3.3; OWASP IoT Top 10 A1)*
- **Anomaly detection**: +0.0196  *(NIST SP 800-160 v2 §G.2)*

## Notebook viewers

GitHub sometimes fails to render large notebooks. Use these alternatives if needed:

| # | Notebook | Run in Colab | View on nbviewer |
|---|---|---|---|
| 00 | [Environment setup](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/00_environment_setup.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/00_environment_setup.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/00_environment_setup.ipynb) |
| 01 | [Drive mount & folder structure](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/01_drive_mount_and_folders.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/01_drive_mount_and_folders.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/01_drive_mount_and_folders.ipynb) |
| 02 | [Dataset extraction & verification](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/02_dataset_extraction_and_verification.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/02_dataset_extraction_and_verification.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/02_dataset_extraction_and_verification.ipynb) |
| 03 | [Dataset profiling (class distribution)](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/03_dataset_profiling.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/03_dataset_profiling.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/03_dataset_profiling.ipynb) |
| 04 | [Stratified 70/15/15 split](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/04_train_val_test_split.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/04_train_val_test_split.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/04_train_val_test_split.ipynb) |
| 05 | [Pillar 1: detection baseline (RF / XGB / MLP)](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/05_pillar1_detection_baseline.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/05_pillar1_detection_baseline.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/05_pillar1_detection_baseline.ipynb) |
| 06 | [Pillar 1: paper-ready tables and figures](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/06_pillar1_analysis_and_figures.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/06_pillar1_analysis_and_figures.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/06_pillar1_analysis_and_figures.ipynb) |
| 07 | [Pillar 2: composite resilience scoring](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/07_pillar2_resilience_components.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/07_pillar2_resilience_components.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/07_pillar2_resilience_components.ipynb) |
| 08 | [Pillar 3: control-family ablation](https://github.com/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/08_pillar3_control_ablation.ipynb) | [Open](https://colab.research.google.com/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/08_pillar3_control_ablation.ipynb) | [Open](https://nbviewer.org/github/jacobjees/scholarly-composite-resilience-iot/blob/main/notebooks/08_pillar3_control_ablation.ipynb) |

## Repository contents

```
.
├── notebooks/                    Jupyter notebooks for the full pipeline
├── results/                      Metrics, summaries, LaTeX tables
├── figures/                      Paper-ready PNG and PDF figures
└── docs/                         How to obtain CICIoT2023 (not redistributed)
```

## What is NOT in this repository

- **The CICIoT2023 dataset itself.** Distributed by the Canadian Institute for
  Cybersecurity under a request-and-accept license. We do not redistribute. See
  [`docs/DATA.md`](docs/DATA.md) for how to obtain it.
- **Processed train/val/test parquets** (~1.0 GB). Regenerable from notebook 04.
- **Trained model checkpoints** (~500 MB). Regenerable from notebook 05.

The numbers reported in the paper are fully reproducible from the dataset plus the
notebooks in this repository. The preserved notebook outputs (visible when you open
each `.ipynb`) provide a tamper-evident record of the original analysis run.

## How to reproduce

1. Obtain the dataset per `docs/DATA.md`.
2. Upload `CSV.zip` to your Google Drive at
   `MyDrive/composite_resilience_framework/data/raw/CSV.zip`.
3. Open notebook `00_environment_setup.ipynb` in Colab Pro+ and run it.
4. Run notebooks 01 through 08 in order.
5. Total runtime on Colab Pro+ A100: approximately 4-5 hours.

## Dataset citation

> E. C. P. Neto, S. Dadkhah, R. Ferreira, A. Zohourian, R. Lu, and A. A. Ghorbani,
> "CICIoT2023: A real-time dataset and benchmark for large-scale attacks in IoT
> environment," *Sensors*, vol. 23, no. 13, p. 5941, 2023.
> https://doi.org/10.3390/s23135941

Download (registration required): https://www.unb.ca/cic/datasets/iotdataset-2023.html

## Citation for this work

```bibtex
@article{jacob2026composite,
  title   = {A Composite Resilience Framework for Consumer IoT: Quantifying Exposure, Detection, and Recovery Against Adaptive Adversaries},
  author  = {Jeesmon Jacob},
  journal = {IEEE Access},
  year    = {2026},
  note    = {Submitted}
}
```

A machine-readable version is provided in [`CITATION.cff`](CITATION.cff).

## License

Released under the MIT License — see [`LICENSE`](LICENSE).
