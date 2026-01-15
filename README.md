## Online Supplement of:

# An efficient branch-and-cut approach for the sequential competitive facility location problem under partially binary rule

##### Yu-Qi Guo，Yan-Ru Wang， Wei-Kun Chen，Yu-Hong Dai

##### School of Mathematics and Statistics, Beijing Institute of Technology,  Beijing 100081, China

###### chenweikun@bit.edu.cn

------

This online supplement provides tables in CSV format with detailed results of the computational experiments conducted for the paper "An efficient branch-and-cut approach for the sequential competitive facility location problem under partially binary rule".



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

#### B&C+GSF Results (Formulation (GSF) with Improved Submodular Inequalities)

- **Obj_B&C+GSF**: Objective value of the optimal solution (or best incumbent if not solved to optimality)
- **T(G%)_B&C+GSF**: Total CPU time in seconds. For instances not solved to optimality within the time limit, the optimality gap G% is reported in parentheses, computed as (UB - LB)/UB × 100%, where UB and LB denote the upper bound and lower bound obtained at termination
- **N_B&C+GSF**: Number of explored branch-and-bound nodes
- **LPG(%)_B&C+GSF**: LP relaxation gap at the root node, defined as (Obj* - Obj_root)/Obj* × 100%, where Obj* is the optimal objective value and Obj_root is the LP relaxation bound at the root node
- **CT_B&C+GSF**: CPU time in seconds spent on separating cutting planes
- **C_B&C+GSF**: Total number of cutting planes (improved submodular inequalities) added throughout the B&C algorithm

#### B&C+EF Results (Extended Formulation (EF))

- **Obj_B&C+EF**: Objective value of the optimal solution (or best incumbent if not solved to optimality)
- **T(G%)_B&C+EF**: Total CPU time in seconds. For instances not solved to optimality within the time limit, the optimality gap G% is reported in parentheses
- **N_B&C+EF**: Number of explored branch-and-bound nodes
- **LPG(%)_B&C+EF**: LP relaxation gap at the root node
- **CT_B&C+EF**: CPU time in seconds spent on separating cutting planes 
- **C_B&C+EF**: Total number of cutting planes added throughout the B&C algorithm

### Special Rows

- **Average row**: Contains summarized average statistics across all instances (marked with "Average" in the m column)
- **Solved row**: Contains the total number of instances solved to optimality within the time limit (marked with "Solved" in the m column) 

