# Wheat Field ERT — Multi-Genotype Root Water Uptake Analysis

This repository contains the full data-processing pipeline for a 2024 field
experiment that combined **Electrical Resistivity Tomography (ERT)** with
**Time-Domain Reflectometry (TDR)** sensors to estimate root water uptake
(RWU) in three wheat genotypes under terminal drought.

## Repository structure

```
wheat_ert_rwu/
├── src/
│   ├── main_pipeline.py            # Core ERT → SWC → RWU workflow
│   ├── validate_ert_tdr.py         # Standalone ERT–TDR cross-validation figure
│   ├── plot_ert_difference.py      # Time-lapse difference-resistivity sections
│   └── plant_physiology_figures.py # Fluorescence, Gsw, yield, and RWU vs Gsw
│
├── data/                           # (gitignored) raw_data folder lives here
│   └── README_data.md
│
├── figures/                        # Generated PNG outputs (gitignored)
├── report/
│   └── tables/                     # Generated CSV tables (gitignored)
│
└── README.md                       # This file

## Pipeline overview (`main_pipeline.py`)

```
TDR exports (.csv)
    │
    ▼  Step 1 — load_tdr_data()
Daily medians: theta, temperature, bulk resistivity
    │
    ▼  Step 2 — build_depth_daily_temperature()
                interpolate_temperature_to_layers()
Layer temperatures at each inversion date
    │
    ▼  Step 3 — extract_corrected_profiles()
Temperature-corrected resistivity per (genotype, date, layer)
    │
    ▼  Step 4 — extract_ert_at_tdr_sensors()
Paired ERT–TDR calibration dataset
    │
    ▼  Step 5 — cross_validate_rf()
Random Forest model: [ln(rho), depth] → theta  (GroupKFold by date)
    │
    ▼  Step 6 — convert_profiles_to_swc()
Predicted SWC for all genotype/layer/date combinations
    │
    ▼  Step 7 — compute_rwu()
Cumulative root water uptake (terminal-drought assumption)
    │
    ▼  Step 8 — run_suite()
 publication-quality figures + all intermediate CSV tables
```

### Terminal-drought assumption

All SWC decline is attributed to root water uptake (no rain, irrigation, or
lateral flow). The monotonic-drying constraint is:

```
theta_mono(t) = min_{τ ≤ t} theta(τ)
RWU_step(t)  = max(0, -Δtheta_mono(t)) × Δz × 1000  [mm]
RWU_cum(t)   = Σ RWU_step
```

with layer thickness Δz = 0.1 m.

### Temperature correction

```
rho_corr = rho_raw × (1 + α × (T − T_ref))
```

where α = 0.02 °C⁻¹ and T_ref = 25 °C.


