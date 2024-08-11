

# Asynchronous-Decentralized-Constrained-Optimization

This repository contains the Python code associated with the experiments presented in the paper "Asynchronous Decentralized Optimization with Constraints: Achievable Speeds of Convergence for Directed Graphs." The code is organized into four main Python scripts (`exp1.py`, `exp2.py`, `exp3.py`, `exp4.py`). Below, you will find a brief description of each experiment, how to run them, and the required dependencies.


## Repository Structure

- `utilities/`: Contains all utility functions used across experiments.
- `Problems/`: Includes problem definitions, gradients, and projections.
- `data/`: Stores the MNIST dataset used in some of the experiments.
- `Optimizers/`: Contains implementations of centralized and decentralized algorithms.
- `graph/`: Holds scripts for generating gossip matrices. `graph_pg_extra.py` is a more general script that provides additional matrices necessary for the PG-EXTRA algorithm.
- `analysis/`: Contains functions for computing performance metrics such as the optimality gap and feasibility gap



## Experiments

### exp1.py
Solves a constrained optimization problem and compares the performance to DAGP and its throttled variant. 


### exp2.py
Addresses an unconstrained logistic regression problem and makes comparisons to APPG and ASY-SPA. 


### exp3.py
Focuses on a constrained problem over undirected graphs, comparing the results to ASY-PG-EXTRA. 


### exp4.py
Investigates the robustness to message losses with a communication failure probability of \(p\). 


## Note on the creation of asynchronous profiles

All experiments simulate asynchronous profiles based on a global iteration counter, which advances whenever at least one agent computes. 

The asynchronous profiles are generated by creating computation times for nodes (`TV_nodes` parameter) and computing all unique times when at least one node is activated (`T_active` parameter). Algorithms update their variables at each iteration only for those nodes activated at that specific time, for a total of `max_iter` iterations.



## Dependencies and Environment Setup

The `requirements.txt` file in this repository lists all the libraries and packages installed in the Anaconda environment used for developing and testing the experiments. It is important to note that this list may include more packages than are strictly necessary for running the experiments, as it reflects the entire environment setup.

```bash
pip install -r requirements.txt
```
