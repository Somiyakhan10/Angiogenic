# Angiogenesis Gradient Simulator

**Computational Model of Competing Pro- and Anti-Angiogenic Signals**

[![Streamlit App](https://img.shields.io/badge/Streamlit-App-red)](https://huggingface.co/spaces/somiya-khan01/vessel-growth-dashboard)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📸 Dashboard Screenshots

### Full Dashboard Interface

![Dashboard Main View]
<img width="1861" height="669" alt="image" src="https://github.com/user-attachments/assets/ba4fa442-e2e6-4afa-91ff-baf29d35605d" />

*Complete web dashboard showing sidebar controls, metric cards, and interactive plots.*


### Metrics Display

<img width="1424" height="594" alt="image" src="https://github.com/user-attachments/assets/19ce0f71-97f0-4b9b-a211-6eafdb09710b" />


*Real-time metrics showing Balance Point, Vessel Front, Oxygen at Center, and Cell Survival.*

---

## 📊 Code Output Results

When the simulation runs, the following results are generated:

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
