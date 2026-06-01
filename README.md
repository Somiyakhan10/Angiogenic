# Agent-Based Angiogenesis Simulation: Competing Chemotactic Gradients Guide Emergent Vascular Network Formation

## Overview

This project implements an agent-based computational model of angiogenesis — the formation of new blood vessels from pre-existing vasculature. The model specifically investigates how competing pro-angiogenic (VEGF) and anti-angiogenic (inhibitor) gradients regulate tip cell migration, branching, anastomosis, and network arrest in a scaffold-like microenvironment.

## Hypothesis

Angiogenic network patterning is not solely determined by VEGF concentration alone, but critically depends on the balance between pro-angiogenic and anti-angiogenic signals, with hypoxia feedback providing spatial regulation and stochastic tip-cell behavior generating realistic branching morphology.

## Objectives

Implement an agent-based tip-cell simulation with chemotaxis, branching, anastomosis, and stalling rules

Generate realistic VEGF and inhibitor gradient fields on a 2D scaffold domain

Incorporate oxygen-dependent hypoxia feedback that upregulates effective VEGF response

Simulate network evolution from bone-edge seed points to inhibitor-dominated arrest zone

## Methodology

The project uses a combination of:

Agent-based modeling of tip-cell migration and decision-making

Finite-difference gradient field generation (VEGF, inhibitor, oxygen)

Bilinear interpolation for continuous-space chemotaxis

Stochastic branching with generation-dependent probability

Distance-based anastomosis detection

Oxygen diffusion from vessel segments with hypoxia feedback

Boundary reflection handling at scaffold edges

Network visualization with generation-based color mapping

## Domain Parameters

| Parameter | Value | Biological Basis |
| :--- | :--- | :--- |
| Domain size | 10 x 10 mm | Typical scaffold cross-section |
| Grid resolution | 200 x 200 | Sub-cellular detail |
| VEGF decay constant | 2.8 | Exponential gradient from bone edge |
| Inhibitor rise constant | 2.8 | Exponential gradient from tendon edge |
| Chemotactic coefficient (chi) | 3.5 | Response strength to gradient |
| Branching probability (base) | 0.012 | Per-step branching rate (literature-calibrated) |
| Anastomosis radius | 0.35 mm | Tip fusion distance |
| Hypoxia boost factor | 1 + 2 exp(-O2/15) | Upregulation at low oxygen |
| Tip step size | 0.12 mm | Migration per 6-hour time step |
| Maximum active tips | 120 | Tip-stalk competition cap |
| Maximum branch generation | 4 | Prevents unbounded branching |

## Results

### Final Vascular Network

<img width="590" height="606" alt="image" src="https://github.com/user-attachments/assets/83dfea25-e3aa-4c6d-9140-f423613ce00e" />


*Figure 1: Emergent branching vascular network from agent-based simulation. Competing VEGF and inhibitor gradients guide tip-cell migration from bone edge toward tendon side. Network arrests near the theoretical balance point where net signal equals zero.*

Color legend: Generation 0 (purple) primary sprouts, Generation 1 (pink) first-order branches, Generation 2 (red) second-order branches, Generation 3 (orange) third-order branches, Generation 4+ (green) higher-order branches. Cyan circles indicate anastomosis events. Yellow squares mark bone-edge seed points. Dashed line shows theoretical balance point at 8.2 mm.

### Time Evolution of Network Development

<img width="1412" height="418" alt="image" src="https://github.com/user-attachments/assets/ddb31a88-8c1a-4405-9b48-8cd4d8c32b1f" />


*Figure 2: Four snapshots showing vascular network development over time.*

Step 30 (Early Sprouting): Primary tip cells migrate rightward guided by VEGF gradient. Minimal branching observed.

Step 80 (Primary Invasion): Vessels penetrate deeper into scaffold. First branching events occur. Network length increases.

Step 180 (Active Branching): Multiple branch generations visible. Anastomosis events begin connecting nearby vessels. Network approaches balance zone.

Step 300 (Final Dense Network): Network arrests near 8.2 mm balance point. Dense, interconnected morphology established. No further progression into inhibitor-dominated region.

### Multi-Panel Overview

<img width="981" height="627" alt="image" src="https://github.com/user-attachments/assets/9276162e-0ed2-44f0-bccc-064090480008" />


*Figure 3: Comprehensive visualization of all model components.*

Panel A (VEGF Field): Pro-angiogenic signal highest at bone edge, decaying exponentially toward tendon side.

Panel B (Inhibitor Field): Anti-angiogenic signal lowest at bone edge, rising toward tendon side.

Panel C (Net Signal): VEGF minus Inhibitor. Zero-crossing (balance point) marked by yellow dashed line at 8.2 mm.

Panel D (Oxygen Field): Oxygen diffuses from vessel network. Vessel overlay shown in white.

Panel E (Effective VEGF): Hypoxia feedback amplifies VEGF response in low-oxygen regions.

Panel F (Final Network): Emergent vascular architecture overlaid on net signal field.

### Quantitative Summary

| Metric | Result |
| :--- | :--- |
| Network arrest position | 8.2 mm from bone edge |
| Maximum branch generation | Generation 4+ |
| Total network length | 126 mm |
| Tip cells seeded | 12 |
| Vessel segments | 24 |
| Anastomosis events | Observed |
| Simulation steps | 300 |

### Hypothesis Validation

The simulation successfully validates the central hypothesis: competing VEGF and inhibitor gradients produce structured, directional, branching vascular networks that arrest near the theoretical balance point. This emergent patterning arises solely from local tip-cell rules without any global coordinate system. All qualitative features observed in experimental angiogenesis (directional sprouting, density-dependent branching, vessel fusion, inhibitor-mediated arrest) are reproduced by the model.


## References

Fan, N., Bull, J.A. & Byrne, H.M. (2026). Exploring the relationship between vascular remodelling and tumour growth using agent-based modelling. PLoS Computational Biology, 22(5), e1012967.

Giverso, C., Grappein, D. & Scialò, S. (2026). Modeling tumor growth with variable mass and angiogenesis-driven perfusion through a 3D-1D coupled framework. arXiv, 2603.29615.

Wang, L.S. et al. (2025). A hybrid PDE-ABM model for angiogenesis and tumour microenvironment with application to resistance in cancer treatment. arXiv, 2505.22580.

Wang, L.S. et al. (2025). Analysis and Mean-Field Limit of a Hybrid PDE-ABM Modeling Angiogenesis-Regulated Resistance Evolution. Mathematics, 13(17), 2898.

Nasello, G. et al. (2025). An in silico study reveals how architectural and mechanical cues jointly regulate angiogenesis and bone regeneration in 3D printed scaffolds. Computers in Biology and Medicine, 185, 109825.

## License

MIT License. Free for academic and research use. Not for clinical diagnosis without experimental validation.
