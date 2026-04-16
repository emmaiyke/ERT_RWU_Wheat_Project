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
