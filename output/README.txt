Outputs for MODEL1507180007 (Thiele2005 - H. pylori iIT341)
Downloaded from BioModels: https://www.ebi.ac.uk/biomodels/MODEL1507180007
Model file: ../models/MODEL1507180007.xml

Scripts run (Python 3.11 + updated contrabass):
1. growth_limiting_reactions.py -> fva_MODEL1507180007.csv
2. generate_sets.py             -> generate_sets.log / generate_sets.tsv
3. generate_single.py           -> generate_single.log / generate_single.tsv
   (growth fractions 0.00 .. 1.00 step 0.05)

Notes:
- MILP step used CBC (Gurobi not installed). Suboptimal growth rates often hit
  the CBC time cutoff, so MRG for those rows may be a feasible but not proven
  optimal minimum (see "aborted" warnings in generate_single.log).
- generate_sets at growth_rate=1.0 finished within the cutoff.
