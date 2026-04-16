# Wheat Field ERT — Multi-Genotype Root Water Uptake Analysis

This project uses field-based ERT with ML calibration to quantify root water uptake in wheat. 
Root architectures were pre-selected in greenhouse experiments, and field results are validated 
with plant physiology and microclimate data to compare genotype water-use strategies under drought.

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
