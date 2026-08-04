# Generated Prompt — Topic: Direct Methods & Applications

**Unit:** Unit 1 — Matrix Algebra and Linear Systems  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Direct Methods for Linear Systems — Cramer's Rule, Matrix Inversion Method, and Engineering Applications"**.

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
\lhead{Direct Methods \& Applications}
\rhead{Unit 1 — Matrix Algebra}
\cfoot{\thepage}

\title{\textbf{Direct Methods: Cramer's Rule, Matrix Inversion \& Engineering Applications} \\ \large Unit 1 — Matrix Algebra and Linear Systems}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: In robotics and control systems, the inverse kinematics problem — finding joint angles from an end-effector position — reduces to solving Ax = b where A is the Jacobian matrix of the robot arm. Using the matrix inversion method (x = A^{-1}b), a robot controller can compute target joint angles in real time. In electrical engineering, Cramer's rule elegantly gives mesh currents in a 2- or 3-mesh circuit without full row reduction — ideal for closed-form symbolic analysis. In chemical process engineering, matrix methods solve simultaneous material balance equations across multiple reactors.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- `booktabs` table:
  - Cramer's Rule → Exact closed-form solution → Best for n ≤ 3, symbolic work, theoretical proofs
  - Matrix Inversion → x = A^{-1}b → Ideal when same A is used for multiple RHS vectors b
  - Gauss Elimination → Row reduction → Best for general large systems, no closed form needed
  - Cramer's Rule for n > 4 → O(n! · n) operations → Computationally infeasible for large n
  - Matrix Inversion → O(n³) → Moderate cost, powerful for repeated solves
- `learnbox`: "Choose your method based on problem size, structure, and whether A changes — engineers must be pragmatic, not dogmatic."

### Section 3: Intuition First & Mathematical Definitions
- Intuition: If Ax = b and A is invertible, then x = A^{-1}b — just like dividing both sides in scalar algebra, but we must multiply by A^{-1} on the LEFT.
- `infobox` definitions:
  - Cramer's Rule: For Ax = b (n×n, det(A) ≠ 0): x_i = det(A_i) / det(A) where A_i is A with the i-th column replaced by b.
  - Matrix Inversion Method: x = A^{-1}b; A^{-1} = adj(A)/det(A)
  - Adjugate matrix: adj(A)_{ij} = C_{ji} (transpose of cofactor matrix)
  - Condition: det(A) ≠ 0 for unique solution (both methods)
  - Computational comparison: Cramer's Rule = n+1 determinants; Matrix inversion = cofactor matrix + one matrix multiplication

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (TikZ):** Cramer's Rule diagram for a 3×3 system: show matrix A, then A1, A2, A3 side by side with the replaced column highlighted in a different color. Label which column is replaced for each.
- **Visual 2 (TikZ):** Matrix inversion pipeline: A → cofactor matrix C → transpose → adj(A) → divide by det(A) → A^{-1} → multiply by b → x. Draw as a flowchart with matrix boxes and arrows.
- **Visual 3 (pgfplots or TikZ):** Method comparison chart — horizontal bar chart comparing computational complexity (operations count) for Cramer's, Matrix Inversion, and Gauss Elimination for n = 2, 3, 4. Use `pgfplots` `ybar` chart.

### Section 5: Step-by-Step Algorithmic Solution / Workflow

**Cramer's Rule Algorithm:**
1. Check det(A) ≠ 0; if det(A) = 0, method fails — use other approach.
2. Compute det(A) by cofactor expansion.
3. For each i = 1 to n:
   a. Form matrix A_i: replace column i of A with vector b.
   b. Compute det(A_i).
   c. x_i = det(A_i) / det(A).
4. Write solution vector x = [x1, x2, ..., xn]^T.

**Matrix Inversion Method Algorithm:**
1. Check det(A) ≠ 0.
2. Compute cofactor C_{ij} = (−1)^{i+j} M_{ij} for all i, j.
3. Form cofactor matrix C.
4. Adjugate: adj(A) = C^T.
5. A^{-1} = adj(A) / det(A).
6. Solution: x = A^{-1} · b (matrix-vector multiplication).
7. Verify: A · x = b.

### Section 6: Fully Worked Step-by-Step Numerical Examples

**Example 1 (Basic — Cramer's Rule, 2×2):**
Solve: 3x + 2y = 7, x − y = 1 using Cramer's rule.
- Compute det(A) = 3(−1) − 2(1) = −5.
- Form A1 (replace col 1 with b): det(A1) = 7(−1)−2(1) = −9 → x = −9/−5 = 9/5.
- Form A2 (replace col 2 with b): det(A2) = 3(1)−7(1) = −4 → y = −4/−5 = 4/5.
- Verify: 3(9/5) + 2(4/5) = 27/5 + 8/5 = 35/5 = 7 ✓.
`learnbox`: "Cramer's rule is elegant for 2×2 and 3×3 — beyond that, use Gauss elimination."

**Example 2 (Intermediate — Matrix Inversion, 3×3):**
Solve: 2x + y + z = 5, 4x − 6y = −2, −2x + 7y + 2z = 9 using the matrix inversion method.
- Write A and b. Compute det(A) by cofactor expansion — show all steps.
- Compute all 9 cofactors C_{11} to C_{33} — show each 2×2 determinant.
- Form cofactor matrix, then adj(A) = C^T.
- Compute A^{-1} = adj(A)/det(A). Show full fraction arithmetic.
- Compute x = A^{-1} · b — show matrix-vector multiplication step by step.
- Verify A · x = b.
`learnbox`: "The matrix inversion method is powerful when you need to solve Ax = b for many different b vectors with the same A."

**Example 3 (Applied Engineering — 3-Mesh Circuit Analysis):**
Three coupled mesh equations from Kirchhoff's Voltage Law give: 5I1 − 2I2 = 10, −2I1 + 6I2 − I3 = 0, −I2 + 4I3 = 8 (all in Ω and V). Solve for mesh currents I1, I2, I3 using Cramer's rule. Interpret each current physically (direction, magnitude relative to source voltage). Compute power delivered: P = I · V_source.
`learnbox`: "Cramer's rule gives mesh currents as clean fractions — ideal for symbolic analysis of circuits."

### Section 7: Tabular Comparison / Workflow Reference

| Method | Formula | Pre-condition | Ops Complexity | When to Use |
|---|---|---|---|---|
| Cramer's Rule | x_i = det(A_i)/det(A) | det(A) ≠ 0 | O(n · n!) | n ≤ 3, symbolic |
| Matrix Inversion | x = A^{-1}b | det(A) ≠ 0 | O(n³) | Multiple b vectors |
| Gauss Elimination | Row reduce [A|b] | — | O(n³/3) | General, large n |
| Gauss-Jordan | RREF [A|b] | — | O(n³/2) | Small, hand calc |
| Iterative (GS/Jacobi) | x^{(k+1)} from x^{(k)} | Diag. dominant | O(k·n²) | Large sparse A |

### Section 8: Common Student Mistakes & Pitfalls

`mistakebox`:

| Mistake | Why Students Do It | Correct Approach |
|---|---|---|
| Replacing wrong column in Cramer's | Confusion about A_i index | For x_i, replace COLUMN i (not row i) with b |
| x = b · A^{-1} instead of x = A^{-1} · b | Scalar intuition | Matrix multiplication is NOT commutative — A^{-1} goes on the LEFT |
| Forgetting to transpose cofactor matrix | Missing the adjugate step | adj(A) = (cofactor matrix)^T — transpose first, then divide by det |
| Using Cramer's for 4×4 system | Not considering cost | Cramer's for n > 3 is computationally expensive — use Gauss |
| Not verifying solution after computation | Overconfidence | Always multiply A · x and check if it equals b |

### Section 9: Comprehensive Assessment Suite

**Viva-Voce (7 Questions):**
1. State Cramer's rule for a 3×3 system.
2. What is the adjugate of a matrix? How is it related to the inverse?
3. When does Cramer's rule fail? What should you do then?
4. Why is x = b · A^{-1} wrong?
5. For which scenario is the matrix inversion method more efficient than Gauss elimination?
6. What is the computational cost of Cramer's rule for a 5×5 system?
7. How do you verify that your computed A^{-1} is correct?

**Descriptive Problems (4):**
1. Solve a 3×3 system using Cramer's rule — show all cofactor determinants.
2. Find A^{-1} using the adjugate method and solve Ax = b.
3. Compare all three methods for a 3×3 circuit system — comment on efficiency.
4. An engineering system has 3 material balances — model as Ax = b and solve using matrix inversion.

**MCQs (5):** Cramer's formula, adjugate definition, computational cost, condition for existence, method selection.

### Section 10: Quick Recap & Formula Sheet

`learnbox` (8 bullets):
- Cramer's Rule: x_i = det(A_i)/det(A); replace i-th column of A with b to form A_i
- Matrix Inversion: x = A^{-1}b = [adj(A)/det(A)]·b
- adj(A) = transpose of cofactor matrix (NOT cofactor matrix itself)
- A^{-1} exists iff det(A) ≠ 0 (non-singular matrix)
- Always left-multiply: x = A^{-1}·b, NOT b·A^{-1}
- Cramer's is O(n·n!) — impractical for n > 3 numerically
- Matrix inversion is O(n³) — efficient for multiple RHS vectors
- Always verify: compute A·x and confirm it equals b

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] Cramer's rule determinant computations show FULL cofactor expansion — no shortcuts.
- [ ] Matrix inversion: all 9 cofactors computed individually with 2×2 determinant shown.
- [ ] TikZ flowchart for inversion pipeline must be properly spaced and labeled.
- [ ] pgfplots bar chart uses valid coordinates and axis labels.
- [ ] Verify step (A·x = b) included in all three worked examples.
- [ ] All tcolorboxes closed; `\begin{document}...\end{document}` wraps everything.
