# Generated Prompt — Topic: Rank, Index, Signature, and Definite Forms

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Rank, Index, Signature, and Definite Forms of Quadratic Forms"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Rank, Index, Signature, and Definite Forms"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Rank of a Quadratic Form | `infobox`: rank equals the number of non-zero terms in canonical form = rank of the associated matrix $A$; connection to dimension of range space. Worked example: find the rank of a 3-variable quadratic form from its canonical form. MCQ on rank interpretation. |
| 2 | Index of a Quadratic Form | `infobox`: index = number of positive squared terms in the canonical form under any non-singular transformation; proof that it is an invariant (Sylvester's Law of Inertia). Worked example: identify the index of a given canonical form. Viva: can two canonical forms of the same quadratic form have different indices? |
| 3 | Signature of a Quadratic Form | `infobox`: signature = (number of positive terms $p$, number of negative terms $q$); relation to rank $r=p+q$; invariance under non-singular transformations. Worked example: state the signature of a 3-variable form. MCQ on interpreting signature $(2,1)$. |
| 4 | Sylvester’s Law of Inertia | `infobox`: formal statement — rank, index, and signature are invariants under any non-singular congruence transformation; any two canonical forms of the same quadratic form agree in $p$ and $q$. Worked example: verify the law by computing canonical form via two different transformations and confirming same $(p,q)$. Viva: what does Sylvester's Law guarantee? |
| 5 | Classification of Definite Forms and Sylvester’s Criterion | `infobox`: positive definite iff all eigenvalues $>0$ iff all leading principal minors $>0$ (Sylvester’s criterion); negative definite iff alternating signs of principal minors; semi-definite and indefinite conditions. Worked example: test positive definiteness using Sylvester’s criterion on a 3×3 matrix. MCQ on Sylvester’s criterion for a 2×2 matrix. |

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
\lhead{Rank, Index, Signature \& Definite Forms}
\rhead{Unit 2 — Quadratic Forms}
\cfoot{\thepage}

\title{\textbf{Rank, Index, Signature, and Definite Forms} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Structural stability** — the potential energy of a mechanical system near equilibrium is a quadratic form; if it is positive definite (index = $n$), the equilibrium is stable; if indefinite, the structure may buckle or diverge. Testing positive definiteness via Sylvester’s criterion is used routinely in finite element analysis.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- 2-column `booktabs` table with at least one row per atomic sub-topic.
- Conclude with a `learnbox`.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic:

1. `\subsection{Rank of a Quadratic Form}`
2. `\subsection{Index of a Quadratic Form}`
3. `\subsection{Signature of a Quadratic Form}`
4. `\subsection{Sylvester's Law of Inertia}`
5. `\subsection{Classification of Definite Forms and Sylvester's Criterion}`

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** 3D surface plot of a positive definite quadratic form $Q(x,y)=x^2+xy+y^2$ showing bowl-shaped surface with minimum at origin.
- **Visual 2 (pgfplots):** Surface or contour of an indefinite form showing saddle point.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow:
1. Form symmetric matrix $A$ of the quadratic form
2. Find canonical form (via eigenvalues or Lagrange’s method)
3. Count: total non-zero terms = rank; positive terms = index; signature = $(p,q)$
4. Classify nature: read signs of eigenvalues or apply Sylvester’s criterion
5. Verify: confirm rank, index, signature are invariant under a different transformation

### Section 6: Fully Worked Step-by-Step Numerical Examples
At least **THREE (3)** examples inside `infobox` environments:
- **Example 1:** Find rank, index, signature of $2x^2+3y^2-z^2+2xy$.
- **Example 2:** Test positive definiteness of $A = \begin{pmatrix}2&1\\1&3\end{pmatrix}$ using Sylvester’s criterion.
- **Example 3:** Verify Sylvester’s Law of Inertia by reducing a form via two different methods and confirming same $(p,q)$.
- **Example 4 (Applied):** Check whether the potential energy function of a structural system is positive definite.

### Section 7: Tabular Comparison / Workflow Reference
- Table: Complete classification of quadratic forms — type, eigenvalue condition, Sylvester’s criterion condition, signature, engineering meaning.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` with **Mistake | Why Students Do It | Correct Approach** columns. At least one row per atomic sub-topic.

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
- [ ] Section 9 has at least one viva and one MCQ per atomic sub-topic.
