# Analytical Signal Preprocessing Laboratory 🧪📊

This repository contains a single-file interactive digital laboratory dashboard designed to simulate and demonstrate the visual effects of chemometric preprocessing filters on various analytical chemistry signals. 

It serves as an educational and prototyping tool for researchers, data scientists, and students working with spectroscopy, chromatography, and mass spectrometry data.

---

## 🚀 Key Features

* **Zero Installation:** Runs directly in any modern web browser (Chrome, Edge, Firefox, Safari) without requiring Python, R, or complex environments.
* **Multi-Technique Data Engine:** Simulates realistic, non-ideal pure signals for 8 distinct analytical methods.
* **Dynamic Artefact Injection:** Live control over high-frequency random noise and complex baseline drift/phase errors.
* **Real-time Preprocessing:** Instantaneous JavaScript implementation of industry-standard chemometric algorithms.
* **High Performance:** Smooth rendering utilizing Chart.js with memory-efficient array structures.

---

## 🔬 Supported Analytical Techniques

The dashboard goes beyond simple synthetic inputs by accurately mimicking the unique physical axes and peak shapes of real laboratory instruments:

| Technique | Peak Shape | Axis Properties | Primary Simulated Artefact |
| :--- | :--- | :--- | :--- |
| **UV-Vis** | Broad overlapping Gaussians | $200 - 400 \text{ nm}$ | Linear baseline drift |
| **Raman** | Narrow scattering peaks | $200 - 2000 \text{ cm}^{-1}$ | Intense exponential fluorescence background |
| **FTIR** | Complex chemical footprints | $4000 - 400 \text{ cm}^{-1}$ (Inverted) | S-shaped baseline distortion |
| **ATR-FTIR** | Wave-dependent penetration | $4000 - 600 \text{ cm}^{-1}$ (Inverted) | Variable crystal contact scaling |
| **¹H-NMR** | Sharp Lorentzians with multipletes | $10 - 0 \text{ ppm}$ (Inverted) | Phase errors (asymmetric dispersive peaks) |
| **HPLC** | sa-Skewed (Asymmetric Tailing) | $0 - 15 \text{ minutes}$ | Sinusoidal pump pulse / gradient ripple |
| **GC-MS (TIC)** | Asymmetric chromatographic bands | $5 - 25 \text{ minutes}$ | Exponential temperature-driven column bleed |
| **Mass Spec (MS)** | Discrete, ultra-sharp ion lines | $50 - 500 \text{ m/z}$ | Vacuum background chemical noise |

---

## 🛠️ Implemented Preprocessing Algorithms

1. **Savitzky-Golay Smoothing:** Polynomial local fitting that suppresses random high-frequency electronic noise while preserving genuine chemical peak heights.
2. **Standard Normal Variate (SNV):** Column-wise Z-score normalization that scales out physical variations like light scattering or variable crystal contact area.
3. **Iterative Baseline / Phase Correction:** An adaptive thresholding loop that dynamically maps the lower envelope of complex backgrounds (e.g., Raman fluorescence) to pull out buried signals.
4. **1st & 2nd Derivatives (SG-based):** Eliminates additive/linear drifts and resolves heavily overlapped peaks (shoulder bands) into clear, narrow valleys for enhanced resolution.

---
