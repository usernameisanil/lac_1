# Generated Prompt — Topic: Iterative Methods (Jacobi & Gauss-Seidel)

**Unit:** Unit 1 — Matrix Algebra and Linear Systems  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Iterative Methods for Linear Systems — Jacobi Method and Gauss-Seidel Method"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 1. LATEX PREAMBLE & CONFIGURATION REQUIREMENTS

```latex
\documentclass[12pt,a4paper]{article}
\usepackage{amsmath, amssymb, geometry, booktabs, xcolor, hyperref,
            listings, pgfplots, tcolorbox, enumitem, fancyhdr, tikz, array}
\usepgfplotslibrary{fillbetween}
\geometry{margin=2.5cm}
\pgfplotsset{compat=1.18}
\tcbuselibrary{skins, breakable}

\newtcolorbox{curiositybox}[1][]{colback=yellow!10, colframe=orange!80, title=#1, breakable}
\newtcolorbox{infobox}[1][]{colback=blue!5, colframe=blue!60, title=#1, breakable}
\newtcolorbox{mistakebox}[1][]{colback=red!5, colframe=red!60, title=#1, breakable}
\newtcolorbox{learnbox}[1][]{colback=green!5, colframe=green!60, title=#1, breakable}

\pagestyle{fancy}
\fancyhf{}
\lhead{Iterative Methods}
\rhead{Unit 1 — Matrix Algebra}
\cfoot{\thepage}

\title{\textbf{Iterative Methods: Jacobi and Gauss-Seidel for Linear Systems} \\ \large Unit 1 — Matrix Algebra and Linear Systems}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: In large-scale power system simulations (e.g., IEEE 118-bus power network), solving the nodal equations directly using Gauss elimination requires inverting matrices of order 118×118 — computationally expensive and numerically unstable. Iterative methods like Gauss-Seidel are the backbone of **load flow analysis** in power systems. They start from an initial guess (flat start: V = 1∠0° at all buses) and iteratively converge to the actual operating voltages. Also used in: heat conduction finite difference solvers, PageRank computation by Google, and large FEA problems.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- `booktabs` table:
  - Jacobi: Uses old values for all unknowns in each iteration → Slower convergence → Safe for parallel computation
  - Gauss-Seidel: Uses updated values immediately → Faster convergence → Standard for power systems
  - Direct methods: Exact solution → Expensive for large n
  - Iterative methods: Approximate but cheap per iteration → Scales to n = millions
- `learnbox`: "When matrices are large and sparse (mostly zeros), iterative methods are faster, cheaper, and the industry standard."

### Section 3: Intuition First & Mathematical Definitions
- Intuition: Imagine guessing the answer, checking the error, and correcting — like tuning a guitar string by ear. Each iteration brings you closer.
- `infobox` definitions:
  - Diagonally Dominant condition: |a_{ii}| > Σ_{j≠i} |a_{ij}| → sufficient condition for convergence
  - Jacobi iteration formula: x_i^{(k+1)} = (1/a_{ii}) [b_i − Σ_{j≠i} a_{ij} x_j^{(k)}]
  - Gauss-Seidel iteration formula: x_i^{(k+1)} = (1/a_{ii}) [b_i − Σ_{j<i} a_{ij} x_j^{(k+1)} − Σ_{j>i} a_{ij} x_j^{(k)}]
  - Convergence criterion: ||x^{(k+1)} − x^{(k)}|| < ε (tolerance)
  - Matrix splitting form: Jacobi: x^{(k+1)} = D^{-1}(b − (L+U)x^{(k)}); Gauss-Seidel: x^{(k+1)} = (D+L)^{-1}(b − Ux^{(k)})

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** Convergence plot — x-axis: iteration number (0 to 10), y-axis: value of x1 converging to true solution. Plot Jacobi curve (slower) and Gauss-Seidel curve (faster) on the same axes with different colors and a horizontal dashed line at the exact solution. Add legend, grid, axis labels.
- **Visual 2 (TikZ):** Side-by-side comparison of one iteration step:
  - Jacobi: All three variables updated simultaneously using ONLY old values (show arrows from iteration k to k+1 all from old values).
  - Gauss-Seidel: x1 updated first using old x2, x3; then x2 updated using NEW x1 and old x3; etc. (show dependency arrows).
- **Visual 3 (TikZ):** Diagonal dominance illustration — draw a 3×3 matrix, circle diagonal entries, show |a_{ii}| vs. sum of |a_{ij}| for each row with a mini bar comparison.

### Section 5: Step-by-Step Algorithmic Solution / Workflow

**Jacobi Method Algorithm:**
1. Rearrange: write x_i = (1/a_{ii})[b_i − Σ_{j≠i} a_{ij} x_j] for each i.
2. Check diagonal dominance: |a_{ii}| > Σ_{j≠i} |a_{ij}| for all i.
3. Start with initial guess x^{(0)} = [0, 0, ..., 0]^T.
4. For k = 0, 1, 2, ...: Compute ALL x_i^{(k+1)} using ONLY x^{(k)} values.
5. Check convergence: max|x_i^{(k+1)} − x_i^{(k)}| < ε. If yes, stop.

**Gauss-Seidel Method Algorithm:**
1. Same setup and diagonal dominance check.
2. For k = 0, 1, 2, ...: Update x_1^{(k+1)} first using old x_2^{(k)}, x_3^{(k)}. Update x_2^{(k+1)} using NEW x_1^{(k+1)} and old x_3^{(k)}. Continue for all i.
3. Check convergence after each full sweep.

### Section 6: Fully Worked Step-by-Step Numerical Examples

**Example 1 (Basic — Jacobi, 3×3, 3 Iterations):**
Solve: 4x1 + x2 − x3 = 5, 2x1 + 7x2 + x3 = 19, x1 − 3x2 + 12x3 = 22.
- First verify diagonal dominance for each row.
- Write Jacobi formulas for x1, x2, x3 explicitly.
- Start: x^{(0)} = (0, 0, 0).
- Perform 3 complete iterations. Show all arithmetic for every variable at every iteration in a table.
- Compare with exact solution.
`learnbox`: "Jacobi updates ALL variables simultaneously — use old values for everything in one iteration."

**Example 2 (Intermediate — Gauss-Seidel, Same System, Faster Convergence):**
Solve the same system using Gauss-Seidel. Perform 3 iterations.
- Show how x1 is updated first, then x2 uses the NEW x1, then x3 uses NEW x1 and x2.
- Create a comparison table: Iteration | Jacobi x1 | GS x1 | Jacobi x2 | GS x2 | Jacobi x3 | GS x3 | Exact.
- Demonstrate that Gauss-Seidel converges in fewer iterations.
`learnbox`: "Gauss-Seidel converges roughly twice as fast as Jacobi by using updated values immediately."

**Example 3 (Applied — Heat Conduction Finite Difference):**
A 1D heat conduction problem with 3 interior nodes gives: 2T1 − T2 = 50, −T1 + 2T2 − T3 = 0, −T2 + 2T3 = 30 (T in °C). Apply Gauss-Seidel to find node temperatures T1, T2, T3. Run until max change < 0.01°C. Interpret the converged temperatures physically.
`learnbox`: "Iterative solvers are the engine of finite difference and finite element heat transfer simulations."

### Section 7: Tabular Comparison / Workflow Reference

| Feature | Jacobi | Gauss-Seidel |
|---|---|---|
| Values used in iteration | Only old (k-th) | Mix of new and old |
| Convergence speed | Slower | Faster (≈2× Jacobi) |
| Convergence condition | Diagonal dominance | Diagonal dominance (weaker requirement) |
| Parallelizable | Yes (all updates independent) | No (sequential dependency) |
| Memory requirement | Needs two arrays | One array (in-place update) |
| Application | Parallel processors | Power systems, heat solvers |

### Section 8: Common Student Mistakes & Pitfalls

`mistakebox`:

| Mistake | Why Students Do It | Correct Approach |
|---|---|---|
| Using updated values in Jacobi | Confusing with Gauss-Seidel | Jacobi uses ONLY x^{(k)} for computing x^{(k+1)} |
| Not checking diagonal dominance | Skipping precondition | Always rearrange to ensure |a_{ii}| > Σ|a_{ij}| |
| Wrong convergence criterion | Using only one variable | Check max change across ALL variables |
| Giving up after 3 iterations | Impatience | Continue until ||x^{(k+1)}−x^{(k)}|| < ε |
| Not rearranging equations | Applying directly | Always isolate the diagonal variable first |

### Section 9: Comprehensive Assessment Suite

**Viva-Voce (7 Questions):**
1. What is diagonal dominance and why is it important for iterative methods?
2. How does Gauss-Seidel differ from Jacobi in updating strategy?
3. What is the convergence criterion for iterative methods?
4. Can iterative methods fail to converge? Give conditions.
5. Why are iterative methods preferred over direct methods for large sparse systems?
6. What is the initial guess typically used and why?
7. Which method — Jacobi or Gauss-Seidel — is better suited for parallel computing and why?

**Descriptive Problems (4):**
1. Apply Jacobi to a given 3×3 diagonally dominant system for 4 iterations.
2. Apply Gauss-Seidel to the same system, compare convergence rate.
3. Verify diagonal dominance of a matrix; rearrange rows if needed.
4. Solve a 3-node temperature distribution problem using Gauss-Seidel.

**MCQs (5):** Convergence condition, Jacobi vs GS update rule, stopping criterion, diagonal dominance, application domain.

### Section 10: Quick Recap & Formula Sheet

`learnbox` (8 bullets):
- Diagonal dominance: |a_{ii}| > Σ_{j≠i}|a_{ij}| — sufficient (not necessary) for convergence
- Jacobi: x_i^{(k+1)} = (b_i − Σ_{j≠i}a_{ij}x_j^{(k)}) / a_{ii}
- Gauss-Seidel: Use updated x_j^{(k+1)} for j < i in same iteration
- Gauss-Seidel converges ≈ 2× faster than Jacobi for same system
- Convergence check: max_i|x_i^{(k+1)} − x_i^{(k)}| < ε
- Start with x^{(0)} = 0 (zero vector) unless better guess available
- Best for large, sparse, diagonally dominant systems
- Applications: power load flow, FEA heat/structural, Google PageRank

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] Iteration tables must use `tabular` or `array` environments — clearly labeled columns.
- [ ] pgfplots convergence plot: axis ranges, legend, grid, proper coordinates.
- [ ] Jacobi and Gauss-Seidel formulas in separate `infobox` environments for clarity.
- [ ] Diagonal dominance verification shown numerically for all examples.
- [ ] All tcolorboxes closed; document wrapped in `\begin{document}...\end{document}`.
