# Wheat Field ERT — Multi-Genotype Root Water Uptake Analysis

This repository contains the full data-processing pipeline for a 2024 field
experiment that combined **Electrical Resistivity Tomography (ERT)** with
**Time-Domain Reflectometry (TDR)** sensors to estimate root water uptake
(RWU) in three wheat genotypes under terminal drought.

## Repository structure

```
Ert_rwu_wheat/
├── codes/
├    ├── Rho_log10-plot.py                    # Time-lapse resistivity sections
├    ├── Rho_change(%)-plot.py                # Time-lapse difference-resistivity sections
│    ├── main_pipeline_all_plots.py           # Core ERT → SWC → RWU workflow
│         ├── validate_ert_tdr.py             # Standalone ERT–TDR cross-validation figure
│         └── plant_physiology_figures.py     # Fluorescence, Gsw, yield, and RWU vs Gsw   
│   
│    
├── raw data                                  # inversion_res.dat, meta-data, tdr, vpd & par                                             
│                       
├──  tables                         # Generated CSV tables                      
│
└── README.md                       # This file
