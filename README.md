# Understanding Growth in Genome-Scale Metabolic Models


The scripts reproduce the main experiments and results presented in the study, which introduces a novel method to classify metabolic reactions based on their functional role in the production of growth. This includes:

- Identify essential, redundant reactions and dead reactions at optimal or suboptimal growth.
- Compute the minimum set of reactions for a given growth rate.
- Compute bottleneck reactions limiting optimal growth.

## 📁 Repository Contents

- ```growth_bottlenecks.py```
Computes the number of bottleneck reactions limiting optimal growth 
using Flux Variability Analysis (FVA) as described in the paper.

- ```compute_reactions_sets.py```
Processes a list of Genome-Scale Models (GEMs) and computes the functional classification of reactions for each model (essential, redundant, dead), as well as the size of the minimum set of reactions for growth.

- ```compute_reactions_across_growth.py```
Computes the functional classification of reactions for a single GEM
for different ranges of growth rates, identifying essential, redundant, and dead reactions,
as well as the minimum number of reactions for the given growth rate.

## ⚙️ Requirements

This codebase is written in Python and uses the following main dependencies:

- [COBRApy](https://opencobra.github.io/cobrapy/)
- [CONTRABASS](https://github.com/openCONTRABASS/CONTRABASS)
- [Pyomo](https://www.pyomo.org/)
- [Gurobi Optimizer](https://www.gurobi.com/) (version ≥ 9.5.2)

The essential dependencies can be installed with:
```bash
pip install -r requirements.txt
```

## 🚀 Quickstart

Download a small SBML metabolic model using command line:

```bash
curl -O https://bigg.ucsd.edu/static/models/e_coli_core.xml
```

Run analysis:
```
python growth_bottlenecks.py --models e_coli_core.xml
python compute_reactions_sets.py --models e_coli_core.xml
```

## 🧪 Reproducing the Results

1. Place your genome-scale models (in SBML or JSON format) in a directory.

2. For growth bottlenecks, run:
    ```bash
    python growth_bottlenecks.py --models <model-path.xml>
    ```
3. To compute reaction sets for one model at optimal growth rate, run:
    ```bash
    python compute_reactions_sets.py --models <model-path.xml>
    ```
4. To compute reactions sets for a custom growth rate you can use the `--growth-rate` param (e.g. `0.5` for 50% of optimal; default is `1.0`):
    ```bash
    python compute_reactions_sets.py --models <model-path.xml> --growth-rate 0.5
    ```

## 🔬 Advanced Usage 

For convenience, all previous scripts allow to 
run analysis on multiple models:

1. For growth bottlenecks, run:
    ```bash
    python growth_bottlenecks.py --models <model-path-1.xml> <model-path-2.xml> ...
    ```
2. To compute reaction sets for one or more models (at a given growth rate), run:
    ```bash
    python compute_reactions_sets.py 
    --growth-rate 1.0 
    --models <model-path-1.xml> <model-path-2.xml> ...
    ```

You can tune the MILP solver time limit (``--time-limit``, default 600) and MIP optimality gap (``--ratio``, default 1e-4) with the following parameters:
```bash
python compute_reactions_sets.py --models <model-path.xml> --time-limit 120 --ratio 0.01
```
The same flags are available in `compute_reactions_across_growth.py`.

## 📄 License

This project is licensed under the GPL-3.0 License. See the [LICENSE](LICENSE) file for details.

## 📫 Contact

For questions please contact [alexOarga](https://github.com/alexOarga)