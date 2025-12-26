<div align="center"> 
  <h2> Academic-English-Group-Paper </h2>
  <h1> From NeRFs to 3D Gaussians: A Survey on Dynamic Scene Modeling and Rendering </h1>
</div>

<img src="./doc/img/ouc.png" alt="ouc_alt" title="ouc_img">

<div align="center">
  <p>
    <strong>Yuwei Zhao</strong>, <strong>Kaiyuan Zhang</strong>, <strong>Yuxiang Liu</strong>, <br>
    <strong>Yilin Zhang</strong>, and <strong>Keqin Zhang</strong>
  </p>
  <p>
    <em>School of Computer Science and Technology, Ocean University of China (OUC)</em><br>
    <em>School of MPs & EPs, Heriot-Watt University (HWU)</em>
  </p>
</div>

<div align="center">

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](./report/paper.pdf)
![Latex](https://img.shields.io/badge/Latex-VScode-green)
[![License](https://img.shields.io/badge/License-Proprietary-lightgrey)](./LICENSE)

</div>

---

## 📖 Abstract

Dynamic scene modeling is a pivotal technology for emerging applications in the Metaverse, virtual reality, and free-viewpoint video. While **Neural Radiance Fields (NeRF)** have achieved photorealistic rendering, their application to dynamic scenes is hindered by slow training and inference speeds. Recently, **3D Gaussian Splatting (3DGS)** has emerged as a disruptive alternative, offering real-time rendering capabilities through explicit splatting.

In this survey, we provide a comprehensive review of the transition from implicit to explicit representations for dynamic scene modeling. We propose a structured taxonomy categorizing existing methods into four paradigms:

- **Implicit Deformation Fields** (e.g., D-NeRF)
- **Spacetime Neural Fields** (e.g., DyNeRF)
- **Hybrid Representations** (e.g., HexPlane)
- **Dynamic Gaussian Splatting** (e.g., 4D-GS)

Furthermore, we conduct a systematic comparative analysis based on reconstruction quality, training efficiency, and storage footprint. Finally, we discuss open challenges, including storage compression and integration with generative AI.

---

## 🗺️ Taxonomy & Evolution

Our survey categorizes the evolution of dynamic scene modeling into four main streams:

| Paradigm | Core Representation | Key Methods | Pros | Cons |
| :--- | :--- | :--- | :--- | :--- |
| **Implicit Deformation** | Canonical NeRF + Warp Field | D-NeRF, Nerfies, HyperNeRF | Low Storage (<5MB), High Fidelity | Slow Training, Slow Inference |
| **Spacetime Fields** | 4D Function $(x,y,z,t) \to c, \sigma$ | DyNeRF, Video-NeRF | Handles Topology Changes | "Curse of Dimensionality", Slow |
| **Hybrid Repr.** | Voxel/Hash/Plane + Tiny MLP | HexPlane, TiNeuVox, K-Planes | Fast Training (min), Compact | Limited Rendering Speed |
| **Dynamic 3DGS** | 4D Gaussians (Position/Rot/Scale) | 4D-GS, Deformable 3DGS | **Real-time (>80 FPS)**, High Fidelity | **Large Storage**, Floater Artifacts |

---

## 📊 Performance Benchmark

Quantitative comparison on the **D-NeRF Synthetic Dataset** ($800 \times 800$ resolution):

| Method | Class | PSNR $\uparrow$ | SSIM $\uparrow$ | FPS $\uparrow$ | Train Time $\downarrow$ | Storage (MB) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **D-NeRF** | Implicit | 30.31 | 0.96 | < 1 | ~ 2 days | **< 5** |
| **TiNeuVox** | Hybrid | 32.67 | 0.97 | 1.5 | 28 min | 48 |
| **HexPlane** | Hybrid | 31.04 | 0.97 | 2.5 | 11 min | 38 |
| **Deformable 3DGS** | Explicit | 33.07 | 0.98 | 45 | **< 10 min** | ~ 20 |
| **4D-GS** | Explicit | **34.05** | **0.98** | **82** | 8 min | 18 |

> **Insight:** While implicit methods excel in storage efficiency, explicit Gaussian-based methods demonstrate superior real-time performance suitable for VR/AR applications.

---

## 📂 Repository Structure

This repository contains the LaTeX source code and compiled resources for the survey paper.

```bash
Academic-English-Paper/
├── doc/                 # Paper Templates & References
│   ├── paper_references/
│   └── ...
├── report/              # LaTeX Source Code
│   ├── paper.tex        # Main document file
│   ├── reference.bib    # Bibliography (60+ citations)
│   └── img/             # Paper figures and charts
├── main.pdf             # Compiled PDF of the survey
├── LICENSE              # Usage terms
└── README.md            # Project documentation
```

---

## 🖊️ Citation

If you find this survey useful for your academic writing or research, please cite:

```
@article{stanley2025reconstruction,
  title={From NeRFs to 3D Gaussians: A Survey on Dynamic Scene Modeling and Rendering},
  author={Zhao, Yuwei and Zhang, Kaiyuan and Liu, Yuxiang and Zhang, Yilin and Zhang, Keqin},
  journal={Academic English Group Project, Ocean University of China},
  year={2025}
}
```

---

#### ⚠️ License: This project isn't open-source. See Details [LICENSE](./LICENSE).

---

<img src="./doc/img/ouc2.png" alt="ouc2_alt" title="ouc2_img">