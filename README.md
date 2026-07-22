# Analytical Signal Preprocessing Laboratory 🧪📊

![version](https://img.shields.io/badge/version-v0.3-blue)

This repository contains a single-file interactive digital laboratory dashboard designed to simulate and demonstrate the visual effects of chemometric preprocessing filters on various analytical chemistry signals.

It serves as an educational and prototyping tool for researchers, data scientists, and students working with spectroscopy, chromatography, and mass spectrometry data.

---

## 🆕 What's New in v0.3

- **Fixed:** Spectrum not refreshing when switching the analysis method. Previously, resetting the zoom/pan view *before* the new dataset was assigned caused the chart to stay locked to the previous signal's axis range. The reset now runs *after* the new data is rendered, so switching the analytical technique correctly redraws the spectrum and its axes every time.

## 🆕 What's New in v0.2

- **2 new preprocessing methods added:** Moving Average and BoxCar Average, alongside the existing Savitzky-Golay, SNV, Detrend/Phase Correction, and 1st/2nd Derivative filters.
- **Interactive zoom & pan added:** Drag over any region of the chart to zoom into it (magnifier cursor on hover), hold `Shift` and drag to pan, and use the **Reset Zoom** button to return to the full view.
- **Bilingual interface (TR/EN):** A language selector switches all labels, dropdown options, method descriptions, and chart axis titles between Turkish and English.

---

## 🚀 Key Features

- **Zero Installation:** Runs directly in any modern web browser (Chrome, Edge, Firefox, Safari) without requiring Python, R, or complex environments.
- **Multi-Technique Data Engine:** Simulates realistic, non-ideal pure signals for 8 distinct analytical methods.
- **Dynamic Artefact Injection:** Live control over high-frequency random noise and complex baseline drift/phase errors.
- **Real-time Preprocessing:** Instantaneous JavaScript implementation of industry-standard chemometric algorithms.
- **Interactive Zoom & Pan:** Drag-to-zoom into any region of the spectrum with a magnifier cursor, pan with `Shift`+drag, and reset with one click.
- **Bilingual UI:** Full Turkish / English language toggle for labels, options, descriptions, and axis titles.
- **High Performance:** Smooth rendering utilizing Chart.js with memory-efficient array structures.

---

## 🔬 Supported Analytical Techniques

The dashboard goes beyond simple synthetic inputs by accurately mimicking the unique physical axes and peak shapes of real laboratory instruments:

| Technique          | Peak Shape                         | Axis Properties                         | Primary Simulated Artefact                  |
| ------------------ | ----------------------------------- | ---------------------------------------- | -------------------------------------------- |
| **UV-Vis**         | Broad overlapping Gaussians        | $200 - 400 \text{ nm}$                  | Linear baseline drift                       |
| **Raman**          | Narrow scattering peaks            | $200 - 2000 \text{ cm}^{-1}$            | Intense exponential fluorescence background |
| **FTIR**           | Complex chemical footprints        | $4000 - 400 \text{ cm}^{-1}$ (Inverted) | S-shaped baseline distortion                |
| **ATR-FTIR**       | Wave-dependent penetration         | $4000 - 600 \text{ cm}^{-1}$ (Inverted) | Variable crystal contact scaling            |
| **¹H-NMR**         | Sharp Lorentzians with multipletes | $10 - 0 \text{ ppm}$ (Inverted)         | Phase errors (asymmetric dispersive peaks)  |
| **HPLC**           | Skewed (Asymmetric Tailing)        | $0 - 15 \text{ minutes}$                | Sinusoidal pump pulse / gradient ripple     |
| **GC-MS (TIC)**    | Asymmetric chromatographic bands   | $5 - 25 \text{ minutes}$                | Exponential temperature-driven column bleed |
| **Mass Spec (MS)** | Discrete, ultra-sharp ion lines    | $50 - 500 \text{ m/z}$                  | Vacuum background chemical noise            |

---

## 🛠️ Implemented Preprocessing Algorithms

1. **Savitzky-Golay Smoothing:** Polynomial local fitting that suppresses random high-frequency electronic noise while preserving genuine chemical peak heights.
2. **Moving Average:** A sliding-window arithmetic mean (selectable window size) that smooths random noise while keeping the same number of data points, at the cost of some peak sharpness.
3. **BoxCar Average:** Adjacent, non-overlapping points are summed and averaged, and the averaged value replaces every point within that block — producing the characteristic staircase-shaped noise reduction described in classical boxcar/gated-integration averaging.
4. **Standard Normal Variate (SNV):** Column-wise Z-score normalization that scales out physical variations like light scattering or variable crystal contact area.
5. **Iterative Baseline / Phase Correction:** An adaptive thresholding loop that dynamically maps the lower envelope of complex backgrounds (e.g., Raman fluorescence) to pull out buried signals.
6. **1st & 2nd Derivatives (SG-based):** Eliminates additive/linear drifts and resolves heavily overlapped peaks (shoulder bands) into clear, narrow valleys for enhanced resolution.

---

## 🔍 Chart Interaction

- **Zoom in:** Click and drag over any region of the spectrum (cursor shows a magnifier icon) to draw a selection box and zoom into it.
- **Pan:** Hold `Shift` and drag to move around the zoomed view.
- **Reset:** Click **Reset Zoom** (top-right of the chart) to return to the original view.
- Zoom automatically resets whenever the analytical technique (dataset) is changed.

---

## 🌐 Language Support

Use the **Dil / Language** selector above the analysis method dropdown to switch the entire interface — labels, dropdown options, method descriptions, and chart axis titles — between **Türkçe** and **English**.

---

## 👤 Author

**Fatih Mehmet AVCU**
📧 fatih.avcu@inonu.edu.tr

---

## About

No description, website, or topics provided.
