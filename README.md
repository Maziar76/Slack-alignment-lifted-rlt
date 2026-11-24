# Slack Alignment and Exactness of Lifted-RLT Relaxations

Reproducibility materials and numerical experiments for the study of slack alignment and exactness properties of semidefinite programming (SDP) and Reformulation-Linearization Technique (RLT) relaxations of equality-constrained box-constrained quadratic programs.

## Overview

This repository accompanies the research on slack-based exactness conditions for quadratic optimization problems of the form

\[
\begin{aligned}
\min \quad & x^\top Hx+c^\top x\\
\text{s.t.}\quad & Ax=b,\\
&0\leq x\leq 1,
\end{aligned}
\]

where the matrix \(H\) is not necessarily positive semidefinite.

The study investigates how equality constraints restrict feasible semidefinite slack directions and how this restriction affects the exactness of SDP and Lifted-RLT relaxations.

The main theoretical and computational topics include:

- Slack-based alignment measures and exactness conditions.
- Equality-induced nullspace restrictions.
- Fractional-coordinate localization of the relevant curvature conditions.
- Rank properties of feasible lifted slack matrices.
- A posteriori bounds on the relaxation gap.
- Numerical comparisons between classical and equality-strengthened relaxations.

## Repository contents

The accompanying ZIP archive contains the computational scripts, numerical outputs, and supporting documentation.

The principal experiments are organized around three complementary purposes:

1. **Main numerical experiments:** Randomly generated instances used to compare alignment measures and the behavior of the different relaxations.
2. **Constructed sharpness experiments:** Structured instances illustrating the quantitative a posteriori gap bound.
3. **Coupled experiments:** Non-diagonal reduced-Hessian instances designed to demonstrate nonzero QP–Lifted-RLT gaps and the numerical tightness of the trace bound.

## Computational environment

The experiments use Python and convex optimization software.

The principal dependencies include:

- Python 3
- NumPy
- SciPy
- CVXPY
- SCS
- Clarabel

Install the principal dependencies using:

```bash
pip install numpy scipy cvxpy scs clarabel
```

The exact package versions used for a particular run should be recorded alongside the corresponding computational results.

## Running the experiments

After extracting the accompanying ZIP archive, the principal scripts are located in the `src/` directory.

The experiments can be run separately:

```bash
python src/unified_experiments.py
```

```bash
python src/constructed_sharpness.py
```

```bash
python src/coupled_experiment.py
```

The generated numerical outputs are saved in the corresponding results directories.

## Numerical interpretation

The computational results are intended to illustrate the theoretical properties and quantitative bounds developed in the accompanying study.

In particular, the coupled experiments examine:

- Negative curvature on the relevant fractional-coordinate subspace.
- Nonzero semidefinite slack in computed lifted solutions.
- Positive gaps between feasible QP solutions and feasible lifted relaxation solutions.
- The numerical tightness of the a posteriori trace bound.
- Sensitivity of numerical rank classifications to the selected tolerance.

Solver-reported primal and dual quantities are treated with appropriate numerical caution. In particular, SCS dual objectives are numerical diagnostics and are not presented as independently verified formal dual certificates.

A solver's returned feasible lifted solution provides a candidate relaxation value; it should not automatically be interpreted as a certified optimal relaxation value.

## Reproducibility

The scripts and accompanying numerical outputs are provided to facilitate inspection and reproduction of the computational experiments.

Numerical results may vary slightly with solver versions, tolerances, and computational environments. Randomized experiments should be reproduced using the seeds and instance-generation specifications recorded with the relevant scripts and outputs.

## Citation

If you use this repository, please cite the accompanying research manuscript.

**Manuscript title:** *Slack Alignment and Exactness of Lifted-RLT Relaxations* 

The final bibliographic information will be added following publication.

## License

No license has currently been assigned to this repository. All rights are reserved by the repository owner unless otherwise stated.
