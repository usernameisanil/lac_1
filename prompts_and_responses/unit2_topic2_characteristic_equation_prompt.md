# Generated Prompt — Topic: Characteristic Equation

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Characteristic Equation"**.

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
- Include a 2-column `booktabs` table contrasting theoretical characteristic polynomial concepts vs. engineering stability analysis, signal processing poles/zeros, differential equation solution modes, and structural resonance prediction.
- Conclude with a `learnbox` on the core objective.

### Section 3: Intuition First & Mathematical Definitions
- Intuition: The characteristic equation is the algebraic fingerprint of a matrix — it encodes ALL information about eigenvalues in a single polynomial.
- Define inside an `infobox`:
  - Characteristic polynomial: $p(\lambda) = \det(A - \lambda I)$
  - Characteristic equation: $\det(A - \lambda I) = 0$
  - For $n \times n$ matrix: degree-$n$ polynomial in $\lambda$
  - Coefficients in terms of trace, minors, and determinant
  - For 2×2: $\lambda^2 - \text{tr}(A)\lambda + \det(A) = 0$
  - For 3×3: explicit expansion form
  - Algebraic multiplicity of an eigenvalue

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (pgfplots):** Plot the characteristic polynomial $p(\lambda) = \lambda^2 - 5\lambda + 6$ as a curve, marking the roots $\lambda = 2$ and $\lambda = 3$ on the x-axis with vertical dashed lines and labels. Include grid, axis labels ($\lambda$ and $p(\lambda)$), and legend.
- **Visual 2 (pgfplots):** For a 3×3 example, plot a degree-3 characteristic polynomial showing one real root and two complex conjugate roots (roots crossing x-axis once), annotating the real root location.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Boxed workflow:
1. Write $(A - \lambda I)$ explicitly
2. Expand $\det(A - \lambda I)$ using cofactor expansion (specify row/column choice strategy)
3. Collect and simplify into standard polynomial form $a_n\lambda^n + \cdots + a_0 = 0$
4. Solve polynomial (factoring, quadratic formula, or numerical methods for higher order)
5. Check: verify that $\text{tr}(A) = \sum \lambda_i$ and $\det(A) = \prod \lambda_i$
- Decision rules: recognise triangular matrices (diagonal entries are eigenvalues directly), symmetric matrices (always real roots), 2×2 shortcut formula.

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide **THREE** examples:
- **Example 1 (2×2 Basic):** $A = \begin{pmatrix} 5 & 2 \\ 2 & 5 \end{pmatrix}$. Form characteristic equation, solve quadratic, verify with trace and determinant. End with `learnbox`.
- **Example 2 (3×3 Intermediate):** $A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 0 & 0 & 2 \end{pmatrix}$ (upper triangular). Show that $p(\lambda) = (1-\lambda)(3-\lambda)(2-\lambda)$ directly from the triangular structure, explain WHY this works. End with `learnbox`.
- **Example 3 (Applied — LRC Circuit):** A coupled electrical circuit produces system matrix $A = \begin{pmatrix} -2 & 1 \\ 1 & -2 \end{pmatrix}$. Find characteristic equation, eigenvalues, and interpret: negative real eigenvalues = stable exponentially decaying modes. End with `learnbox`.

### Section 7: Tabular Comparison / Workflow Reference
- **Table:** Characteristic polynomial properties for special matrices — diagonal, triangular, symmetric, anti-symmetric, singular, identity, nilpotent — with their characteristic equation forms and eigenvalue patterns.

### Section 8: Common Student Mistakes & Pitfalls
Inside a `mistakebox`, table with columns: Mistake | Why Students Do It | Correct Approach.
- Cover: sign error in $(A - \lambda I)$ vs $(\lambda I - A)$, incorrect cofactor expansion, forgetting to set $\det = 0$, arithmetic errors in 3×3 expansion, confusing characteristic polynomial with minimal polynomial.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce (6–8 Questions):** Degree of characteristic polynomial? Can two different matrices have the same characteristic polynomial? What is algebraic multiplicity?
2. **Descriptive Problems (4–5):** Full worked problems with hints.
3. **MCQs (5):** Bold correct answer, single-line explanation.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullets: definition of $p(\lambda)$, 2×2 shortcut, trace/det relations, triangular matrix rule, algebraic multiplicity, degree of polynomial = size of matrix.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] `\begin{document}` and `\end{document}` wrap entire code.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every algebraic step shown explicitly — no skipped arithmetic.
- [ ] All `tcolorbox` environments properly closed.
- [ ] pgfplots `samples=100` used; axes properly labelled.
