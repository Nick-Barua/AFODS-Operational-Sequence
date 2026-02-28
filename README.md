# AFODS Operational Sequence Documentation

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue?style=flat-square)](https://opensource.org/licenses/Apache-2.0)
[![DOI: MDPI](https://img.shields.io/badge/DOI-10.3390%2Fvehicles7040149-blue?style=flat-square)](https://doi.org/10.3390/vehicles7040149)
[![Zenodo Figures](https://img.shields.io/badge/Zenodo-Figures-orange?style=flat-square)](https://doi.org/10.5281/zenodo.17621800)
[![Zenodo Video](https://img.shields.io/badge/Zenodo-Video_Demo-orange?style=flat-square)](https://doi.org/10.5281/zenodo.17460755)
[![ORCID](https://img.shields.io/badge/ORCID-0000--0003--4641--0112-A6CE39?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0000-0003-4641-0112)

> **Author:** Dr. Nick Barua · AN Holdings Co., Nishinomiya City, Hyogo, Japan
> **Part of:** [4-Paper Road Safety Research Program](#-related-publications)
> **Supporting:** [MDPI Vehicles 2025](https://doi.org/10.3390/vehicles7040149) · DOI: 10.3390/vehicles7040149

---

## 📌 Overview

This repository provides supplementary documentation and the core diagram for the **operational sequence of the Advanced Falling Object Detection System (AFODS)**, supporting the peer-reviewed manuscript:

> **Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans: Quantitative Evaluation for Enhanced Vehicle Safety**
> *Vehicles*, MDPI, 2025, 7(4), 149 · DOI: [10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149)

The **Graphical Abstract (GA)** and the **five-stage processing diagram** illustrate the advanced data processing pipeline designed for proactive threat detection — detailing the sequential flow from initial sensor data acquisition to the final decision and action stage.

---

## 🖼️ Five-Stage AFODS Pipeline
```
Stage 1: Sensor Data Acquisition
─────────────────────────────────
LWIR Thermal · NIR Stereo · Ultrasonic
         ↓
Stage 2: Multi-Modal Fusion
─────────────────────────────────
Weighted Detection Probability
Pd = w_LWIR · C_thermal + w_NIR · C_visual
         ↓
Stage 3: AI Detection & Classification
─────────────────────────────────
YOLOv7-Tiny (mAP@0.5: 91.3%)
Fall Velocity Estimation via NIR Stereo Disparity
MFCC Acoustic Signature Verification
         ↓
Stage 4: Predictive Kinematics
─────────────────────────────────
RNN + Kalman Filter State Estimation
Alert generated 0.3–0.8s before ground contact
         ↓
Stage 5: Decision & Action
─────────────────────────────────
SHAP Explainability · Forensic Audit Trail
ISO 26262 ASIL C-D Compliant Response
```

---

## 🔗 Repository Resources

| Resource | DOI / Link | Purpose |
| :--- | :--- | :--- |
| **Codebase** | [sensor-fusion-fall-detection](https://github.com/Nick-Barua/sensor-fusion-fall-detection) | All implementation scripts and models |
| **Video Demonstration** | [10.5281/zenodo.17460755](https://doi.org/10.5281/zenodo.17460755) | Real-time system performance demo |
| **Methodology Figures** | [10.5281/zenodo.17621800](https://doi.org/10.5281/zenodo.17621800) | Key diagrams and results charts |
| **Published Paper** | [10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149) | Full peer-reviewed methodology |

---

## 📊 Performance Summary

| Condition | TPR (%) | mAP@0.5 (%) | Latency (ms) |
| :--- | :---: | :---: | :---: |
| **Daytime, Clear** | 98.2 | 91.3 | 38 |
| **Night, Dry Road** | 95.6 | 88.7 | 42 |
| **Night, Rain** | 89.4 | 83.1 | 51 |
| *Baseline (Monocular, Night)* | *21.4* | *N/A* | *N/A* |

---

## 💡 How to Use

The flowchart and figures are intended for use in:
- Academic presentations and conference posters
- Technical documentation and reports
- Publications referencing the AFODS architecture
- ISO 26262 safety case documentation

---

## 🔗 Related Publications

This repository is **Part of** a unified 4-paper road safety research program:

| # | Title | Venue | Role |
| :---: | :--- | :---: | :--- |
| 1 | [Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans](https://doi.org/10.3390/vehicles7040149) | MDPI Vehicles | Technical foundation & benchmarks |
| 2 | [From Post-Mortem to Prevention: Redefining "Invisible" Pedestrians through ISO 26262 and Multi-Modal AI](https://doi.org/10.2139/ssrn.6305618) | SSRN | Problem framing & ISO 26262 compliance |
| 3 | [Integrated Safety Architectures: Leveraging Multi-Modal AI and ISO 26262 to Protect Vulnerable Road Users](https://ssrn.com/abstract=6112086) | SSRN | System-level VRU architecture |
| 4 | Sudden Incapacitation or Death at the Wheel: Unravelling the Predictors of Catastrophic Multi-Vehicle Collisions | SSRN *(pending)* | Epidemiological evidence for ADAS mandate |

---

## 📂 Related Repositories

- **[sensor-fusion-fall-detection](https://github.com/Nick-Barua/sensor-fusion-fall-detection)** — Core implementation of AFODS *(MDPI Vehicles, 2025)*
- **[From-Post-Mortem-to-Prevention-AFODS](https://github.com/Nick-Barua/From-Post-Mortem-to-Prevention-AFODS)** — ISO 26262-aligned conceptual framework

---

## 📝 Citation
```bibtex
@article{vehicles7040149,
  author    = {Barua, Nick and Hitosugi, Masahito},
  title     = {Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans:
               Quantitative Evaluation for Enhanced Vehicle Safety},
  journal   = {Vehicles},
  volume    = {7},
  number    = {4},
  pages     = {149},
  year      = {2025},
  doi       = {10.3390/vehicles7040149},
  url       = {https://doi.org/10.3390/vehicles7040149}
}
```

---

## 📜 License

This project is licensed under the **Apache 2.0 License** — see the [LICENSE](LICENSE) file for details.
