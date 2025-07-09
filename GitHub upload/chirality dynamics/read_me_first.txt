README-first.txt  —  Chirality-reversal checks
================================================
This folder reproduces Section VII  
“**Chirality and Reversal of Dynamical Outcomes**” of the paper.

Files
-----
| Script | Role |
|--------|--------------------------------------------------------------|
| **data_for_CCW_system.py** | Runs the 10 000-point sweep with the intrinsic fibre spin flipped from −1 (clockwise) to **+1 (counter-clockwise)**.  Produces `../ode_steady_analysis_ccw.xlsx`, mirroring the clockwise file generated earlier by `C1_verify.py`. |

| **chirality_left_right_summary.py** | Reads both workbooks – clockwise (`../ode_steady_analysis.xlsx`) and counter-clockwise (`../ode_steady_analysis_ccw.xlsx`) – keeps only rows with `match_type ∈ {(1),(2)}` (steady state + zeros) and prints counts of trajectories that converge to the **Right** side (δ★ > δ₀) or **Left** side (δ★ < δ₀).  No files are written. |

Dependencies
------------
* Python ≥ 3.9  
* numpy, scipy, pandas, tqdm, openpyxl  
  (same environment as the other verification scripts)

Run order
---------
```bash
# 1. Ensure the clockwise dataset exists one directory up:
#    ../ode_steady_analysis.xlsx    ← produced by C1_verify.py

# 2. Generate the counter-clockwise dataset by data_for_CCW_system.py

# 3. Print left-vs-right convergence statistics for both chiralities by python chirality_left_right_summary.py
