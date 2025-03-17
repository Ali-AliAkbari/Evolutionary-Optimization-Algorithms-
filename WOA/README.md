GitHub's Markdown rendering does not natively support LaTeX equations, which is why your equations are not displaying correctly. To display equations properly on GitHub, you can use one of the following workarounds:

---

### **1. Use Images for Equations**
Convert your equations into images (e.g., PNG or SVG) and embed them in your README file. You can use tools like [LaTeXiT](https://www.chachatelier.fr/latexit/) or online LaTeX editors (e.g., [Overleaf](https://www.overleaf.com/)) to generate images of your equations.

Example:
```markdown
![Equation 1](https://latex.codecogs.com/png.image?\vec{D}&space;=&space;|\vec{C}&space;\cdot&space;\vec{X}_{rand}&space;-&space;\vec{X}|)
```

---

### **2. Use Codecogs or Other Online Renderers**
You can use an online LaTeX renderer like [CodeCogs](https://www.codecogs.com/latex/eqneditor.php) to generate URLs for your equations. These URLs can then be embedded as images in your README.

Example:
```markdown
![Equation 1](https://latex.codecogs.com/png.image?\vec{D}&space;=&space;|\vec{C}&space;\cdot&space;\vec{X}_{rand}&space;-&space;\vec{X}|)

![Equation 2](https://latex.codecogs.com/png.image?\vec{X}_{t&plus;1}&space;=&space;\vec{X}_{rand}&space;-&space;\vec{A}&space;\cdot&space;\vec{D})
```

---

### **3. Use Plain Text with Markdown Formatting**
If you don't want to use images, you can format the equations as plain text with Markdown formatting for clarity. While this won't look as polished as LaTeX, it will be readable.

Example:
```markdown
- **Equation 1**: D = |C · X_rand - X|
- **Equation 2**: X_{t+1} = X_rand - A · D
```

---

### **4. Use GitHub's Math Support (Experimental)**
GitHub has limited support for math rendering using `$$` for block equations and `$` for inline equations. However, this is not fully reliable across all platforms. You can try it, but results may vary.

Example:
```markdown
$$
\vec{D} = |\vec{C} \cdot \vec{X}_{rand} - \vec{X}|
$$

$$
\vec{X}_{t+1} = \vec{X}_{rand} - \vec{A} \cdot \vec{D}
$$
```

---

### **Updated README with Workaround**

Here’s how you can rewrite your README using the **CodeCogs image method**:

---

# **Whale Optimization Algorithm (WOA) - Benchmark Functions**

## **1️⃣ Overview of WOA**

The **Whale Optimization Algorithm (WOA)** is a **nature-inspired metaheuristic optimization algorithm** introduced by **Seyedali Mirjalili** in 2016. It is inspired by the **hunting behavior of humpback whales**, specifically their **bubble-net feeding strategy**. 

Humpback whales hunt by creating a spiral movement around their prey, trapping it within a shrinking circle before attacking. WOA mathematically models this behavior to solve **optimization problems** by iteratively refining solutions within a search space.

## **2️⃣ How WOA Works**

The WOA simulates the whale's hunting strategy through three primary operations:

### **A. Encircling Prey (Exploitation)**

Whales identify the best candidate solution (prey) and update their positions relative to it:

![Equation 1](https://latex.codecogs.com/png.image?\vec{D}&space;=&space;|\vec{C}&space;\cdot&space;\vec{X}^{*}&space;-&space;\vec{X}|)

![Equation 2](https://latex.codecogs.com/png.image?\vec{X}_{t&plus;1}&space;=&space;\vec{X}^{*}&space;-&space;\vec{A}&space;\cdot&space;\vec{D})

Where:  
- \( \vec{X^*} \) is the best solution found so far (prey).  
- \( \vec{X} \) represents the whale’s current position.  
- \( \vec{A} \) and \( \vec{C} \) are coefficient vectors controlling convergence.  

### **B. Spiral Update (Exploitation)**

If the probability \( p \geq 0.5 \), the whale follows a **spiral path** instead of direct encircling:

![Equation 3](https://latex.codecogs.com/png.image?\vec{X}_{t&plus;1}&space;=&space;\vec{X}^{*}&space;&plus;&space;D&space;\cdot&space;e^{bl}&space;\cdot&space;\cos(2\pi&space;l))

Where:  
- \( b \) controls the spiral shape.  
- \( l \) is a random number in **[-1,1]**.  

### **C. Search for Prey (Exploration)**

To maintain diversity and avoid local optima, whales **randomly explore the search space**:

![Equation 4](https://latex.codecogs.com/png.image?\vec{D}&space;=&space;|\vec{C}&space;\cdot&space;\vec{X}_{rand}&space;-&space;\vec{X}|)

![Equation 5](https://latex.codecogs.com/png.image?\vec{X}_{t&plus;1}&space;=&space;\vec{X}_{rand}&space;-&space;\vec{A}&space;\cdot&space;\vec{D})

Where \( \vec{X}_{rand} \) is a **random whale**.

---

This approach ensures your equations are displayed correctly on GitHub. Let me know if you need further assistance!
