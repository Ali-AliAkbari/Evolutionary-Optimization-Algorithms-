# Moth-Flame Optimization (MFO)

This project implements the **Moth-Flame Optimization (MFO) algorithm**, a nature-inspired metaheuristic optimization technique designed to solve complex optimization problems. The algorithm mimics the navigation behavior of moths, which use a logarithmic spiral flying pattern toward light sources. In the MFO algorithm, a set of moths explores the search space, while flames (elite solutions) guide them toward better solutions. Over iterations, moths converge to optimal or near-optimal solutions.

This implementation is based on the original MFO paper, ensuring an accurate representation of the algorithm's principles and behavior. The algorithm is tested on five well-known benchmark functions: **Griewank, Rastrigin, Sphere, Rosenbrock, and Ackley functions**. The optimization process is visualized using GIFs that show the movement of moths towards flames during the optimization.

## Algorithm Explanation
The Moth-Flame Optimization (MFO) algorithm is inspired by the natural behavior of moths navigating using a transverse orientation mechanism. The mathematical model behind the algorithm consists of three main components:

1. **Moth Movement**: Each moth follows a logarithmic spiral path towards a flame (elite solution) in the search space. The movement is defined as:

   ```
   S(M_i, F_j) = D_i * e^(b * t) * cos(2πt) + F_j
   ```
   
   where:
   - `S(M_i, F_j)` is the new position of moth `M_i` moving towards flame `F_j`,
   - `D_i` is the distance between the moth and the flame, calculated as `|F_j - M_i|`,
   - `b` is a constant defining the shape of the logarithmic spiral,
   - `t` is a random number in `[-1, 1]`,
   - `F_j` is the position of the flame.

2. **Flame Update Mechanism**: Flames represent the best solutions found so far. In each iteration, the number of flames decreases to emphasize exploitation in later stages of optimization:

   ```
   N_f = round(N - (t * (N - 1)) / T)
   ```
   
   where:
   - `N_f` is the number of flames,
   - `N` is the total number of moths,
   - `t` is the current iteration number,
   - `T` is the maximum number of iterations.

3. **Exploration and Exploitation**: The search is balanced between exploration (searching new areas) and exploitation (refining known good areas) by dynamically adjusting the number of flames and moth movement patterns.

## Benchmark Functions
The objective functions used in this project are:

1. **Griewank Function**
2. **Rastrigin Function**
3. **Sphere Function**
4. **Rosenbrock Function**
5. **Ackley Function**

For more details about these benchmark functions, visit the [WOA page](https://github.com/Ali-AliAkbari/Evolutionary-Optimization-Algorithms-/tree/main/WOA).

## Results Table

| Function Name       | Best Solution                         | Cost                      |
|---------------------|---------------------------------------|---------------------------|
| Griewank Function   | [-0.00012325, 0.00037966]             | 4.367143913164284e-08     |
| Rastrigin Function  | [8.49387704e-07, -8.99559405e-07]     | 3.036717544091516e-10     |
| Sphere Function     | [3.29224425e-06, -7.34607905e-06]     | 6.480374959209336e-11     |
| Rosenbrock Function | [1.0, 1.0]                            | 3.2405872918652843e-22    |
| Ackley Function     | [-5.34234115e-11, 1.07229060e-10]     | 3.3884761663216523e-10    |

## GIF Visualizations
GIFs illustrating the optimization process for each function are generated. These visualizations show how moths move towards the best solutions over iterations.

<table align="center">
  <tr>
    <td align="center"><strong>Sphere</strong></td>
    <td align="center"><strong>Rastrigin</strong></td>
  </tr>
  <tr>
    <td align="center"><img src="./Images/Sphere Function.gif" width="250" height="200" alt="Sphere Optimization"></td>
    <td align="center"><img src="./Images/Rastrigin Function.gif" width="250" height="200" alt="Rastrigin Optimization"></td>
  </tr>
  <tr>
    <td align="center"><strong>Rosenbrock</strong></td>
    <td align="center"><strong>Ackley</strong></td>
  </tr>
  <tr>
    <td align="center"><img src="./Images/Rosenbrock Function.gif" width="250" height="200" alt="Rosenbrock Optimization"></td>
    <td align="center"><img src="./Images/Ackley Function.gif" width="250" height="200" alt="Ackley Optimization"></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><strong>Griewank</strong></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><img src="./Images/Griewank Function.gif" width="250" height="200" alt="Griewank Optimization"></td>
  </tr>
</table>

## References

For the original MFO algorithm paper and theoretical foundation, please refer to the following work:

**Mirjalili, S. (2015). Moth-flame optimization algorithm: A novel nature-inspired heuristic paradigm. Knowledge-Based Systems, 89, 228-249.**

## 📜 License  

This project is licensed under the **MIT License**, allowing free use, modification, and distribution.  

## 🤝 Get in Touch  

Feel free to reach out if you have any questions or are interested in collaboration! 🚀
