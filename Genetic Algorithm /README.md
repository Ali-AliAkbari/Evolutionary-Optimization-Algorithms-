# Genetic Algorithm for Solving the Traveling Salesman Problem (TSP)

## Overview

This section of the repository implements a **Genetic Algorithm (GA)** to find an optimized route for the **Traveling Salesman Problem (TSP)**. The algorithm evolves a population of potential solutions using **selection, crossover, and mutation** to minimize the total distance traveled.

## What is the Traveling Salesman Problem (TSP)?

The **Traveling Salesman Problem (TSP)** is a classic optimization problem in which a salesman must visit a set of cities **exactly once** and return to the starting city while minimizing the total travel distance. TSP is an **NP-hard** problem, meaning there is no known efficient algorithm to find the optimal solution in polynomial time for large datasets.

TSP has applications in:

- **Logistics & Supply Chain Management**: Optimizing delivery routes
- **Circuit Design**: Minimizing wire length in printed circuit boards
- **Robotics & AI**: Path planning for autonomous systems
- **Genome Sequencing**: DNA fragment alignment

Due to the problem's complexity, heuristic and metaheuristic approaches, such as the **Genetic Algorithm**, are often used to find near-optimal solutions efficiently.

## What is a Genetic Algorithm (GA)?

A **Genetic Algorithm (GA)** is an optimization technique inspired by **natural selection** and **evolution**. It iteratively improves solutions by simulating biological processes such as **selection, crossover, and mutation**.

### Key Steps of Genetic Algorithm:

1. **Initialization**: Generate an initial population of random solutions.
2. **Fitness Evaluation**: Measure how good each solution is (shorter distances are better in TSP).
3. **Selection**: Choose the best solutions as parents based on fitness.
4. **Crossover (Recombination)**: Combine parent solutions to create new offspring.
5. **Mutation**: Introduce small changes to maintain diversity.
6. **Elitism & Replacement**: Keep the best solutions and replace weaker ones.
7. **Termination**: Stop when the best solution stabilizes or after a set number of generations.

### Why Use GA for TSP?

- **GA explores a vast solution space efficiently**: Instead of checking all possible routes (which grows factorially), it evolves good solutions over time.
- **It avoids local optima**: Unlike greedy algorithms, GA doesn't get stuck in suboptimal solutions.
- **It is adaptable to variations of TSP**: GA can handle constraints like time windows or additional travel costs.

## Features

- Random generation of cities within a given coordinate range
- Fitness evaluation based on the total path distance
- Tournament selection for choosing parents
- Ordered crossover to generate offspring
- Mutation with a configurable probability
- Elitism to retain the best individuals across generations
- Early stopping if improvements stagnate
- Visualization of the evolving paths
- Animated GIF output of the optimization process

## Requirements

This implementation requires the following Python libraries:

- `numpy`
- `matplotlib`
- `random`

You can install missing dependencies using:

```bash
pip install numpy matplotlib
```

## Usage

Run the script to execute the Genetic Algorithm for TSP:

```python
python genetic_algorithm_tsp.py
```

### Key Parameters

| Parameter                | Description                              | Default Value |
| ------------------------ | ---------------------------------------- | ------------- |
| `n_cities`               | Number of cities in the problem          | 30            |
| `Xmin, Xmax, Ymin, Ymax` | Bounds for city coordinates              | -1000, 1000   |
| `n_iter`                 | Maximum number of generations            | 1000          |
| `n_pop`                  | Population size                          | 1000          |
| `r_mut`                  | Mutation probability                     | 0.1           |
| `elite_percent`          | Percentage of elite individuals retained | 0.4           |
| `tolerance`              | Threshold for early stopping             | 0.000001      |

## Output

The algorithm prints the best solution and distance found:

```
> Generation X, new best f([...]) = Y
Best solution: [...]
Best score: Z
```

Additionally, an animated visualization of the optimization process is saved as:

```
tsp_animation.gif
```

This animation showcases the evolution of the best path over generations.

## Visualization of Optimization

The algorithm generates an **animated GIF** (`tsp_animation.gif`) that visually demonstrates how the best route evolves over generations. The image shows how the paths improve, converging to a near-optimal solution.

## Example Output

After running the script, you might see:

```
Best solution: [0, 3, 7, ..., 1]
Best score: 4520.67
Animation saved as tsp_animation.gif
```

## Notes

- The algorithm uses **elitism** to preserve top solutions across generations.
- The **early stopping mechanism** prevents unnecessary computation if no significant improvement occurs.
- The **mutation rate** balances exploration and exploitation.

## License

This project is licensed under the **MIT License**. It is open-source and available for modification and enhancement.

