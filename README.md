# Angiogenesis Gradient Simulator

**Computational Model of Competing Pro- and Anti-Angiogenic Signals for Tendon-Bone Interface Engineering**

[![Streamlit App](https://img.shields.io/badge/Streamlit-App-red)](https://huggingface.co/spaces/somiya-khan01/vessel-growth-dashboard)
[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-blue)](https://kaggle.com/your-notebook-link)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

---

## Table of Contents
1. [Overview](#overview)
2. [Dashboard Preview](#dashboard-preview)
3. [Model Description](#model-description)
4. [Interactive Controls](#interactive-controls)
5. [Output Results](#output-results)
6. [Code Output Example](#code-output-example)
7. [Quick Start](#quick-start)
8. [Deployment](#deployment)
9. [Citation](#citation)

---

## Overview

This interactive web application simulates how blood vessels respond to competing pro-angiogenic (VEGF) and anti-angiogenic (inhibitor) signals in a tissue engineering scaffold. The model demonstrates that vessels self-organize into a discrete band at the balance point where both signals are equal.

### Key Scientific Finding

Competing gradients cause vessels to form a **narrow, discrete band** at the exact point where VEGF equals inhibitor. This emergent patterning mechanism explains natural vascular organization in tendon-bone interfaces.

---

## Dashboard Preview

### Full Dashboard View

<img width="1478" height="649" alt="image" src="https://github.com/user-attachments/assets/a0f4beaf-8caa-46bf-a829-7ff14ab7ec26" />


*Complete dashboard showing sidebar controls, metric cards, and four interactive plots.*

### Sidebar Controls Panel

<img width="359" height="735" alt="image" src="https://github.com/user-attachments/assets/edabbbb8-cf92-4399-8ae3-a129f8e8e4b6" />


*Parameter control panel with sliders for VEGF strength, inhibitor strength, gradient steepness, migration speed, and simulation duration.*

---

## Model Description

### The Biological Problem

In tendon-bone interface healing, blood vessels must invade the scaffold to deliver oxygen, but excessive vascularization leads to scar tissue formation.

| Signal Type | Role | Spatial Distribution |
|-------------|------|---------------------|
| **VEGF** (Pro-angiogenic) | Attracts blood vessels | High at bone side (x=0), low at tendon side (x=10) |
| **Inhibitor** (Anti-angiogenic) | Repels blood vessels | Low at bone side (x=0), high at tendon side (x=10) |

### Mathematical Model

```python
# Signal Gradients
VEGF(x) = VEGF_max × exp(-steepness × x / L)
Inhibitor(x) = Inhibitor_max × (1 - exp(-steepness × x / L))
Net Signal(x) = VEGF(x) - Inhibitor(x)
Balance Point = x where Net Signal = 0

# Vessel Migration
Front(t+dt) = Front(t) + speed × dt
Stop when Front reaches Balance Point

# Oxygen Delivery
Oxygen(x) = 40 × Vessel Density(x)
Hypoxia threshold = 10 mmHg
