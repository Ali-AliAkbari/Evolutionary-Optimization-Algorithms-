# Moth-Flame Optimization (MFO) Algorithm Visualization

This repository contains an implementation of the Moth-Flame Optimization (MFO) algorithm with a visualization of the moth and flame movement over iterations. The solution is shown through a contour plot, where moths and flames are distinctly marked with different colors, and a GIF animation is created to visualize their movement through the optimization space.

## Description

Moth-Flame Optimization (MFO) is an optimization algorithm inspired by the flight behavior of moths. This repository implements the MFO algorithm for a simple 2D optimization problem (minimizing the sum of squares). The algorithm generates moths and flames, with moths representing potential solutions, and flames representing the best solutions.

The algorithm's behavior is visualized by:
- Plotting the movement of moths and flames at each iteration.
- Saving the iteration steps into an animated GIF.

## Features
- **MFO Algorithm**: Solves an optimization problem using moths and flames.
- **Visualization**: Moths and flames are displayed on a contour plot.
- **GIF Creation**: A GIF is generated to showcase the optimization progress.

## Requirements

To run this code, you need the following libraries:

- `numpy` for numerical operations.
- `matplotlib` for plotting and visualization.
- `PIL` (Pillow) for creating GIFs.

You can install the required libraries with pip:

```bash
pip install numpy matplotlib pillow
```

## Code Overview

### **Objective Function**
The objective function is a simple sum of squares (L2 norm squared):

```python
def objective_function(X):
    return np.sum(X**2, axis=1)
```

### **MFO Algorithm**
The main function `MFO` simulates the moth-flame behavior, updating moths' positions over time to optimize the objective function.

```python
def MFO(nw, dim, iter, xMin, xMax):
    # MFO algorithm code here
```

### **GIF Creation**
The `create_gif` function generates a GIF to visualize the optimization process:

```python
def create_gif(moth_path, flame_path, xMin, xMax, filename="MFO_movement.gif"):
    # GIF creation code here
```

## Example Usage

To run the MFO algorithm and generate the GIF, use the following code:

```python
# Set parameters for MFO
nw, dim, iter, xMin, xMax = 30, 2, 100, -5, 5

# Run MFO optimization
best_solution, moth_path, flame_path = MFO(nw, dim, iter, xMin, xMax)

# Generate and save GIF
create_gif(moth_path, flame_path, xMin, xMax)
```

The generated GIF will be saved as `MFO_movement.gif` by default.

## Results

The optimization process is shown in a GIF where:
- **Moths** are displayed in **white**.
- **Flames** are displayed in **orange**.
- The **Global Minimum** is marked with a **red 'X'**.

## Contributing

Feel free to fork this repository, open issues, or submit pull requests. Contributions are always welcome!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

