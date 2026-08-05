# Generated Prompt — Topic: Cayley-Hamilton Theorem

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Cayley-Hamilton Theorem"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Cayley-Hamilton Theorem"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Statement of Cayley-Hamilton Theorem | `infobox` must state: every square matrix satisfies its own characteristic equation, i.e., $p(A)=0$ where $p(\lambda)=\det(A-\lambda I)$. Include formal theorem statement for $n\times n$ matrix. Worked example: verify theorem for a 2×2 matrix by substituting $A$ into $p(\lambda)$. MCQ on what $p(A)=0$ means. |
| 2 | Verification of Cayley-Hamilton Theorem | `infobox`: procedure for verification — form $p(\lambda)$, substitute matrix $A$ for $\lambda$, compute each matrix power, sum and confirm zero matrix. Show that $A^0=I$. Worked example: full verification for a 3×3 matrix with all matrix power computations shown. Viva: does the theorem apply to non-square matrices? |
| 3 | Finding the Inverse Using Cayley-Hamilton | `infobox`: from $p(A)=0$, for non-singular $A$, multiply through by $A^{-1}$ to express $A^{-1}$ as a polynomial in $A$. State the formula explicitly. Worked example: compute $A^{-1}$ for a 2×2 and 3×3 matrix using the theorem. MCQ: which condition is required to find the inverse via Cayley-Hamilton? |
| 4 | Computing Higher Powers of a Matrix Using Cayley-Hamilton | `infobox`: use $p(A)=0$ to express $A^n$ (for $n\geq\deg p$) as a linear combination of lower powers $I, A, A^2, \ldots, A^{n-1}$; recursive reduction algorithm. Worked example: compute $A^4$ and $A^5$ for a 2×2 matrix using the recurrence. Viva: up to what power can you reduce $A^k$ for a $3\times3$ matrix? |
| 5 | Minimal Polynomial and its Relation to Cayley-Hamilton | `infobox`: define minimal polynomial $m(\lambda)$ as the monic polynomial of least degree such that $m(A)=0$; $m(\lambda)$ divides $p(\lambda)$; every eigenvalue is a root of both. Worked example: find minimal polynomial for a diagonalisable and a non-diagonalisable matrix. MCQ: can the minimal polynomial have higher degree than the characteristic polynomial? |

**ENFORCEMENT RULES:**
1. Section 3 must contain **exactly 5 named `\subsection{}` entries**, one per row above.
2. Section 9 must contain **at least one viva-voce question and one MCQ per atomic sub-topic** (minimum 5 viva, 5 MCQ), each clearly referencing the sub-topic it tests.
3. Each atomic sub-topic must have a dedicated `infobox`, at least one fully worked example, and at least one assessment item.

---

## 1. LATEX PREAMBLE & CONFIGURATION REQUIREMENTS

The generated LaTeX document MUST start with this exact preamble:

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
\lhead{Cayley-Hamilton Theorem}
\rhead{Unit 2 — Eigenanalysis}
\cfoot{\thepage}

\title{\textbf{Cayley-Hamilton Theorem} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Control engineering and digital signal processing** — computing matrix exponentials $e^{At}$ for system state transitions (e.g., discretising a continuous-time model) requires high matrix powers; Cayley-Hamilton lets engineers reduce $A^k$ cheaply without repeated multiplication.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- 2-column `booktabs` table: theoretical statement vs. applications (matrix power reduction, inverse computation, minimal polynomial, system state transition). At least one row per atomic sub-topic.
- Conclude with a `learnbox` on the core objective.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0. Follow each subsection heading with 2–4 lines of conversational intuition, then a dedicated `infobox` per Section 0 specifications.

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** Plot the characteristic polynomial of a 2×2 example and mark the matrix's eigenvalues on the $\lambda$-axis, visually confirming the roots.
- **Visual 2 (TikZ):** A flowchart showing the algorithm: form $p(\lambda)$ → substitute $A$ → verify $p(A)=0$ → use for inverse/power computation.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow:
1. Find characteristic polynomial $p(\lambda)=\det(A-\lambda I)$
2. Write $p(\lambda) = \lambda^n + c_{n-1}\lambda^{n-1}+\cdots+c_0$
3. By Cayley-Hamilton: $A^n + c_{n-1}A^{n-1}+\cdots+c_0 I = 0$
4. To find $A^{-1}$ (if $c_0\neq 0$): rearrange $c_0 I = -(A^n+\cdots+c_1 A)$, multiply by $A^{-1}$
5. To find $A^k$ for $k\geq n$: use the recurrence $A^n = -(c_{n-1}A^{n-1}+\cdots+c_0 I)$

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide at least **THREE (3)** examples inside `infobox` environments (ideally one per atomic sub-topic):
- **Example 1:** Verify Cayley-Hamilton for a 2×2 matrix. Show all matrix power computations.
- **Example 2:** Find $A^{-1}$ using Cayley-Hamilton for a 3×3 matrix.
- **Example 3:** Compute $A^4$ and $A^5$ for a 2×2 matrix using the theorem's recurrence.
- **Example 4 (Applied):** Discretise a state-space model — use $p(A)=0$ to express $A^3$ cheaply, interpret in engineering context.

### Section 7: Tabular Comparison / Workflow Reference
- Table comparing methods for computing $A^{-1}$ (Gaussian elimination vs Cayley-Hamilton vs adjugate/cofactor) and methods for computing $A^k$ (direct multiplication vs Cayley-Hamilton recurrence vs diagonalisation).

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` table with columns: **Mistake Made | Why Students Do It | Correct Approach**. At least one row per atomic sub-topic:
- Sub-topic 1: confusing $p(\lambda)=0$ (scalar equation) with $p(A)=0$ (matrix equation)
- Sub-topic 2: arithmetic errors computing $A^2, A^3$ during verification
- Sub-topic 3: dividing by $\det(A)$ without checking invertibility
- Sub-topic 4: not using the recurrence, instead computing $A^k$ by brute force
- Sub-topic 5: assuming minimal polynomial = characteristic polynomial always

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8, at least one per atomic sub-topic)**
2. **Descriptive Problems (4–5)**
3. **MCQs (5 or more, at least one per atomic sub-topic):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullets.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] Section 3 contains **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0.
- [ ] All algebraic steps shown; no "it can easily be shown".
- [ ] All `tcolorbox` environments properly closed.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}` consistently.
- [ ] Section 9 has at least one viva and one MCQ per atomic sub-topic.
