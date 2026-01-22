## Detailed computational results of the paper:

### An efficient branch-and-cut approach for the sequential competitive facility location problem under partially binary rule

### Yu-Qi Guo，Yan-Ru Wang， Wei-Kun Chen，Yu-Hong Dai

#### [https://arxiv.org/abs/2508.08135](https://arxiv.org/abs/2508.08135)

------

This repository provides tables in CSV format with detailed results of the computational experiments conducted for the paper "An efficient branch-and-cut approach for the sequential competitive facility location problem under partially binary rule".


### Algorithms

The following two B&C algorithms are compared in the computational experiments:

- **B&C+GSF**: Branch-and-Cut algorithm based on formulation (GSF) using improved submodular inequalities
- **B&C+EF**: Branch-and-Cut algorithm based on the extended formulation (EF)

### CSV Data Details

The CSV file `tbl_1000_merge.csv` contains detailed computational results for all 144 large-scale SCFLP instances.

### Column Definitions

The CSV file contains the following columns:

#### Instance Parameters

- **m**: Number of customers
- **n**: Number of potential facility locations
- **p**: Number of facilities opened by the leader
- **r**: Number of facilities opened by the follower

#### Results

- **Obj**: Objective value of the optimal solution (or best incumbent if not solved to optimality)
- **T(G%)**: Total CPU time in seconds. For instances not solved to optimality within the time limit, the optimality gap G% is reported in parentheses, computed as (UB - LB)/UB × 100%, where UB and LB denote the upper bound and lower bound obtained at termination
- **N**: Number of explored branch-and-bound nodes
- **LPG(%)**: LP relaxation gap at the root node, defined as (Obj* - Obj_root)/Obj* × 100%, where Obj* is the optimal objective value or best incumbent and Obj_root is the LP relaxation bound at the root node
- **CT**: CPU time in seconds spent on separating cuts
- **C**: Total number of cuts added throughout the B&C algorithm

### At the end of the table

- **Average**: Contains summarized average statistics across all instances that can be solved by at least one setting
- **Solved**: Contains the total number of instances solved to optimality within the time limit of 7200 seconds 

