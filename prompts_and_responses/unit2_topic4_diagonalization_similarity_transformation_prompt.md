# Generated Prompt — Topic: Diagonalization and Similarity Transformation

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Diagonalization and Similarity Transformation"**.

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
\lhead{Diagonalization \& Similarity}
\rhead{Unit 2 — Diagonalization}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Diagonalization and Similarity Transformation} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence:

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Principal Component Analysis (PCA) in data science and image compression** — diagonalising the covariance matrix of sensor data decouples correlated signals into independent modes, allowing compression of a 1000-pixel image into 50 dominant components. Also: decoupling coupled differential equations in structural dynamics.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- `booktabs` table: similarity transformation concept vs. decoupling ODEs, PCA, computing $A^n$ efficiently, coordinate change in mechanics, modal analysis in FEM.
- Conclude with `learnbox`.

### Section 3: Intuition First & Mathematical Definitions
- Intuition: Diagonalising $A$ means finding a new coordinate system (basis of eigenvectors) in which $A$ acts as a simple scalar-stretching operation. In that basis, $A$ becomes diagonal.
- `infobox` definitions:
  - Similarity: $B = P^{-1}AP$ (similar matrices represent same transformation in different bases)
  - Diagonalization: $A = PDP^{-1}$, where $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$ and $P$ is the matrix of eigenvectors
  - Condition for diagonalizability: $A$ is diagonalisable iff it has $n$ linearly independent eigenvectors
  - Sufficient condition: $n$ distinct eigenvalues guarantee diagonalisability
  - Geometric vs. algebraic multiplicity criterion for repeated eigenvalues

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (TikZ):** Commutative diagram showing $A$ in standard basis, $P$ change-of-basis, $D$ diagonal in eigenvector basis, and $P^{-1}$ inverse transform. Use arrows with labels $P$, $P^{-1}$, $A$, $D$.
- **Visual 2 (pgfplots):** Show original axes vs. rotated eigenvector axes for a 2×2 symmetric matrix, illustrating how an ellipse (quadratic form) aligns with the eigenvector directions after diagonalisation.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow:
1. Find all eigenvalues $\lambda_1, \ldots, \lambda_n$ from $\det(A - \lambda I) = 0$
2. For each $\lambda_i$, find eigenvector $\mathbf{v}_i$ by solving $(A - \lambda_i I)\mathbf{v} = \mathbf{0}$
3. Check linear independence of $\{\mathbf{v}_1, \ldots, \mathbf{v}_n\}$ (if $n$ distinct eigenvalues, auto-independent)
4. Form $P = [\mathbf{v}_1 | \mathbf{v}_2 | \cdots | \mathbf{v}_n]$ and $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$
5. Verify: compute $P^{-1}AP$ and confirm it equals $D$
6. Decision: if matrix is NOT diagonalisable, state why (geometric multiplicity < algebraic multiplicity)

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide **THREE** examples:
- **Example 1 (2×2 with distinct eigenvalues):** $A = \begin{pmatrix} 4 & 1 \\ 2 & 3 \end{pmatrix}$. Find $P$, $D$, verify $A = PDP^{-1}$. End with `learnbox`.
- **Example 2 (3×3 symmetric matrix):** $A = \begin{pmatrix} 2 & 1 & 0 \\ 1 & 2 & 1 \\ 0 & 1 & 2 \end{pmatrix}$. Diagonalise completely. Verify. End with `learnbox`.
- **Example 3 (Applied — Decoupling ODEs):** System $\dot{\mathbf{x}} = A\mathbf{x}$ with $A = \begin{pmatrix} -1 & 2 \\ 0 & -3 \end{pmatrix}$. Diagonalise, change variables $\mathbf{y} = P^{-1}\mathbf{x}$, solve decoupled system $\dot{\mathbf{y}} = D\mathbf{y}$, transform back. Interpret the independent decay modes. End with `learnbox`.

### Section 7: Tabular Comparison / Workflow Reference
- **Table 1:** Similarity invariants — trace, determinant, rank, eigenvalues, characteristic polynomial are preserved under similarity.
- **Table 2:** When is diagonalisation possible? — distinct eigenvalues (YES), symmetric matrix (YES), geometric = algebraic multiplicity (YES), otherwise (NOT diagonalisable — use Jordan form mention only).

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` table:
- Placing eigenvalues (not eigenvectors) as columns of $P$
- Incorrect column ordering in $P$ vs $D$ (eigenvalue in $D$ must match eigenvector column position in $P$)
- Not verifying linear independence of eigenvectors
- Computing $PDA^{-1}$ instead of $P^{-1}AP$
- Trying to diagonalise a non-diagonalisable matrix

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8):** What is a similarity transformation? When is a matrix diagonalisable? Are all matrices diagonalisable? What is $P$ made of?
2. **Descriptive Problems (4–5):** Full diagonalisation problems with verification.
3. **MCQs (5):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
`learnbox`: $A = PDP^{-1}$, columns of $P$ are eigenvectors, diagonalisability condition, similarity invariants, application to $A^n = PD^nP^{-1}$.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] All matrix multiplication steps shown explicitly.
- [ ] TikZ commutative diagram uses proper arrow and node syntax.
- [ ] All `tcolorbox` environments properly closed.
- [ ] $P^{-1}$ computation shown step-by-step (adjugate/cofactor method for 2×2).
