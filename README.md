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


### Dasboard

<img width="1428" height="554" alt="image" src="https://github.com/user-attachments/assets/d14940cd-b61f-409e-a1fa-edcbdf2be237" />



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

Plot 1: Competing Pro- and Anti-Angiogenic Signals
<img width="529" height="358" alt="image" src="https://github.com/user-attachments/assets/f953fc23-9324-41c3-8c10-66b15423c8b9" />


VEGF (blue) attracts vessels from bone side. Inhibitor (red) repels vessels from tendon side. Balance point at 2.31 mm.

Plot 2: Net Angiogenic Signal
<img width="539" height="359" alt="image" src="https://github.com/user-attachments/assets/9d63560f-414e-4830-8621-c7b9ffd70b78" />


Net signal = VEGF - Inhibitor. Green = Growth Zone. Red = Suppression Zone.

Plot 3: Vessel Front Progression Over Time
<img width="522" height="367" alt="image" src="https://github.com/user-attachments/assets/fa45e2ec-546f-4cee-8ca4-7cf3e7c5c9a2" />


Vessel front moves from bone side toward balance point over time.

Plot 4: Final Vessel Distribution - Narrow Band Formation
<img width="511" height="375" alt="image" src="https://github.com/user-attachments/assets/5bd3ebff-d6ab-4662-a547-9f6d72126992" />


Vessels form a narrow band precisely at the balance point.

## Plot 4: Final Vessel Distribution - Narrow Band Formation

- Vessel Density
- Balance point = 2.31 mm
- Vessel front = 2.31 mm
- Vascularized zone = 2.31 mm
