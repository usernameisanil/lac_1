# Generated Prompt — Topic: Characteristic Equation

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Characteristic Equation"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Characteristic Equation"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Characteristic Polynomial Definition | `infobox` must define $p(\lambda)=\det(A-\lambda I)$, its degree equals $n$ for an $n\times n$ matrix, and show that coefficients are expressed in terms of trace, principal minors, and determinant. Worked example: write out $p(\lambda)$ symbolically for a general 2×2 and 3×3. MCQ: what is the degree of the characteristic polynomial of a 4×4 matrix? |
| 2 | Characteristic Equation and its Roots (Eigenvalues) | `infobox`: characteristic equation is $p(\lambda)=0$; roots are eigenvalues; algebraic multiplicity of a root; Vieta's formulas linking $\sum\lambda_i=\text{tr}(A)$ and $\prod\lambda_i=\det(A)$. Worked example: solve characteristic equation for a concrete 2×2 matrix. Viva: what does it mean if the characteristic equation has a repeated root? |
| 3 | Cofactor Expansion for 2×2 and 3×3 Matrices | `infobox`: step-by-step cofactor/Laplace expansion rule, sign pattern $(-1)^{i+j}$, shortcuts for upper/lower triangular and diagonal matrices. Worked example: full expansion for a 3×3 non-triangular matrix. MCQ: eigenvalues of a triangular matrix are its diagonal entries — True/False. |
| 4 | Shortcuts and Special Cases | `infobox`: triangular matrix rule (eigenvalues = diagonal entries directly), 2×2 shortcut formula $\lambda^2-\text{tr}(A)\lambda+\det(A)=0$, symmetric matrices always have real eigenvalues, block diagonal eigenvalues. Worked example: use the 2×2 shortcut on a symmetric matrix. Viva: why do symmetric matrices always have real eigenvalues? |
| 5 | Algebraic Multiplicity | `infobox`: definition — order of $\lambda_i$ as a root of $p(\lambda)$; sum of all algebraic multiplicities equals $n$; relationship to repeated eigenvalues. Worked example: matrix with a double eigenvalue, identify its algebraic multiplicity. MCQ on sum of algebraic multiplicities. |

**ENFORCEMENT RULES:**
1. Section 3 must contain **exactly 5 named `\subsection{}` entries**, one per row above.
2. Section 9 must contain **at least one viva-voce question and one MCQ per atomic sub-topic** (minimum 5 viva, 5 MCQ), each clearly referencing the sub-topic it tests.
3. Each atomic sub-topic must have a dedicated `infobox`, at least one fully worked example, and at least one assessment item.

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
\lhead{Characteristic Equation}
\rhead{Unit 2 — Eigenanalysis}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Characteristic Equation} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence:

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: **Control systems engineering** — the stability of a feedback control loop (e.g., autopilot, robotics arm) is determined by the roots of the characteristic equation of the system matrix. If any root (eigenvalue) has a positive real part, the system is unstable and the aircraft crashes or the robot arm oscillates uncontrollably.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a 2-column `booktabs` table contrasting theoretical characteristic polynomial concepts vs. engineering stability analysis, signal processing poles/zeros, differential equation solution modes, and structural resonance prediction. At least one row per atomic sub-topic.
- Conclude with a `learnbox` on the core objective.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0:

1. `\subsection{Characteristic Polynomial Definition}`  
   Intuition: the characteristic polynomial is the algebraic fingerprint of a matrix. Dedicated `infobox` as specified in Section 0, Row 1.

2. `\subsection{Characteristic Equation and its Roots (Eigenvalues)}`  
   Intuition: setting $p(\lambda)=0$ pins down the special scalar values. Dedicated `infobox` as in Section 0, Row 2.

3. `\subsection{Cofactor Expansion for 2×2 and 3×3 Matrices}`  
   Intuition: determinant expansion is a systematic bookkeeping of signed products. Dedicated `infobox` as in Section 0, Row 3.

4. `\subsection{Shortcuts and Special Cases}`  
   Intuition: structure in the matrix means structure in the eigenvalues. Dedicated `infobox` as in Section 0, Row 4.

