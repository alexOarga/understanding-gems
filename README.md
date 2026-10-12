# Understanding Growth in Genome-Scale Metabolic Models


The scripts reproduce the main experiments and results presented in the study, which introduces a novel method to classify metabolic reactions based on their functional role in the production of growth. This includes:

- Identify essential, redundant reactions and dead reactions at optimal or suboptimal growth.
- Compute bottleneck reactions limiting optimal growth.
- Explain gene essentiality in terms of reaction redundancy.

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

## 🧪 Reproducing the Results

1. Place your genome-scale models (in SBML or JSON format) in a directory.

2. For growth bottlenecks, run:
    ```bash
    python growth_bottlenecks.py --models <model-path-1.xml> <model-path-2.xml> ...
    ```
3. For a batch analysis of models, run:
    ```bash
    python compute_reactions_sets.py --models <model-path-1.xml> <model-path-2.xml> ...
    ```

4. For a single model analysis, run the following pointing to the model file:
    ```bash
    python compute_reactions_across_growth.py <path-to-your-model.xml>
    ```

## 📄 License

This project is licensed under the GPL-3.0 License. See the [LICENSE](LICENSE) file for details.

## 📫 Contact

For questions please contact [alexOarga](https://github.com/alexOarga)