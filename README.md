# ⏚ Percolation Threshold Fitting Tool

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> **Live demo:** https://你的用户名.github.io/percolation-tool  
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

1. Open the [live demo](https://你的用户名.github.io/percolation-tool) or download `percolation_tool.html`
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


---

### Step 3：上传文件

在仓库主页点 `Add file` → `Upload files`，把以下文件拖进去：

| 文件 | 你在本地的路径 |
|------|---------------|
| 核心工具 | `G:\AcademicTools\percolation_tool.html` |
| 英文指南 | `G:\AcademicTools\tool-guide-en.md` （放到 `docs/` 目录） |

---

### Step 4：创建 LICENSE

`Add file` → `Create new file` → 文件名填 `LICENSE` → 粘贴：
MIT License

Copyright (c) 2025 你的名字

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

### Step 5：创建 CITATION.cff

`Create new file` → 文件名 `CITATION.cff`：

```yaml
cff-version: 1.2.0
message: "If you use this software, please cite it as below."
authors:
  - family-names: "你的姓"
    given-names: "你的名"
title: "Percolation Threshold Fitting Tool"
version: 1.0.0
date-released: 2025-06-01
url: "https://github.com/你的用户名/percolation-tool"
