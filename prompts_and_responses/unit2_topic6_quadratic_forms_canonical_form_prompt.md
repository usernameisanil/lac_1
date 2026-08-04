# Generated Prompt — Topic: Quadratic Forms and Canonical Form

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Quadratic Forms and Canonical Form (Reduction by Orthogonal Transformation)"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 1. LATEX PREAMBLE & CONFIGURATION REQUIREMENTS

The generated LaTeX document MUST start with this exact preamble and environment definitions:

```latex
\documentclass[12pt,a4paper]{article}
\usepackage{amsmath, amssymb, geometry, booktabs, xcolor, hyperref,
            listings, pgfplots, tcolorbox, enumitem, fancyhdr, tikz, array}
\usepgfplotslibrary{fillbetween}
\geometry{margin=2.5cm}
\pgfplotsset{compat=1.18}
\tcbuselibrary{skins, breakable}

% Define custom environments
\newtcolorbox{curiositybox}[1][]{colback=yellow!10, colframe=orange!80, title=#1, breakable}
\newtcolorbox{infobox}[1][]{colback=blue!5, colframe=blue!60, title=#1, breakable}
\newtcolorbox{mistakebox}[1][]{colback=red!5, colframe=red!60, title=#1, breakable}
\newtcolorbox{learnbox}[1][]{colback=green!5, colframe=green!60, title=#1, breakable}

% Header and Footer
\pagestyle{fancy}
\fancyhf{}
\lhead{Quadratic Forms \& Canonical Form}
\rhead{Unit 2 — Quadratic Forms}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Quadratic Forms and Canonical Form} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence:

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Finite Element Analysis (FEA) and stress tensors** — the stress state at a point in a structural component is described by a quadratic form $Q = \mathbf{x}^T A \mathbf{x}$ (the strain energy). Reducing this to canonical form (sum of squares) reveals the principal stresses (eigenvalues) and principal directions (eigenvectors). Engineers use this to find the maximum stress direction and prevent material failure.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- `booktabs` table: quadratic form theory vs. applications in stress/strain analysis, conic section classification (ellipse/hyperbola/parabola), optimisation of objective functions, covariance matrices in statistics, energy functions in physics.
- Conclude with `learnbox`.

### Section 3: Intuition First & Mathematical Definitions
- Intuition: A quadratic form is a polynomial with all degree-2 terms. Cross terms (like $2xy$) make it hard to analyse — the canonical form eliminates cross terms so each variable contributes independently.
- `infobox` definitions:
  - Quadratic form: $Q(\mathbf{x}) = \mathbf{x}^T A \mathbf{x}$ where $A$ is real symmetric
  - General form for 2 variables: $Q = ax^2 + 2hxy + by^2$, matrix $A = \begin{pmatrix} a & h \\ h & b \end{pmatrix}$
  - General form for 3 variables: $Q = a_1x_1^2 + a_2x_2^2 + a_3x_3^2 + 2a_{12}x_1x_2 + 2a_{13}x_1x_3 + 2a_{23}x_2x_3$
  - Canonical (normal) form: $Q = \lambda_1 y_1^2 + \lambda_2 y_2^2 + \lambda_3 y_3^2$ (no cross terms)
  - Orthogonal transformation: $\mathbf{x} = P\mathbf{y}$ where $P$ is orthogonal ($P^T = P^{-1}$), $P^TAP = D$
  - Nature of quadratic form determined by signs of eigenvalues

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** Plot level curves (contours) of a quadratic form $Q = 5x^2 + 2xy + 5y^2 = c$ for $c = 1, 4, 9$ as ellipses in the $xy$-plane. Show the principal axes (eigenvectors) as dashed arrows superimposed.
- **Visual 2 (TikZ):** Side-by-side diagrams showing original tilted ellipse (cross-term present) vs. axis-aligned ellipse (canonical form, no cross-term) after orthogonal transformation, with axis labels $x,y$ and $y_1, y_2$.
- Both visuals must compile with `samples=100`, proper grid, axis labels, legend.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow — Reduction to Canonical Form by Orthogonal Transformation:
1. Write the quadratic form $Q$ and identify the symmetric matrix $A$
2. Find eigenvalues $\lambda_1, \ldots, \lambda_n$ of $A$ (solve $\det(A-\lambda I)=0$)
3. For each $\lambda_i$, find the eigenvector $\mathbf{v}_i$
4. Normalise each eigenvector: $\hat{\mathbf{v}}_i = \mathbf{v}_i / \|\mathbf{v}_i\|$
5. Form orthogonal matrix $P = [\hat{\mathbf{v}}_1 | \hat{\mathbf{v}}_2 | \ldots]$ — verify $P^T P = I$
6. Apply transformation $\mathbf{x} = P\mathbf{y}$: canonical form is $Q = \lambda_1 y_1^2 + \lambda_2 y_2^2 + \ldots$
7. Determine nature: all positive → positive definite; all negative → negative definite; mixed → indefinite

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide **THREE** examples:
- **Example 1 (2×2 Basic):** $Q = 3x^2 + 4xy + 3y^2$. Find matrix $A$, eigenvalues, normalised eigenvectors, orthogonal $P$, canonical form. Identify nature (positive definite). End with `learnbox`.
- **Example 2 (3×3 Intermediate):** $Q = 2x_1^2 + 2x_2^2 + 2x_3^2 + 2x_1x_2$. Reduce to canonical form. State rank, index, signature. End with `learnbox`.
- **Example 3 (Applied — Stress Analysis):** A 2D stress tensor at a material point is $\sigma = \begin{pmatrix} 60 & 20 \\ 20 & 40 \end{pmatrix}$ MPa. Find principal stresses (eigenvalues) and principal directions (eigenvectors). State the maximum shear stress as $(\lambda_{\max}-\lambda_{\min})/2$. End with `learnbox`.

### Section 7: Tabular Comparison / Workflow Reference
- **Table 1:** Nature classification based on eigenvalue signs — positive definite, negative definite, positive semi-definite, negative semi-definite, indefinite — with conditions on eigenvalues and examples.
- **Table 2:** Rank, index, and signature definitions with examples.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` table:
- Not symmetrising $A$ (placing full coefficient $2h$ in off-diagonal instead of $h$)
- Forgetting to NORMALISE eigenvectors before forming $P$
- Not verifying $P^TP = I$ (orthogonality check)
- Confusing rank (number of non-zero eigenvalues) with index (number of positive eigenvalues)
- Incorrect nature classification when eigenvalue = 0 (semi-definite, not definite)

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8):** What is a quadratic form? Why must $A$ be symmetric? What is the canonical form? When is a quadratic form positive definite?
2. **Descriptive Problems (4–5):** Full reduction problems for 2×2 and 3×3 quadratic forms.
3. **MCQs (5):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
`learnbox`: $Q = \mathbf{x}^TA\mathbf{x}$, canonical form definition, orthogonal diagonalisation, nature classification table, rank/index/signature formulas.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] pgfplots contour plots use `\addplot[domain=...]` with correct ellipse parametric equations.
- [ ] Normalisation steps shown explicitly with square root computations.
- [ ] All `tcolorbox` environments properly closed.
- [ ] $P^TP = I$ verification shown numerically in each example.
