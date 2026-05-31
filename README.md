# AFODS Operational Sequence Documentation

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue?style=flat-square)](https://opensource.org/licenses/Apache-2.0)
[![DOI: MDPI](https://img.shields.io/badge/DOI-10.3390%2Fvehicles7040149-blue?style=flat-square)](https://doi.org/10.3390/vehicles7040149)
[![Zenodo Figures](https://img.shields.io/badge/Zenodo-Figures-orange?style=flat-square)](https://doi.org/10.5281/zenodo.17621800)
[![Zenodo Video](https://img.shields.io/badge/Zenodo-Video_Demo-orange?style=flat-square)](https://doi.org/10.5281/zenodo.17460755)
[![ISO 26262](https://img.shields.io/badge/Standard-ISO_26262_ASIL_B-red?style=flat-square)](https://www.iso.org/standard/43464.html)
[![Patent](https://img.shields.io/badge/Patent-JP_2025--167440-green?style=flat-square)]()
[![ORCID](https://img.shields.io/badge/ORCID-0000--0003--4641--0112-A6CE39?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0000-0003-4641-0112)

> **Authors:** Dr. Nick Barua · Prof. Masahito Hitosugi  
> Department of Legal Medicine, Shiga University of Medical Science, Otsu, Shiga, Japan  
> **Supporting:** [MDPI Vehicles 2025](https://doi.org/10.3390/vehicles7040149) · DOI: 10.3390/vehicles7040149  
> **Patent Filed:** Japanese Patent Application No. 2025-167440 (Filed: 3 October 2025)

---

## 📌 Overview

This repository provides supplementary documentation and the core diagram for the **operational sequence of the Advanced Falling Object Detection System (AFODS)**, supporting the peer-reviewed manuscript:

> **Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans: Quantitative Evaluation for Enhanced Vehicle Safety**  
> *Vehicles*, MDPI, 2025, 7(4), 149 · DOI: [10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149)

The **Graphical Abstract** and the **five-stage processing diagram** illustrate the advanced data processing pipeline designed for proactive threat detection — detailing the sequential flow from initial sensor data acquisition to the final decision and action stage. Validated across **320 controlled trials**, AFODS achieved **98.2% TPR at night (0 lux)**, where the baseline visible-spectrum system collapsed to 21.4%.

---

## 🖼️ Five-Stage AFODS Pipeline

| Stage | Name | Key Operations |
| :---: | :--- | :--- |
| **1** | **Acquisition & Preprocessing** | LWIR Thermal · NIR Stereo · Ultrasonic · Confidence-weighted fusion dynamically adjusts sensor trust based on environmental conditions |
| **2** | **Detection & Classification** | YOLOv7-Tiny (trained on 15,000+ images) · Hypothermia Detection Mode adjusts thermal threshold dynamically by ambient temperature |
| **3** | **Depth Estimation & Motion Analysis** | SGM stereo algorithm → dense disparity map · Lucas–Kanade optical flow → vertical motion tracking · Lightweight pose estimation distinguishes collapse from non-critical actions |
| **4** | **Predictive Threat Assessment** | GRU-based RNN analyses pose sequences over 1–2 s window · Detects pre-fall indicators (staggering, loss of balance) before collapse is complete |
| **5** | **Decision & Action** | TTC = D / v_vehicle · Braking triggered when TTC < 1.2 s AND confidence > 95% · Acoustic sensor as final corroborating factor · Target: ISO 26262 ASIL B · Mean latency: 46.3 ms (SD = 4.1 ms) |
---

## 🔗 Repository Resources

| Resource | DOI / Link | Purpose |
| :--- | :--- | :--- |
| **Primary Codebase** | [Advanced-Multi-Modal-Sensor-Fusion-System-for-Detecting-Falling-Humans](https://github.com/Nick-Barua/Advanced-Multi-Modal-Sensor-Fusion-System-for-Detecting-Falling-Humans) | Full system documentation, source code, and figures |
| **Sensor Fusion Code** | [AFODS-Sensor-Fusion-Code](https://github.com/Nick-Barua/AFODS-Sensor-Fusion-Code) | YOLOv7-Tiny and GRU model scripts |
| **Video Demonstration** | [10.5281/zenodo.17460755](https://doi.org/10.5281/zenodo.17460755) | Real-time system performance demo |
| **Methodology Figures** | [10.5281/zenodo.17621800](https://doi.org/10.5281/zenodo.17621800) | Key diagrams and results charts |
| **Published Paper** | [10.3390/vehicles7040149](https://doi.org/10.3390/vehicles7040149) | Full peer-reviewed methodology |

---

## 📊 Validated Performance (320 Controlled Trials)

All values are from the peer-reviewed publication (Tables 1 & 2). Each condition repeated 20 times using standardised ATDs at 20 m.

| Environmental Condition | AFODS TPR (%) | Baseline TPR (%) | p-value |
| :--- | :---: | :---: | :---: |
| **Clear Daylight** | **99.5** | 96.8 | 0.041 |
| **Night (0 lux)** | **98.2** | 21.4 | <0.001 |
| **Rain (50 mm/h)** | **96.4** | 55.7 | <0.001 |
| **Fog (<50 m visibility)** | **95.8** | 32.1 | <0.001 |

**Mean System Latency:** 46.3 ms (SD = 4.1 ms)  
**Mean Detection Range:** 41.5 m (SD = 4.8 m) vs. Baseline 22.3 m (SD = 12.5 m)  
**False Positive Rate:** AFODS avg. 1.6/24 h vs. Baseline avg. 32.2/24 h (95.0% reduction)

---

## 💡 How to Use

The flowchart and figures are intended for use in:

- Academic presentations and conference posters
- Technical documentation and reports
- Publications referencing the AFODS architecture
- ISO 26262 ASIL B safety case documentation

---

## 🔗 Related Publications

This repository is part of a unified research program on sensor fusion and road safety:

| # | Title | Venue | Role |
| :---: | :--- | :---: | :--- |
| **1** | [Advanced Multi-Modal Sensor Fusion System for Detecting Falling Humans](https://doi.org/10.3390/vehicles7040149) | MDPI Vehicles | Technical foundation & benchmarks |
| 2 | [Integrated Safety Architectures: Leveraging Multi-Modal AI and ISO 26262 to Protect Vulnerable Road Users](https://doi.org/10.2139/ssrn.6112086) | SSRN | System-level ISO 26262 safety architecture |
| 3 | [From Post-Mortem to Prevention: Redefining "Invisible" Pedestrians through ISO 26262 and Multi-Modal AI](https://doi.org/10.2139/ssrn.6305618) | SSRN | Problem framing & ISO 26262 compliance |
| 4 | [Sudden Incapacitation or Death at the Wheel: Probabilistic Risk Factors for Catastrophic Multi-Vehicle Collisions](https://doi.org/10.2139/ssrn.6305478) | SSRN | Epidemiological evidence for ADAS mandate |
| 5 | [The Invisible Victims of the Road: Why ADAS Cannot See the Pedestrians Most Likely to Die](https://doi.org/10.20944/preprints202604.0850.v1) | Preprints.org *(under review)* | AFODS forensic injury translation & regulatory advocacy |
| 6 | [A Physics-Grounded Multi-Modal Sensor Fusion Framework for Pedestrian Impact Kinematic Reconstruction Under Uncertainty: Phase 1 Design and Theoretical Evaluation](https://doi.org/10.3390/s26113387) | MDPI Sensors | Forensic reconstruction companion — retrospective kinematic reconstruction from post-impact scene observables |

---

## 📂 Related Repositories

- **[Advanced-Multi-Modal-Sensor-Fusion-System-for-Detecting-Falling-Humans](https://github.com/Nick-Barua/Advanced-Multi-Modal-Sensor-Fusion-System-for-Detecting-Falling-Humans)** — Primary repository with full system documentation and figures
- **[AFODS-Sensor-Fusion-Code](https://github.com/Nick-Barua/AFODS-Sensor-Fusion-Code)** — YOLOv7 and GRU model implementation scripts
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

The system described in this repository is subject to **Japanese Patent Application No. 2025-167440** (Filed: 3 October 2025).
