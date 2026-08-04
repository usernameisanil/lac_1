# Generated Prompt — Topic: Rank, Index, Signature and Positive Definite Forms

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Rank, Index, Signature and Positive Definite Forms"**.

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
\lhead{Rank, Index, Signature \& PD Forms}
\rhead{Unit 2 — Quadratic Forms}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Rank, Index, Signature and Positive Definite Forms} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence:

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Structural stability and optimisation** — a positive definite quadratic form represents stored elastic energy that is always positive (system has a stable equilibrium). In machine learning, a positive definite covariance matrix guarantees a valid probability distribution. A structural engineer checks positive definiteness of the stiffness matrix to confirm the structure won't collapse under any loading direction.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- `booktabs` table: rank/index/signature theory vs. structural stability, convex optimisation (positive definite Hessian = local minimum), physics (positive definite metric tensor), statistics (valid covariance), control systems (Lyapunov stability).
- Conclude with `learnbox`.

### Section 3: Intuition First & Mathematical Definitions
- Intuition: After reducing a quadratic form to canonical form $Q = \lambda_1 y_1^2 + \cdots + \lambda_n y_n^2$, the rank counts how many terms appear, the index counts how many are positive, and the signature packages this into a (p, q) pair. The nature of $Q$ tells us the geometry of the surface $Q = c$.
- `infobox` definitions:
  - **Rank** of $Q$: number of non-zero eigenvalues of $A$ (= rank of $A$)
  - **Index** (positive index of inertia): number of positive eigenvalues = $p$
  - **Signature**: the ordered pair $(p, q)$ where $q$ = number of negative eigenvalues; equivalently, sometimes written as $p - q$
  - **Nature classification**:
    - Positive definite: all $\lambda_i > 0$ (equivalently: all leading principal minors > 0 — Sylvester's criterion)
    - Negative definite: all $\lambda_i < 0$
    - Positive semi-definite: all $\lambda_i \geq 0$, at least one = 0
    - Negative semi-definite: all $\lambda_i \leq 0$, at least one = 0
    - Indefinite: mixed positive and negative eigenvalues
  - **Sylvester's Criterion** (state and derive for 2×2 and 3×3): $A$ is positive definite iff all leading principal minors $D_1, D_2, \ldots, D_n > 0$
  - **Law of Inertia (Sylvester)**: rank and signature are invariant under any non-singular linear transformation

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots 3D surface):** Plot $Q(x,y) = x^2 + 2y^2$ (positive definite — paraboloid opening upward) using `\addplot3[surf,...]`. Label axes $x$, $y$, $Q$. Add title "Positive Definite: Paraboloid".
- **Visual 2 (pgfplots 3D surface):** Plot $Q(x,y) = x^2 - y^2$ (indefinite — saddle surface). Label axes. Title "Indefinite: Saddle Surface".
- **Visual 3 (TikZ table diagram):** A visual classification chart mapping eigenvalue sign patterns to nature, geometry, and engineering interpretation.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow — Two methods:

**Method 1: Eigenvalue Method**
1. Find all eigenvalues of $A$
2. Count: $r$ = non-zero eigenvalues (rank), $p$ = positive eigenvalues (index), $q = r - p$ (negative count)
3. Signature = $(p, q)$; classify nature

**Method 2: Sylvester's Criterion (Positive Definiteness Check)**
1. Compute $D_1 = a_{11}$
2. Compute $D_2 = \det\begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix}$
3. Compute $D_3 = \det(A)$ (for 3×3)
4. If all $D_i > 0$: positive definite; if signs alternate starting negative: negative definite; else: check further

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide **THREE** examples:
- **Example 1 (2×2 Classification):** $Q = x^2 + 4xy + 5y^2$. Form $A$, find eigenvalues, determine rank, index, signature, and nature. Verify using Sylvester's criterion. End with `learnbox`.
- **Example 2 (3×3 with Zero Eigenvalue):** $Q = x_1^2 + 2x_2^2 + 3x_3^2 - 2x_1x_2$. Find rank (hint: one eigenvalue = 0), index, signature $(p,q)$, classify as semi-definite. End with `learnbox`.
- **Example 3 (Applied — Checking Stability of Optimum):** Hessian of $f(x,y) = 3x^2 + 2xy + 4y^2$ at critical point is $H = \begin{pmatrix} 6 & 2 \\ 2 & 8 \end{pmatrix}$. Check positive definiteness using Sylvester's criterion. Conclude: local minimum exists. End with `learnbox`.

### Section 7: Tabular Comparison / Workflow Reference
- **Master classification table:** Nature | Eigenvalue Condition | Sylvester Condition | Signature $(p,q)$ | Geometric Shape | Engineering Meaning.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` table:
- Confusing rank of quadratic form with rank of matrix (they are the same — clarify this is NOT a mistake, just needs clear understanding)
- Confusing index (count of positive eigenvalues) with rank
- Incorrect Sylvester check — using wrong submatrix sizes
- Classifying zero eigenvalue as positive (leading to wrong nature — should be semi-definite)
- Reporting signature as a single number $p-q$ instead of pair $(p,q)$ when the problem asks for the pair

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8):** Define rank of a quadratic form. What is Sylvester's Law of Inertia? How does positive definiteness relate to eigenvalues? What is the signature?
2. **Descriptive Problems (4–5):** Full classification problems.
3. **MCQs (5):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
`learnbox`: rank/index/signature definitions, nature classification table, Sylvester's criterion, Law of Inertia, engineering significance of positive definiteness.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] pgfplots 3D plots use `\addplot3[surf, domain=..., domain y=..., samples=20]` for smooth surfaces.
- [ ] Sylvester's criterion applied step-by-step with all determinant computations shown.
- [ ] All `tcolorbox` environments properly closed.
- [ ] Nature classification consistent across all examples and tables.
