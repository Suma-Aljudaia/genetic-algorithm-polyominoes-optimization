# Genetic Algorithm Polyominoes Optimization

This project addresses a **combinatorial optimization problem** modeled as a Set Cover / Polyominoes Puzzle.  
The goal is to determine the **minimum number of subsets (tiles)** required to fully cover a given set **without overlaps**, using both exact and heuristic optimization techniques.

---

## Problem Formulation

The problem is formulated as an optimization task where:
- Each candidate solution represents a selection of subsets from a given collection.
- The selected subsets must **cover all elements** in the target set.
- **Overlapping between subsets is not allowed**.
- The objective is to **minimize the number of selected subsets**.

To enable efficient exploration of the solution space, solutions are represented using **binary encoding**, where:
- `1` indicates a selected subset
- `0` indicates an unselected subset

This representation satisfies:
- **Completeness**: All possible subset combinations can be represented.
- **Connectivity**: Neighboring solutions can be generated via small binary changes.
- **Effectiveness**: Solutions can be evaluated efficiently.

---

## Optimization Approach

### 1. Branch and Bound
An exact search method was used to:
- Systematically explore feasible solutions.
- Prune invalid or suboptimal branches early.
- Identify an optimal solution when possible.

This approach guarantees correctness but suffers from exponential growth in the search space.

---

### 2. Genetic Algorithm
To handle larger and more complex cases, a **Genetic Algorithm (GA)** was implemented as a heuristic optimization approach.

Key components include:
- **Population-based search**
- **Fitness evaluation** based on coverage and overlap constraints
- **Uniform crossover** to improve exploration diversity
- **Swap mutation** to refine solutions without disrupting good candidates
- **Neighborhood functions** (flip and swap) to explore local solution spaces

The GA provides near-optimal solutions efficiently for problems where exact methods become impractical.

---

## Analysis

- The size of the search space grows exponentially with the number of subsets (2ⁿ).
- Neighborhood functions enable controlled exploration of nearby solutions.
- The combination of exact (Branch and Bound) and heuristic (GA) methods provides both correctness and scalability.

---

## Implementation

All algorithms were implemented and evaluated using Python.  
The notebook includes:
- Solution representation
- Objective function definition
- Branch and Bound implementation
- Genetic Algorithm design and operators
- Experimental evaluation and results

---

## Technologies
- Python
- Genetic Algorithms
- Combinatorial Optimization
- Search Algorithms

---

## Files
- `Genetic_Algorithm_Polyominoes_Puzzle.ipynb` — Complete implementation and experimental results
