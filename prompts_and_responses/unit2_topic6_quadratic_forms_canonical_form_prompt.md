# Generated Prompt — Topic: Quadratic Forms and Canonical Form

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Quadratic Forms and Canonical Form"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Quadratic Forms and Canonical Form"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Definition and Matrix Representation of a Quadratic Form | `infobox` must define $Q(\mathbf{x}) = \mathbf{x}^T A \mathbf{x}$ where $A$ is a real symmetric matrix; show how any quadratic expression $ax^2+bxy+cy^2$ maps to a matrix; state that $A$ can always be taken as symmetric ($A = \frac{1}{2}(A+A^T)$). Worked example: write $2x^2+3xy+5y^2$ in matrix form. MCQ on identifying the symmetric matrix of a quadratic form. |
| 2 | Orthogonal Transformation to Canonical Form | `infobox`: using the orthogonal diagonalisation $A=Q\Lambda Q^T$, substitute $\mathbf{x}=Q\mathbf{y}$ to reduce $Q(\mathbf{x})=\mathbf{y}^T\Lambda\mathbf{y}=\sum\lambda_i y_i^2$; this is the canonical form under orthogonal transformation; transformation matrix $Q$ is orthogonal. Worked example: reduce a 2-variable quadratic form to canonical form via eigenvectors. Viva: what makes the transformation orthogonal? |
| 3 | Reduction to Canonical Form by Congruence (Lagrange’s Method) | `infobox`: Lagrange’s method of completing the square to eliminate cross-product terms; systematic grouping by variable; result is sum of squared terms. Worked example: reduce $x^2+4xy+y^2$ using completing the square. MCQ on the number of squared terms in the canonical form. |
| 4 | Nature of a Quadratic Form (Definite, Semi-Definite, Indefinite) | `infobox`: classification by signs of eigenvalues — positive definite ($\lambda_i>0$ all), positive semi-definite ($\lambda_i\geq0$), negative definite ($\lambda_i<0$ all), negative semi-definite ($\lambda_i\leq0$), indefinite (mixed signs); Sylvester’s criterion (leading principal minors). Worked example: classify two quadratic forms. Viva: can a positive definite form be zero for some non-zero $\mathbf{x}$? |
| 5 | Rank, Index, and Signature of a Quadratic Form | `infobox`: rank = number of non-zero terms in canonical form (= rank of $A$); index = number of positive squared terms; signature = (number of positive terms, number of negative terms); law of inertia (Sylvester) — these are invariants under non-singular transformation. Worked example: find rank, index, signature of a given 3-variable quadratic form. MCQ on the law of inertia. |

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
\lhead{Quadratic Forms \& Canonical Form}
\rhead{Unit 2 — Quadratic Forms}
\cfoot{\thepage}

\title{\textbf{Quadratic Forms and Canonical Form} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Structural mechanics and stress analysis** — the stress tensor at a point is a quadratic form; its canonical form reveals principal stresses and directions, critical for failure prediction (von Mises criterion). Also: stability of equilibrium points in control systems (energy functions are quadratic forms).

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- 2-column `booktabs` table with at least one row per atomic sub-topic (stress tensors, energy methods, stability criteria, principal axes, invariants).
- Conclude with a `learnbox`.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0. Each with 2–4 lines intuition + dedicated `infobox`:

1. `\subsection{Definition and Matrix Representation of a Quadratic Form}`
2. `\subsection{Orthogonal Transformation to Canonical Form}`
3. `\subsection{Reduction to Canonical Form by Congruence (Lagrange's Method)}`
4. `\subsection{Nature of a Quadratic Form (Definite, Semi-Definite, Indefinite)}`
5. `\subsection{Rank, Index, and Signature of a Quadratic Form}`

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** Plot the conic section corresponding to a positive definite quadratic form (ellipse) and indefinite form (hyperbola) in 2D coordinates, showing principal axes.
- **Visual 2 (pgfplots/TikZ):** Contour plot of $Q(x,y)=2x^2+3xy+2y^2$ showing level curves, with eigenvector directions marked.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow for reducing a quadratic form to canonical form:
1. Write the quadratic form as $\mathbf{x}^T A \mathbf{x}$ (symmetric $A$)
2. Find eigenvalues of $A$
3. Find eigenvectors; orthonormalise (Gram-Schmidt if repeated eigenvalues)
4. Form orthogonal matrix $Q$; substitute $\mathbf{x}=Q\mathbf{y}$
5. Canonical form: $\sum\lambda_i y_i^2$
6. Classify: read signs of $\lambda_i$ for nature; count non-zero/positive for rank/index/signature

### Section 6: Fully Worked Step-by-Step Numerical Examples
At least **THREE (3)** examples inside `infobox` environments:
- **Example 1 (Basic):** Write $3x^2 + 4xy + 3y^2$ in matrix form and reduce to canonical form via eigenvalues.
- **Example 2 (3-variable):** Reduce $x^2+y^2+z^2+2xy+2yz+2xz$ to canonical form; find rank, index, signature.
- **Example 3 (Lagrange's method):** Use completing the square to reduce a 2-variable form without finding eigenvalues.
- **Example 4 (Applied — Stress Analysis):** A 2D stress state with symmetric tensor; find principal stresses and directions.

### Section 7: Tabular Comparison / Workflow Reference
- Table: Classification of quadratic forms by eigenvalue signs — positive definite, positive semi-definite, negative definite, negative semi-definite, indefinite.
- Table: Comparison of orthogonal transformation method vs Lagrange's method.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` with **Mistake | Why Students Do It | Correct Approach** columns. At least one row per atomic sub-topic:
- Sub-topic 1: using a non-symmetric matrix (off-diagonal not halved)
- Sub-topic 2: using a non-orthogonal transformation (forgetting to normalise eigenvectors)
- Sub-topic 3: error in completing the square (sign mistakes)
- Sub-topic 4: classifying by diagonal entries instead of eigenvalues
- Sub-topic 5: confusing index with rank

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
- [ ] All TikZ/pgfplots visuals are self-contained.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}` consistently.
- [ ] Section 9 has at least one viva and one MCQ per atomic sub-topic.
