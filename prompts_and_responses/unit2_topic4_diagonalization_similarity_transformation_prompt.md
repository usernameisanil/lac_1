# Generated Prompt — Topic: Diagonalization and Similarity Transformation

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Diagonalization and Similarity Transformation"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Diagonalization and Similarity Transformation"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Similarity Transformation | `infobox` must define $B=P^{-1}AP$; state that similar matrices share the same eigenvalues, characteristic polynomial, trace, and determinant; define equivalence relation. Worked example: verify two matrices are similar by computing $P^{-1}AP$. MCQ: which properties are preserved under similarity? |
| 2 | Diagonalizability Condition | `infobox`: $A$ is diagonalisable iff it has $n$ linearly independent eigenvectors; equivalently, for each eigenvalue, geometric multiplicity = algebraic multiplicity; sufficient condition: $n$ distinct eigenvalues. Worked example: test diagonalisability of a matrix with repeated eigenvalue. Viva: is every symmetric matrix diagonalisable? |
| 3 | Diagonalization Procedure (Modal Matrix) | `infobox`: steps — find all eigenvalues, find eigenvectors, form modal matrix $P$ (columns = eigenvectors), compute $D=P^{-1}AP$ (diagonal matrix of eigenvalues). Worked example: full diagonalisation of a 3×3 matrix with 3 distinct eigenvalues. MCQ on the diagonal entries of $D$. |
| 4 | Computing Matrix Powers via Diagonalization | `infobox`: $A^k = P D^k P^{-1}$ where $D^k$ is trivial (raise each diagonal entry to power $k$); extend to matrix functions $f(A)=Pf(D)P^{-1}$. Worked example: compute $A^{10}$ efficiently using diagonalisation. Viva: how does diagonalisation simplify computing $e^{At}$? |
| 5 | Orthogonal Diagonalization of Symmetric Matrices | `infobox`: real symmetric matrices have real eigenvalues and orthogonal eigenvectors for distinct eigenvalues; Spectral Theorem — $A=Q\Lambda Q^T$ where $Q$ is orthogonal; procedure includes Gram-Schmidt if eigenvalues are repeated. Worked example: orthogonally diagonalise a 2×2 symmetric matrix. MCQ on the condition for orthogonal diagonalisation. |

**ENFORCEMENT RULES:**
1. Section 3 must contain **exactly 5 named `\subsection{}` entries**, one per row above.
2. Section 9 must contain **at least one viva-voce question and one MCQ per atomic sub-topic** (minimum 5 viva, 5 MCQ).
3. Each atomic sub-topic must have a dedicated `infobox`, at least one fully worked example, and at least one assessment item.

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
\lhead{Diagonalization \& Similarity}
\rhead{Unit 2 — Eigenanalysis}
\cfoot{\thepage}

\title{\textbf{Diagonalization and Similarity Transformation} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Principal Component Analysis (PCA) in data engineering / image compression** — diagonalisation decomposes a covariance matrix into principal directions (eigenvectors) and variances (eigenvalues), enabling dimension reduction. Also: computing structural mode shapes and decoupling a system of differential equations.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- 2-column `booktabs` table with at least one row per atomic sub-topic.
- Conclude with a `learnbox`.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic. Begin each with 2–4 lines of intuition followed by a dedicated `infobox`.

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (TikZ):** Show a transformation $A$ in original coordinates, then $D = P^{-1}AP$ in eigen-coordinates, with axes rotated to eigenvector directions.
- **Visual 2 (pgfplots):** Visualise eigenvectors of a symmetric 2×2 matrix as orthogonal arrows, with ellipses showing the quadratic form.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed diagonalisation procedure:
1. Find characteristic polynomial $\det(A-\lambda I)=0$
2. Solve for all eigenvalues $\lambda_1,\ldots,\lambda_n$
3. For each $\lambda_i$, find eigenvector(s) via $(A-\lambda_i I)\mathbf{v}=\mathbf{0}$
4. Check: $n$ linearly independent eigenvectors exist?
5. Form $P = [\mathbf{v}_1\,|\,\mathbf{v}_2\,|\,\cdots\,|\,\mathbf{v}_n]$
6. Compute $D = P^{-1}AP$ and verify it is diagonal
- Branch: if not diagonalisable, mention Jordan normal form briefly.

### Section 6: Fully Worked Step-by-Step Numerical Examples
At least **THREE (3)** examples inside `infobox` environments (ideally one per atomic sub-topic):
- **Example 1:** Diagonalise a 2×2 matrix with distinct eigenvalues.
- **Example 2 (Non-diagonalisable):** A matrix with repeated eigenvalue and deficient eigenspace — show why it cannot be diagonalised.
- **Example 3:** Orthogonally diagonalise a real symmetric 2×2 matrix; verify $Q^TQ=I$.
- **Example 4 (Applied):** Use $A^k = PD^kP^{-1}$ to compute $A^{10}$ for a given matrix. Interpret in context.

### Section 7: Tabular Comparison / Workflow Reference
- Table: Diagonalisable vs Non-diagonalisable matrices — conditions, modal matrix existence, Jordan form alternative.
- Table: Matrix functions via diagonalisation ($A^k$, $e^A$, $\sin(A)$) with formulas.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` with **Mistake | Why Students Do It | Correct Approach** columns. At least one row per atomic sub-topic:
- Sub-topic 1: claiming matrices with same eigenvalues are similar (necessary but not sufficient in general)
- Sub-topic 2: assuming every matrix is diagonalisable
- Sub-topic 3: column order in $P$ must match order of $\lambda$ in $D$
- Sub-topic 4: computing $A^k$ by brute force instead of using $D^k$
- Sub-topic 5: failing to orthonormalise eigenvectors for repeated eigenvalues of symmetric matrix

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8, at least one per atomic sub-topic)**
2. **Descriptive Problems (4–5)**
3. **MCQs (5 or more, at least one per atomic sub-topic):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullets.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] Section 3 contains **exactly 5 named `\subsection{}` entries**.
- [ ] All `tcolorbox` environments properly closed.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}` consistently.
- [ ] Section 9 has at least one viva and one MCQ per atomic sub-topic.