5. `\subsection{Algebraic Multiplicity}`  
   Intuition: a repeated root means the matrix has a "degenerate" direction. Dedicated `infobox` as in Section 0, Row 5.

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** Plot the characteristic polynomial $p(\lambda) = \lambda^2 - 5\lambda + 6$ as a curve, marking the roots $\lambda = 2$ and $\lambda = 3$ on the x-axis with vertical dashed lines and labels. Include grid, axis labels ($\lambda$ and $p(\lambda)$), and legend.
- **Visual 2 (pgfplots):** For a 3×3 example, plot a degree-3 characteristic polynomial showing distinct real roots, annotating root locations.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow:
1. Write $(A - \lambda I)$ explicitly
2. Expand $\det(A - \lambda I)$ using cofactor expansion (specify row/column choice strategy)
3. Collect and simplify into standard polynomial form $a_n\lambda^n + \cdots + a_0 = 0$
4. Solve polynomial (factoring, quadratic formula, or numerical methods for higher order)
5. Check: verify that $\text{tr}(A) = \sum \lambda_i$ and $\det(A) = \prod \lambda_i$
- Decision rules: recognise triangular matrices (diagonal entries are eigenvalues directly), symmetric matrices (always real roots), 2×2 shortcut formula.

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide at least **THREE (3)** comprehensive examples inside `infobox` environments, ideally one per atomic sub-topic:
- **Example 1 (2×2 Basic):** $A = \begin{pmatrix} 5 & 2 \\ 2 & 5 \end{pmatrix}$. Form characteristic equation, solve quadratic, verify with trace and determinant. End with `learnbox`.
- **Example 2 (3×3 Cofactor Expansion):** $A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 0 & 0 & 2 \end{pmatrix}$ (upper triangular). Show that $p(\lambda) = (1-\lambda)(3-\lambda)(2-\lambda)$ directly from triangular structure, explain WHY. End with `learnbox`.
- **Example 3 (Repeated Eigenvalue — Algebraic Multiplicity):** Matrix with a double eigenvalue; identify and state algebraic multiplicity. End with `learnbox`.
- **Example 4 (Applied — LRC Circuit):** Coupled electrical circuit system matrix $A = \begin{pmatrix} -2 & 1 \\ 1 & -2 \end{pmatrix}$. Find characteristic equation, eigenvalues, interpret: negative real eigenvalues = stable exponentially decaying modes. End with `learnbox`.

### Section 7: Tabular Comparison / Workflow Reference
- **Table:** Characteristic polynomial properties for special matrices — diagonal, triangular, symmetric, anti-symmetric, singular, identity, nilpotent — with their characteristic equation forms and eigenvalue patterns.

### Section 8: Common Student Mistakes & Pitfalls
Inside a `mistakebox`, table with columns: **Mistake Made | Why Students Do It | Correct Mathematical Approach**.
- At least one row per atomic sub-topic:
  - Sub-topic 1: incorrectly forming $p(\lambda)$ without $-\lambda$ on diagonal
  - Sub-topic 2: forgetting to set $\det=0$
  - Sub-topic 3: sign error in cofactor expansion $(-1)^{i+j}$
  - Sub-topic 4: not applying triangular matrix shortcut, wasting expansion time
  - Sub-topic 5: confusing algebraic multiplicity with geometric multiplicity

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8, at least one per atomic sub-topic):**
   - [Sub-topic 1] What is the leading coefficient of the characteristic polynomial of an $n\times n$ matrix?
   - [Sub-topic 2] What is the degree of the characteristic polynomial? Can two different matrices share the same characteristic polynomial?
   - [Sub-topic 3] State the shortcut for eigenvalues of a triangular matrix.
   - [Sub-topic 4] State the 2×2 shortcut characteristic equation.
   - [Sub-topic 5] What is algebraic multiplicity? What is the sum of all algebraic multiplicities?
2. **Descriptive Problems (4–5):** Full worked problems with hints.
3. **MCQs (5 or more, at least one per atomic sub-topic):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullets: definition of $p(\lambda)$, 2×2 shortcut, trace/det relations, triangular matrix rule, algebraic multiplicity, degree of polynomial = size of matrix.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] Section 3 contains **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every algebraic step shown explicitly — no skipped arithmetic.
- [ ] All `tcolorbox` environments properly closed.
- [ ] pgfplots `samples=100` used; axes properly labelled.
- [ ] Section 9 contains at least **one viva and one MCQ per atomic sub-topic**, each question referencing the sub-topic it tests.
