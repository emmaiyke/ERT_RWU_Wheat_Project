## Wheat Field ERT — Multi-Genotype Root Water Uptake Analysis

This project integrates Electrical Resistivity Tomography (ERT) with machine learning calibration to quantify root water uptake (RWU) in field-grown wheat under drought conditions.

Root system architectures were pre-characterized in controlled greenhouse experiments, and field-scale RWU estimates are validated using plant physiology (fluorescence, stomatal conductance) and microclimate data (VPD, PAR) to compare genotype-specific water-use strategies.

ERT_RWU_Wheat_Project/
├── codes/                         # Main scripts
│   ├── main_pipeline_all_plots.py     # Core ERT → SWC → RWU workflow
│   ├── validate_ert_tdr.py           # ERT–TDR calibration and validation
│   ├── Rho_log10_plot.py             # Time-lapse resistivity sections
│   ├── Rho_change_plot.py            # Difference-resistivity (% change)
│   └── plant_physiology_figures.py   # Gsw, fluorescence, yield analysis
│
├── raw_data/                     # Input datasets
│   ├── inversion_res_dat/       # ERT inversion outputs (.dat)
│   ├── tdr_exports/             # TDR soil moisture & temperature
│   ├── metadata/                # Experimental metadata
│   └── climate/                 # VPD and PAR data (if applicable)
│
├── tables/                      # Generated CSV outputs
├── figures/                     # Generated figures
└── README.md                    # Project description
