# Changelog

All notable changes to this project will be documented in this file.  
This project adheres to [Semantic Versioning](https://semver.org/).

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## [Unreleased]
- Planned improvements and future updates will be listed here.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## [v1.0.0] - 2025-10-30
### Added
- Initial public release of **YOLOv8l Baseline — VisDrone**.
- Included training notebook (`YOLOv8l Baseline.ipynb`) exactly as used in Colab Pro (High-RAM, A100 GPU).
- Added all outputs under `runs/yolov8_training/train/`:
  - Training curves (`results.png`)
  - Confusion matrices
  - Box precision/recall/F1/PR curves
  - Per-epoch metrics (`results.csv`)
  - Per-class AP values (`val_per_class_ap.csv`)
  - Frozen arguments (`args.yaml`)
- Exported model weights and formats (PT, ONNX, TorchScript, TensorRT, etc.) tracked via Git LFS.
- Inference results under `runs/yolov8_training/test_infer/`.
- Project governance files:
  - `LICENSE` (MIT)
  - `CONTRIBUTING.md`
  - `CODE_OF_CONDUCT.md`
  - `SECURITY.md`
  - `CITATION.cff`
- Repository hygiene:
  - `.gitignore`
  - `.gitattributes`
  - GitHub Actions workflow (`.github/workflows/smoke.yml`).

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## [v0.1.0] - 2025-10-25
### Added
- Internal project setup and initial experiments on VisDrone dataset.
- Drafted baseline training notebook and preliminary runs.
- Local results saved to Google Drive for replication.
