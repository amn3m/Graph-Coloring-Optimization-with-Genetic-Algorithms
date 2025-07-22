#  Graph Coloring Optimization using a Genetic Algorithm

This repository contains a Python implementation of a graph coloring solver using a Genetic Algorithm and a traditional Backtracking algorithm. The project is designed to find the minimum number of colors required to color a graph such that no two adjacent vertices share the same color.

##  Project Overview

Graph coloring is a classic NP-hard problem with significant real-world applications in domains like scheduling, resource allocation, and frequency assignment. This project provides a tool to tackle this problem by implementing two distinct algorithmic approaches:

1.  A **Genetic Algorithm**, which uses principles of natural selection to evolve solutions and find near-optimal colorings efficiently.
2.  A **Backtracking Algorithm**, which performs an exhaustive search to guarantee the optimal solution, serving as a benchmark for correctness.

The program can handle various graph input formats and compares the performance and results of both algorithms.

##  Key Features

*   **Dual Algorithm Implementation:** Solves the graph coloring problem using both a Genetic Algorithm and a Backtracking algorithm.
*   **Flexible Graph Input:** Accepts graph data from multiple sources:
    *   Adjacency List
    *   Adjacency Matrix
    *   Adjacency Dictionary
    *   Randomly Generated Graph
*   **Automated Chromatic Number Search:** The program iteratively reduces the number of available colors to find the minimum required for a valid solution.
*   **Performance Comparison:** Directly benchmarks the heuristic-based genetic approach against the guaranteed backtracking method, highlighting trade-offs between speed and optimality.

##  Algorithms & Methodology

### Genetic Algorithm

The genetic algorithm finds a solution by evolving a population of candidate colorings (chromosomes). The core process includes:

1.  **Initialization:** An initial population of random colorings is generated.
2.  **Fitness Evaluation:** Each coloring is assigned a fitness score based on the number of "conflicts" (adjacent nodes with the same color). A lower conflict score means a higher fitness.
3.  **Selection:** The fittest individuals are selected to be "parents." This implementation includes **Tournament Selection** and **Truncation Selection**.
4.  **Crossover:** Parents are combined to create offspring, inheriting traits from both. **One-Point** and **Two-Point Crossover** methods are used.
5.  **Mutation:** Random changes are introduced into the offspring to maintain genetic diversity and avoid premature convergence.
6.  **Termination:** The cycle repeats until a valid, conflict-free coloring is found or a maximum number of generations is reached.

### Backtracking Algorithm

The backtracking algorithm provides a guaranteed solution by exploring the search space recursively. It assigns colors to vertices one by one, and if an assignment leads to a conflict, it backtracks to the previous vertex and tries a different color. This exhaustive search ensures it finds the optimal coloring but can be computationally expensive for large graphs.

##  Key Findings

*   The **Genetic Algorithm** consistently found valid colorings for a wide range of graph sizes and structures within a reasonable number of generations.
*   The **Backtracking Algorithm** successfully guaranteed the optimal solution (the true chromatic number) but became significantly slower as the number of graph nodes increased.
*   The project demonstrates a classic AI trade-off: the genetic algorithm provides a highly effective and scalable heuristic for finding near-optimal solutions quickly, making it ideal for large, complex problems where a guaranteed optimal solution is not feasible to compute.

##  How to Use

1.  Run the main program.
2.  Enter the number of nodes in the graph.
3.  Enter the desired population size for the Genetic Algorithm.
4.  Choose the input format for your graph (List, Matrix, Dictionary, or Random).
5.  Provide the graph data as prompted.
6.  The program will output the greedy solution, the final coloring with the minimum colors found, and a proof from the backtracking algorithm.
