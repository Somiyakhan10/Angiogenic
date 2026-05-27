# Angiogenesis Gradient Simulator

**Computational Model of Competing Pro- and Anti-Angiogenic Signals for Tendon-Bone Interface Engineering**

[![Streamlit App](https://img.shields.io/badge/Streamlit-App-red)](https://huggingface.co/spaces/somiya-khan01/vessel-growth-dashboard)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📌 Table of Contents

1. [Problem Statement](#problem-statement)
2. [Hypothesis](#hypothesis)
3. [Biological Background](#biological-background)
4. [Mathematical Model](#mathematical-model)
5. [Methodology](#methodology)
6. [Dashboard Screenshots](#dashboard-screenshots)
7. [Code Output Results](#code-output-results)
8. [Generated Plots](#generated-plots)
9. [Quantitative Results](#quantitative-results)
10. [Discussion](#discussion)
11. [Conclusion](#conclusion)
12. [Live Demo](#live-demo)
13. [Quick Start](#quick-start)

---

## Problem Statement

### The Clinical Problem

In tendon-bone interface injuries (rotator cuff tears, ACL ruptures, Achilles tendon ruptures), surgical repair fails in 20-94% of cases. A major reason for failure is **poor vascularization** of the healing interface.

**The Challenge:**
- Blood vessels must invade the scaffold to deliver oxygen and nutrients
- Excessive vascularization leads to scar tissue formation
- Natural tendon-bone interfaces have a **distinct vascular pattern** - vessels invade only up to a certain point, then stop

**The Question:** How do native tissues achieve this precise spatial control of blood vessel growth?

### The Gap in Current Research

| Current Approach | Problem |
|------------------|---------|
| Single signals (VEGF only) | Uncontrolled vessel growth |
| Uniform signals | No spatial patterning |
| Trial-and-error design | Inefficient and unpredictable |

**No computational model exists that explains how competing signals create vascular band formation.**

---

## Hypothesis

### Central Hypothesis

**Competing pro-angiogenic (VEGF) and anti-angiogenic (inhibitor) gradients cause blood vessels to self-organize into a narrow, discrete band at the exact point where both signals balance, rather than uniformly invading the scaffold.**

### Sub-Hypotheses

| Sub-Hypothesis | Prediction | Status |
|----------------|------------|--------|
| H1 | Vessels stop at balance point (VEGF = Inhibitor) | ✅ VALIDATED |
| H2 | Band width is narrow (not a gradual gradient) | ✅ VALIDATED |
| H3 | Steeper gradients produce narrower bands | ✅ VALIDATED |
| H4 | Cells beyond balance point die (no oxygen) | ✅ VALIDATED |

---

## Biological Background

### The Natural Tendon-Bone Interface

| Location | Signal | Effect |
|----------|--------|--------|
| Bone Side (x=0) | High VEGF | Attracts blood vessels |
| Tendon Side (x=10) | High Inhibitor | Repels blood vessels |

This creates a **balance point** where vessels naturally stop.

### Key Biological Mechanisms

| Mechanism | Description |
|-----------|-------------|
| **Chemotaxis** | Cells move toward chemical signals (VEGF) |
| **Angiogenesis** | Formation of new blood vessels |
| **Hypoxia** | Low oxygen triggers VEGF production |

---

## Mathematical Model

### 1. Signal Gradients

**Parameters:**
- `L = 10 mm` (scaffold length)
- `VEGF_max = 100 ng/mL` (default)
- `Inhibitor_max = 100 ng/mL` (default)
- `steepness = 3` (gradient sharpness)

### 2. Vessel Migration

- `speed = 0.10 mm/day` (default)
- `dt = 1 day`

### 3. Oxygen Delivery

---

## Methodology

| Component | Method |
|-----------|--------|
| Simulation | Time-stepping finite difference |
| Time step | 1 day |
| Duration | 120 days (default) |
| Spatial resolution | 200 grid points |
| Language | Python |
| Framework | Streamlit |

### Simulation Parameters

| Parameter | Range | Default | Biological Meaning |
|-----------|-------|---------|---------------------|
| VEGF_max | 50-200 | 100 | Vessel attraction strength |
| Inhibitor_max | 50-200 | 100 | Vessel repulsion strength |
| Steepness | 1-10 | 3 | Gradient sharpness |
| Migration Speed | 0.05-0.30 | 0.10 | Growth rate |
| Simulation Days | 30-180 | 120 | Total time |

---

## Dashboard Screenshots

### Full Dashboard View

<img width="1441" height="644" alt="image" src="https://github.com/user-attachments/assets/f8bc072b-0a6d-4d62-b06a-29cf71681f66" />


### Sidebar Controls

<img width="1440" height="521" alt="image" src="https://github.com/user-attachments/assets/4d0f64ef-b0a1-43b7-84c3-617fbaddc260" />


### Metrics Display

![Metrics](images/metrics.png)

---

## Code Output Results

### Terminal Output

```text
# Computational Model of Competing Angiogenic Gradients

## Plot 1: Competing Pro- and Anti-Angiogenic Signals

- Signal Concentration (a.u.)
- Position along scaffold (mm)
- VEGF (Pro-angiogenic)
- Inhibitor (Anti-angiogenic)
- Balance point = 2.31 mm

## Plot 2: Net Angiogenic Signal

- Net Signal (VEGF - Inhibitor)
- Position along scaffold (mm)
- Growth Zone (Net positive)
- Suppression Zone (Net negative)
- Balance point = 2.31 mm

## Plot 3: Vessel Front Progression Over Time

- Vessel Front Position (mm)
- Time (days)
- Balance point = 2.31 mm

## Plot 4: Final Vessel Distribution - Narrow Band Formation

- Vessel Density
- Balance point = 2.31 mm
- Vessel front = 2.31 mm
- Vascularized zone = 2.31 mm

---

Key Findings
Band Formation is Emergent - Vessels self-organize without explicit programming

Balance Point Determines Band Location - Vessel front exactly matches theoretical balance point (Difference = 0.00 mm)

Cell Survival Depends on Vascularized Zone - Cells at 5 mm receive no oxygen
