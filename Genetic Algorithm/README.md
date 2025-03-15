# Solve the Traveling Salesman Problem (TSP) with a Genetic Algorithm

## What’s This About?

This project uses a **Genetic Algorithm (GA)** to find an efficient route for the **Traveling Salesman Problem (TSP)**. Instead of checking every possible path (which would take forever), GA **evolves** solutions over time, mimicking natural selection to get better results with each generation.

## What’s the Traveling Salesman Problem (TSP)?

Imagine a salesperson who needs to visit several cities, but they can only visit each city **once** before returning to where they started. The challenge? **Finding the shortest possible route.**

TSP is more than just a math puzzle—it has real-world applications like:

- **Optimizing delivery routes** 🚚
- **Reducing wiring in circuit boards** 🛠️
- **Planning paths for robots** 🤖
- **Genome sequencing** 🧬

Since it’s an **NP-hard** problem, meaning there’s no quick way to get an exact solution for large datasets, we use algorithms like GA to get near-optimal solutions efficiently.

## How Does a Genetic Algorithm (GA) Work?

GA is inspired by evolution: survival of the fittest. It finds good solutions through:

1. **Starting with random routes**
2. **Evaluating their fitness (shorter routes are better)**
3. **Selecting the best routes as parents**
4. **Combining them to create new routes (crossover)**
5. **Mutating some routes to keep diversity**
6. **Repeating the process until the best route stabilizes**

### Why Use GA for TSP?

- **It explores a huge solution space efficiently** 🌎
- **It avoids getting stuck in local optima** 🚀
- **It works well for different versions of TSP** 🛤️

## Requirements

Install dependencies using:

```bash
pip install numpy matplotlib
```

## How to Run

Run the script to start optimizing the TSP solution:

```python
python genetic_algorithm_tsp.py
```

### Key Parameters

| Parameter  | Description | Default |
|------------|-------------|----------|
| `n_cities` | Number of cities | 30 |
| `Xmin, Xmax, Ymin, Ymax` | City coordinate range | -1000, 1000 |
| `n_iter` | Max generations | 1000 |
| `n_pop` | Population size | 1000 |
| `r_mut` | Mutation probability | 0.1 |
| `elite_percent` | Top solutions retained | 0.4 |
| `tolerance` | Early stopping threshold | 0.000001 |

## What You Get

Once the script runs, it prints the best route and its distance:

```
> Generation X, new best f([...]) = Y
Best solution: [...]
Best score: Z
```

It also generates an **animated visualization** (`tsp_animation.gif`) showing how the route improves over generations.

## Example Output

```
Best solution: [0, 3, 7, ..., 1]
Best score: 4520.67
Animation saved as tsp_animation.gif
```

## Notes

- **Elitism** ensures top solutions are carried forward.
- **Early stopping** prevents unnecessary computation.
- **Mutation rate** keeps the search diverse and avoids getting stuck.

## License

This project is licensed under the **MIT License**. Modify and enhance it as you like!

