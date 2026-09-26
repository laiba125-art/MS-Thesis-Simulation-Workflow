# MS Thesis: Simulation-Based Performance Study of a Monolithic CMOS Pixel Sensor

## Overview

This thesis presents a simulation-based performance study of a monolithic CMOS pixel sensor using the **Allpix Squared** Monte Carlo framework. The simulated sensor comprises a 20 × 20 pixel matrix with a 28 µm × 28 µm pixel pitch and a 100 µm sensitive silicon thickness. The internal electric field is modelled using a linear field approximation restricted to a 25 µm depleted epitaxial layer under a reverse bias voltage of −6 V, approximating the two-layer structure of thin monolithic CMOS sensors.

## Simulation Chain

- **Charge deposition:** Geant4-based, using a 120 GeV positive pion beam
- **Charge transport:** Drift-diffusion model with the Jacoboni–Canali mobility model
- **Charge collection:** Direct pixel assignment
- **Digitization:** Discriminator threshold of 120 e⁻, electronic noise of 10 e⁻

## Baseline Detector Performance (Nominal Conditions)

| Metric | Value |
|---|---|
| Cluster charge (MPV) | 2.019 ± 0.005 ke⁻ |
| Mean cluster size | 1.945 ± 0.010 pixels |
| Intrinsic spatial resolution (σₓ) | 6.030 ± 0.176 µm |
| Hit detection efficiency | 99.983 ± 0.013 % |

Spatial resolution was extracted using the RMS99.73% method (following Dannheim et al.), with statistical uncertainties evaluated from 10,000 Poisson pseudo-experiments.

## Parametric Studies

**Angular dependence:**
Spatial resolution improves from 6.030 µm at normal incidence to a minimum of 3.857 ± 0.334 µm at 30°, driven by enhanced charge sharing at oblique incidence. Detection efficiency remains above 99.6% across the full angular range.

**Threshold scan:**
Spatial resolution degrades monotonically from 5.594 µm at 40 e⁻ to 7.105 µm at 500 e⁻, with a corresponding reduction in mean cluster size. Detection efficiency remains at unity across the full threshold range.

**Bias voltage scan:**
Stable charge collection confirmed across −6 V to −20 V, consistent with fully depleted operation. Mean charge carrier drift time decreases from 3.760 ns to 2.603 ns at higher voltages.

## Comparison with Literature

Results are compared with published findings reporting a spatial resolution of 3.60 µm for a comparable sensor geometry simulated using detailed TCAD electric field maps. The larger resolution obtained in this work is attributed to the linear electric field approximation used, which does not reproduce the strongly non-uniform field profiles characteristic of small collection electrode CMOS sensors.

## Conclusion

This work establishes a validated simulation baseline for monolithic CMOS pixel sensors within the Allpix Squared framework, and identifies the integration of TCAD-derived electric field maps as the most impactful direction for future improvement.

## Repository Structure

- `Simulation_Workflow/` — Allpix Squared configuration files and instructions to run the simulation
- `Analysis/` — Python scripts used for post-processing and performance analysis
- `Results/` — Plots, graphs, and extracted performance metrics

## Tools & Frameworks

- Allpix Squared (Monte Carlo simulation framework)
- Geant4
- Python (analysis)
