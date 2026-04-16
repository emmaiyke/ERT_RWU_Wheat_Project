# Multi-Genotype Inversion -> SWC -> RWU

Main script:
- `run_multigenotype_inversion_to_rwu.py`

Run from terminal:
```bash
python3 run_multigenotype_inversion_to_rwu.py
```

Expected package layout (relative to script):
- `../raw_data/inversion_res_dat/f001_res.dat ... f044_res.dat`
- `../raw_data/tdr_exports/DataSnapExport_*.csv`
- `../raw_data/metadata/*.csv`

Outputs:
- `../figures/`
- `../report/tables/`
- `../report/multi_genotype_inversion_to_rwu_report.md`
