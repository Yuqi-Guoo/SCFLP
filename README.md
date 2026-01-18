## Detailed computational results of paper:

# An efficient branch-and-cut approach for the sequential competitive facility location problem under partially binary rule

##### Yu-Qi Guo，Yan-Ru Wang， Wei-Kun Chen，Yu-Hong Dai

###### [https://arxiv.org/abs/2508.08135](https://arxiv.org/abs/2508.08135)

------

This repository provides tables in CSV format with detailed results of the computational experiments conducted for the paper "An efficient branch-and-cut approach for the sequential competitive facility location problem under partially binary rule".



## Test Set

The computational experiments were conducted on a testset of 144 large-scale SCFLP instances. These instances were generated with the following characteristics: 

- **Customer locations** and **facility locations**: Randomly generated with integer coordinates on a [0, 70] × [0, 70] Euclidean plane 
- **Attractiveness parameters**: Set to $v_{ij} = e^{-0.1d_{ij}}$, where $d_{ij}$ is the Euclidean distance between customer $i$ and facility $j$
- **Number of customers** ($m$): 500, 800, 1000
- **Number of potential facility locations** ($n$): 500, 800, 1000
- **Customer demands** ($w_i$): Uniformly randomly chosen from $\{1, ..., 10\}$
- **Number of leader's open facilities** ($p$): 2, 5, 10, 50
- **Number of follower's open facilities** ($r$): 2, 5, 10, 50

## Computational Environment

The proposed B&C algorithms were implemented in **Julia 1.11.5** using **Cplex 20.1.0**. All computations were conducted on a cluster of **Intel(R) Xeon(R) Gold 6230R CPU @ 2.10 GHz** computers with the following settings:

- **Threading**: Single-threaded mode
- **Time limit**: 7200 seconds
- **MIP gap tolerance**: 0%
- **Other parameters**: Default Cplex settings

## Algorithms

The following two B&C algorithms are compared in the computational experiments:

- **B&C+GSF**: Branch-and-Cut algorithm based on formulation (GSF) using improved submodular inequalities
- **B&C+EF**: Branch-and-Cut algorithm based on the extended formulation (EF)

## CSV Data Details

The CSV file `tbl_1000_merge.csv` contains detailed computational results for all 144 large-scale SCFLP instances.

### Column Definitions

The CSV file contains the following columns:

#### Instance Parameters

- **m**: Number of customers
- **n**: Number of potential facility locations
- **p**: Number of facilities that the leader can open
- **r**: Number of facilities that the follower can open

#### Results

- **Obj**: Objective value of the optimal solution (or best incumbent if not solved to optimality)
- **T(G%)**: Total CPU time in seconds. For instances not solved to optimality within the time limit, the optimality gap G% is reported in parentheses, computed as (UB - LB)/UB × 100%, where UB and LB denote the upper bound and lower bound obtained at termination
- **N**: Number of explored branch-and-bound nodes
- **LPG(%)**: LP relaxation gap at the root node, defined as (Obj* - Obj_root)/Obj* × 100%, where Obj* is the optimal objective value and Obj_root is the LP relaxation bound at the root node
- **CT**: CPU time in seconds spent on separating cuts
- **C**: Total number of cuts added throughout the B&C algorithm

### At the end of the table

- **Ave. row**: Contains summarized average statistics across all instances can be solved by both settings 
- **Sol. row**: Contains the total number of instances solved to optimality within the time limit 

