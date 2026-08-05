# Generated Prompt — Topic: Special Matrices

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Special Matrices"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Special Matrices"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Symmetric and Skew-Symmetric Matrices | `infobox`: symmetric $A=A^T$, skew-symmetric $A=-A^T$; eigenvalues of symmetric matrix are real; eigenvalues of skew-symmetric are zero or purely imaginary; every square matrix is uniquely the sum of a symmetric and skew-symmetric part. Worked example: decompose a 3×3 matrix into symmetric and skew-symmetric parts. MCQ on eigenvalues of a real skew-symmetric matrix. |
| 2 | Orthogonal Matrices | `infobox`: $Q^TQ=I$ iff columns are orthonormal; $\det(Q)=\pm1$; eigenvalues have modulus 1; preserves length and angle (isometry); inverse = transpose. Worked example: verify a given 2×2 rotation matrix is orthogonal, find its eigenvalues. Viva: what does it mean geometrically that $Q$ is orthogonal? |
| 3 | Hermitian and Skew-Hermitian Matrices | `infobox`: Hermitian $A=A^*$ (conjugate transpose); skew-Hermitian $A=-A^*$; Hermitian matrices have real eigenvalues; skew-Hermitian have purely imaginary or zero eigenvalues; unitary matrix $U^*U=I$ (complex orthogonal). Worked example: verify a complex matrix is Hermitian; find its eigenvalues. MCQ on eigenvalues of a Hermitian matrix. |
| 4 | Idempotent and Nilpotent Matrices | `infobox`: idempotent $A^2=A$, eigenvalues $\in\{0,1\}$, rank = trace; nilpotent $A^k=0$ for some $k$, all eigenvalues = 0, characteristic polynomial = $\lambda^n$. Worked example: verify idempotency and find eigenvalues; show a nilpotent matrix satisfies $A^2=0$. Viva: what is the characteristic polynomial of a nilpotent matrix? |
| 5 | Unitary Matrices and Normal Matrices | `infobox`: unitary $U^*U=I$ (generalises orthogonal to complex); normal matrix $AA^*=A^*A$ (includes Hermitian, skew-Hermitian, unitary, real symmetric, orthogonal); normal matrices are unitarily diagonalisable (Spectral Theorem for normal matrices). Worked example: verify a complex matrix is unitary. MCQ on the condition for unitary diagonalisability. |

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
\lhead{Special Matrices}
\rhead{Unit 2 — Eigenanalysis}
\cfoot{\thepage}

\title{\textbf{Special Matrices} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Quantum computing and signal processing** — unitary matrices represent quantum gates that preserve probability; Hermitian matrices represent observable quantities; orthogonal matrices are used in 3D rotation (robotics, computer graphics); idempotent matrices appear in projection operations (filtering, regression).

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- 2-column `booktabs` table with at least one row per atomic sub-topic.
- Conclude with a `learnbox`.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic:

1. `\subsection{Symmetric and Skew-Symmetric Matrices}`
2. `\subsection{Orthogonal Matrices}`
3. `\subsection{Hermitian and Skew-Hermitian Matrices}`
4. `\subsection{Idempotent and Nilpotent Matrices}`
5. `\subsection{Unitary Matrices and Normal Matrices}`

Each with 2–4 lines of intuition followed by a dedicated `infobox` per Section 0 specifications.

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (TikZ):** Venn diagram or hierarchy of matrix types — Normal $\supset$ \{Hermitian, Unitary, Orthogonal, Symmetric\} showing containment relationships.
- **Visual 2 (TikZ):** 2D geometric illustration of an orthogonal matrix as a rotation, showing a unit circle preserved under the transformation.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow for identifying and verifying special matrix types:
1. Check symmetry: compute $A^T$ (or $A^*$ for complex); compare with $A$
2. Check orthogonality/unitarity: compute $Q^TQ$ (or $U^*U$); verify = $I$
3. Check idempotency/nilpotency: compute $A^2$; compare with $A$ or $0$
4. Check normality: compute $AA^*$ and $A^*A$; verify equality
5. For each type confirmed, state eigenvalue consequences immediately

### Section 6: Fully Worked Step-by-Step Numerical Examples
At least **THREE (3)** examples inside `infobox` environments (ideally one per atomic sub-topic):
- **Example 1:** Decompose a 3×3 matrix into symmetric and skew-symmetric parts; find eigenvalues of each part.
- **Example 2:** Verify a 2×2 rotation matrix is orthogonal; find its eigenvalues (complex).
- **Example 3:** Verify a complex matrix is Hermitian; confirm real eigenvalues.
- **Example 4:** Show $A^2=0$ for a nilpotent matrix; find its characteristic polynomial.
- **Example 5 (Applied — Projection):** Show that an idempotent matrix represents a projection; interpret geometrically.

### Section 7: Tabular Comparison / Workflow Reference
- Master reference table: all 5 matrix types with defining condition, eigenvalue property, determinant property, engineering application, and relationship to diagonalisation.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` with **Mistake | Why Students Do It | Correct Approach** columns. At least one row per atomic sub-topic:
- Sub-topic 1: confusing $A^T = A$ with $A^T = -A$
- Sub-topic 2: assuming $Q^T = Q^{-1}$ without verifying $Q^TQ=I$
- Sub-topic 3: applying real transpose instead of conjugate transpose for Hermitian check
- Sub-topic 4: confusing idempotent ($A^2=A$) with involutory ($A^2=I$)
- Sub-topic 5: assuming all matrices are normal

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
- [ ] All TikZ/pgfplots visuals self-contained and compilable with pdflatex.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}` consistently.
- [ ] Section 9 has at least one viva and one MCQ per atomic sub-topic.
