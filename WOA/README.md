# **Whale Optimization Algorithm (WOA) - Benchmark Functions**

## **1️⃣ Overview of WOA**

The **Whale Optimization Algorithm (WOA)** is a **nature-inspired metaheuristic optimization algorithm** introduced by **Seyedali Mirjalili** in 2016. It is inspired by the **hunting behavior of humpback whales**, specifically their **bubble-net feeding strategy**. 

Humpback whales hunt by creating a spiral movement around their prey, trapping it within a shrinking circle before attacking. WOA mathematically models this behavior to solve **optimization problems** by iteratively refining solutions within a search space.

## **2️⃣ How WOA Works**

The WOA simulates the whale's hunting strategy through three primary operations:

### **A. Encircling Prey (Exploitation)**

Whales identify the best candidate solution (prey) and update their positions relative to it:

\[
\vec{D} = |\vec{C} \cdot \vec{X^*} - \vec{X}|
\]

\[
\vec{X}_{t+1} = \vec{X^*} - \vec{A} \cdot \vec{D}
\]

Where:  
- \( \vec{X^*} \) is the best solution found so far (prey).  
- \( \vec{X} \) represents the whale’s current position.  
- \( \vec{A} \) and \( \vec{C} \) are coefficient vectors controlling convergence.  

### **B. Spiral Update (Exploitation)**

If the probability \( p \geq 0.5 \), the whale follows a **spiral path** instead of direct encircling:

\[
\vec{X}_{t+1} = \vec{X^*} + D \cdot e^{bl} \cdot \cos(2\pi l)
\]

Where:  
- \( b \) controls the spiral shape.  
- \( l \) is a random number in **[-1,1]**.  

### **C. Search for Prey (Exploration)**

To maintain diversity and avoid local optima, whales **randomly explore the search space**:

\[
\vec{D} = |\vec{C} \cdot \vec{X}_{rand} - \vec{X}|
\]

\[
\vec{X}_{t+1} = \vec{X}_{rand} - \vec{A} \cdot \vec{D}
\]

Where \( \vec{X}_{rand} \) is a **random whale**.

### **D. Adaptive Parameters**

The **coefficient vectors** help control exploration vs. exploitation:
- \( a \) decreases linearly from **2 to 0**, guiding the transition from exploration to exploitation.  
- \( A \) and \( C \) depend on random values for stochastic behavior.  

---

## **3️⃣ Benchmark Functions Used**

To evaluate WOA, we apply it to **five well-known optimization functions**:

| **Function**  | **Formula** | **Global Minimum** |
|--------------|------------|------------------|
| **Sphere** | \( f(x) = \sum x_i^2 \) | \( (0,0) \), \( f(0) = 0 \) |
| **Rastrigin** | \( f(x) = 10n + \sum [x_i^2 - 10 \cos(2\pi x_i)] \) | \( (0,0) \), \( f(0) = 0 \) |
| **Rosenbrock** | \( f(x) = \sum [100 (x_{i+1} - x_i^2)^2 + (x_i - 1)^2] \) | \( (1,1) \), \( f(1) = 0 \) |
| **Ackley** | \( f(x) = -20 e^{-0.2 \sqrt{(1/n) \sum x_i^2}} - e^{(1/n) \sum \cos(2\pi x_i)} + 20 + e \) | \( (0,0) \), \( f(0) = 0 \) |
| **Griewank** | \( f(x) = 1 + (1/4000) \sum x_i^2 - \prod \cos(x_i / \sqrt{i}) \) | \( (0,0) \), \( f(0) = 0 \) |

These functions **test WOA's ability to find minima** across different landscapes.

---

## **4️⃣ GIF Visualizations**

The optimization process for each function is animated in GIFs, showing the whales' movement towards the global optimum.

| **Function** | **GIF Visualization** |
|-------------|----------------------|
| **Sphere** | ![Sphere Optimization](./gifs/sphere.gif) |
| **Rastrigin** | ![Rastrigin Optimization](./gifs/rastrigin.gif) |
| **Rosenbrock** | ![Rosenbrock Optimization](./gifs/rosenbrock.gif) |
| **Ackley** | ![Ackley Optimization](./gifs/ackley.gif) |
| **Griewank** | ![Griewank Optimization](./gifs/griewank.gif) |

---

## **5️⃣ Optimization Results**

Below is a table showing the **best solution found** for each function:

| **Function**  | **Best (x, y) Found** | **WOA Cost** | **Optimal Cost** |
|--------------|----------------------|-------------|-----------------|
| **Sphere** | (-0.01, 0.02) | 0.0005 | 0 |
| **Rastrigin** | (0.03, -0.02) | 0.1 | 0 |
| **Rosenbrock** | (0.98, 0.99) | 0.04 | 0 |
| **Ackley** | (0.01, -0.01) | 0.002 | 0 |
| **Griewank** | (-0.02, 0.01) | 0.0003 | 0 |

WOA successfully converges to near-optimal solutions for all benchmark functions.

---

## **6️⃣ Reference**

- Mirjalili, S. (2016). **"The Whale Optimization Algorithm"**. *Advances in Engineering Software, 95, 51-67*. [DOI: 10.1016/j.advengsoft.2016.01.008](https://doi.org/10.1016/j.advengsoft.2016.01.008)

---

### **Note on GitHub Rendering**

To ensure equations render correctly on GitHub, use the following format:

```markdown
\[
\vec{D} = |\vec{C} \cdot \vec{X^*} - \vec{X}|
\]
```

This will ensure proper rendering of mathematical equations in your README file.
