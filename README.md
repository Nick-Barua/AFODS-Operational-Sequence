# AFODS-Sensor-Fusion-Code: Reproducible Methodology (vehicles-3989222)

This repository contains the complete implementation scripts, configuration, and core logic for the **Advanced Falling Object Detection System (AFODS)**. It provides the necessary codebase to reproduce the quantitative results and methodology presented in the academic manuscript "Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans: Quantitative Evaluation for Enhanced Vehicle Safety."

## ⚙️ Core Methodology Code

The codebase supports the dual-model AI pipeline:
* **Detection Model:** YOLOv7-Tiny implementation scripts.
* **Proactive Model:** Gated Recurrent Unit (GRU) scripts for pose-sequence analysis.
* **Fusion Logic:** Scripts detailing the confidence-weighted sensor fusion pipeline.

## 🔗 Archival and Data Links

### Figures and Methodology Diagrams
The static figures and high-level diagrams (e.g., Data Processing Pipeline, TPR chart) are permanently archived on Zenodo:
* [10.5281/zenodo.17621800]

### Supplementary Video Demonstration
The video demonstrating the operational sequence is also archived:
* [10.5281/zenodo.17460755]

## 🛠️ How to Use (Reproducibility)
Clone the repository and follow the instructions in the `README.md` and the Wiki pages (e.g., **Validation Script Usage**) to set up the PyTorch environment and reproduce the validation metrics (TPR/FPR).

## 📚 How to Cite This Work
Please cite the published article when referencing this code or its methodology.
