# ⏚ Percolation Threshold Fitting Tool

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> **Live demo:** https://xiaorehothot-lgtm.github.io/percolation-tool  
> **No installation required** — single HTML file, runs in any browser, works offline.

A browser-based interactive tool for determining the **percolation threshold (φc)**, **critical exponent (t)**, and **pre-factor (κ₀)** of conductive polymer composites from experimental conductivity vs. filler loading data.

---

## ✨ Features

- 🔍 **Automatic φc determination** — coarse grid scan + golden-section RSS minimization
- 📋 **One-click report export** — formatted output with LaTeX-ready equations
- 🔬 **Expert diagnostics** — RSS curvature analysis, t-exponent validation, R² plateau width
- 📉 **Residual diagnostics** — residuals vs. fitted values, physical plausibility checks
- 📊 **Multi-dataset comparison** — fit up to 4 datasets side-by-side with overlaid plots
- 💾 **CSV export** — download full candidate φc table
- 🎨 **Clean UI** — responsive, works on desktop and mobile

---

## 🚀 Quick Start

1. Open the [live demo](https://xiaorehothot-lgtm.github.io/percolation-tool) or download `percolation_tool.html`
2. Paste your **φ** (CNT loading, wt%) and **κ** (conductivity, S/m) — one value per line
3. Click **Start Fitting**
4. Example:
φ: 0.3 0.5 0.8 1.2 1.8 2.5 3.5
κ: 0.007 0.058 0.276 0.931 2.785 6.741 16.951

→ φc = 0.1491 wt%, t = 2.5067, κ₀ = 8.05×10⁻¹ S/m, R² = 0.99997

---

## 📐 Theory

The classical percolation power-law:

$$\kappa = \kappa_0 (\phi - \phi_c)^t \quad (\phi > \phi_c)$$

Linearized for fitting:

$$\ln(\kappa) = \ln(\kappa_0) + t \cdot \ln(\phi - \phi_c)$$

The tool uses **profile likelihood (concentrated least squares)**: for each candidate φc, the inner OLS problem has a closed-form solution. A golden-section search then refines φc to RSS minimum.



