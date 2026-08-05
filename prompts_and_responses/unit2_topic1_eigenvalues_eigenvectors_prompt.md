# Generated Prompt — Topic: Eigenvalues and Eigenvectors

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Eigenvalues and Eigenvectors"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Eigenvalues and Eigenvectors"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:
- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Definition of Eigenvalue and Eigenvector | `infobox` must state $A\mathbf{v}=\lambda\mathbf{v}$, non-triviality condition $\mathbf{v}\neq\mathbf{0}$, eigenspace definition, and spectrum of a matrix. Worked example: identify eigenvalues of a 2×2 matrix by inspection. MCQ on eigenvalue of the identity matrix. |
| 2 | Characteristic Equation and Polynomial | `infobox` must define $\det(A-\lambda I)=0$, degree-$n$ polynomial, trace/determinant relations for 2×2 and 3×3 cases. Worked example: form and solve the characteristic polynomial for a 2×2 matrix step by step. Viva: what is the degree of the characteristic polynomial for an $n\times n$ matrix? |
| 3 | Computing Eigenvectors via Row Reduction | `infobox` must state that for each $\lambda_i$, solve $(A-\lambda_i I)\mathbf{v}=\mathbf{0}$ using Gaussian elimination; express solution as free-variable parametric form. Worked example: full row-reduction for a 3×3 matrix. MCQ on the number of free variables. |
| 4 | Geometric and Algebraic Multiplicity | `infobox` must define algebraic multiplicity (root multiplicity in characteristic polynomial) and geometric multiplicity (dimension of eigenspace), with the inequality $1\leq\text{geom}\leq\text{alg}$. Worked example with a repeated eigenvalue. Viva: when does algebraic multiplicity equal geometric multiplicity? |
| 5 | Eigenvalues of Special Matrices | `infobox` must cover: diagonal/triangular matrices (eigenvalues = diagonal entries), symmetric matrices (real eigenvalues), orthogonal matrices ($|\lambda|=1$), singular matrices (zero eigenvalue), idempotent matrices ($\lambda\in\{0,1\}$). Worked example: triangular matrix eigenvalues by inspection. MCQ on singular matrix eigenvalue. |

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
\lhead{Eigenvalues \& Eigenvectors}
\rhead{Unit 2 — Eigenanalysis}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Eigenvalues and Eigenvectors} \\ \large Unit 2: Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence:

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**
- Use a compelling scenario such as: a mechanical engineer analysing the **natural vibration frequencies (resonance modes) of a bridge or aircraft wing**, where eigenvalues represent the natural frequencies and eigenvectors represent the corresponding mode shapes. Explain why missing an eigenvalue during structural design could cause catastrophic resonance failure (e.g., Tacoma Narrows Bridge).

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Contrast understanding vs. misunderstanding of eigenvalues/eigenvectors.
- Include a 2-column `booktabs` table: **"Theoretical Concept" vs "Engineering Application / Consequence of Misunderstanding"** with at least one row per atomic sub-topic from Section 0 (principal axes, vibration modes, stability analysis, image compression/PCA, quantum states).
- Conclude with a `learnbox` summarising the core objective.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0:

1. `\subsection{Definition of Eigenvalue and Eigenvector}`  
   Begin with geometric intuition: a linear transformation $A$ stretches or rotates vectors — eigenvectors are the special directions that do NOT rotate, only scale by $\lambda$. Follow with a dedicated `infobox` containing all formal definitions listed in Section 0, Row 1.

2. `\subsection{Characteristic Equation and Polynomial}`  
   Intuition: the characteristic equation is the algebraic fingerprint of a matrix. Dedicated `infobox` with content from Section 0, Row 2.

3. `\subsection{Computing Eigenvectors via Row Reduction}`  
   Intuition: once $\lambda$ is known, finding the direction is a null-space problem. Dedicated `infobox` with content from Section 0, Row 3.

4. `\subsection{Geometric and Algebraic Multiplicity}`  
   Intuition: repeated roots can collapse the eigenspace unexpectedly. Dedicated `infobox` with content from Section 0, Row 4.

5. `\subsection{Eigenvalues of Special Matrices}`  
   Intuition: structural properties of a matrix directly dictate its spectrum. Dedicated `infobox` with content from Section 0, Row 5.

### Section 4: Visual Artifacts & Geometric Interpretation (MANDATORY LaTeX Visuals)
- **Visual 1 (TikZ):** Draw a 2D coordinate plane showing a vector $\mathbf{v}$ before and after transformation $A\mathbf{v}$, highlighting that eigenvectors remain collinear (only stretched), while a non-eigenvector rotates.
- **Visual 2 (pgfplots):** For matrix $A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$, plot the eigenvectors as arrows from the origin with distinct colours, labelled with their eigenvalues.
- Include full axis labels, legends, grid, and `samples=100` where applicable.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
Provide a boxed workflow:
1. Form the characteristic matrix $(A - \lambda I)$
2. Compute $\det(A - \lambda I) = 0$ — the characteristic equation
3. Solve the polynomial for eigenvalues $\lambda_1, \lambda_2, \ldots$
4. For each $\lambda_i$, substitute back: solve $(A - \lambda_i I)\mathbf{v} = \mathbf{0}$ using row reduction
5. Express the eigenvector as a parametric free-variable solution
6. Verify: check $A\mathbf{v}_i = \lambda_i \mathbf{v}_i$
- Include decision rules: repeated eigenvalues, zero eigenvalues, complex eigenvalues.

### Section 6: Fully Worked Step-by-Step Numerical Examples
Provide at least **THREE (3)** comprehensive examples inside `infobox` environments, ideally **one per atomic sub-topic** (5 examples strongly preferred):
- **Example 1 (Basic — 2×2 matrix):** $A = \begin{pmatrix} 4 & 1 \\ 2 & 3 \end{pmatrix}$. Find all eigenvalues and eigenvectors. Show complete determinant expansion, quadratic solution, and row reduction. End with a `learnbox` titled "What Did We Learn?".
- **Example 2 (Intermediate — 3×3 matrix):** $A = \begin{pmatrix} 2 & 0 & 0 \\ 1 & 3 & 0 \\ 0 & 1 & 2 \end{pmatrix}$ (triangular). Show that eigenvalues of a triangular matrix are its diagonal entries, then verify by solving $(A - \lambda I)\mathbf{v} = \mathbf{0}$ for each. End with a `learnbox`.
- **Example 3 (Repeated Eigenvalue — Algebraic vs Geometric Multiplicity):** Matrix with a repeated eigenvalue; show case where geometric multiplicity equals algebraic (diagonalisable) and mention case where it does not. End with a `learnbox`.
- **Example 4 (Applied — Vibration Analysis):** A 2-DOF spring-mass system produces stiffness matrix $K = \begin{pmatrix} 3 & -1 \\ -1 & 3 \end{pmatrix}$ (mass-normalised). Find eigenvalues (natural frequencies squared $\omega^2$) and eigenvectors (mode shapes). Interpret physically: which mode is in-phase and which is out-of-phase? End with a `learnbox`.

### Section 7: Tabular Comparison / Workflow Reference
- **Table 1:** Properties of eigenvalues — Trace $= \sum \lambda_i$, Determinant $= \prod \lambda_i$, Symmetric matrices have real eigenvalues, Orthogonal matrices have $|\lambda|=1$.
- **Table 2:** Special matrix types and their eigenvalue characteristics (diagonal, triangular, symmetric, singular, orthogonal, idempotent).

### Section 8: Common Student Mistakes & Pitfalls
Inside a `mistakebox`, provide a `tabular` table with columns: **Mistake Made | Why Students Do It | Correct Mathematical Approach**.
- Include **at least one row per atomic sub-topic** from Section 0:
  - Sub-topic 1: forgetting $\mathbf{v} \neq \mathbf{0}$
  - Sub-topic 2: sign errors in $(A - \lambda I)$
  - Sub-topic 3: incomplete row reduction giving wrong eigenspace
  - Sub-topic 4: assuming all matrices are diagonalisable (confusing algebraic and geometric multiplicity)
  - Sub-topic 5: assuming complex eigenvalues for symmetric matrices

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (6–8, at least one per atomic sub-topic):**
   - [Sub-topic 1] What is an eigenspace? Can eigenvalue be zero?
   - [Sub-topic 2] What is the degree of the characteristic polynomial of an $n\times n$ matrix?
   - [Sub-topic 3] Are eigenvectors unique? How is the eigenspace expressed?
   - [Sub-topic 4] When does algebraic multiplicity equal geometric multiplicity?
   - [Sub-topic 5] What does a zero eigenvalue imply about the matrix?
2. **Descriptive Exam Questions (4–5):** Full worked problems — find eigenvalues/eigenvectors of given 2×2 and 3×3 matrices, verify Cayley-Hamilton, interpret vibration modes.
3. **MCQs (5 or more, at least one per atomic sub-topic):** Bold the correct option, single-line explanation. Topics: eigenvalue of identity [Sub-topic 1], shortcut for triangular matrix [Sub-topic 5], relationship between trace and eigenvalues [Sub-topic 2], repeated eigenvalue geometric multiplicity [Sub-topic 4].

### Section 10: Quick Recap & Formula Sheet
- Conclude with a `learnbox` containing 6–8 high-impact bullet points: core equation, characteristic polynomial, trace/determinant relations, eigenspace definition, special cases (zero eigenvalue = singular, repeated eigenvalues), geometric vs algebraic multiplicity.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] Ensure `\begin{document}` and `\end{document}` wrap the entire code.
- [ ] Section 3 contains **exactly 5 named `\subsection{}` entries**, one per atomic sub-topic in Section 0.
- [ ] NO missing brackets, undefined control sequences, or raw unescaped LaTeX characters.
- [ ] Show EVERY step of algebraic manipulation — do NOT use phrases like "it can easily be shown that".
- [ ] Every custom `tcolorbox` MUST be properly closed.
- [ ] All TikZ/pgfplots code must be self-contained and compilable without external files.
- [ ] Matrix notation must use `\begin{pmatrix}...\end{pmatrix}` consistently.
- [ ] Section 9 contains at least **one viva and one MCQ per atomic sub-topic** (5 sub-topics = minimum 5 viva, 5 MCQ), each question clearly referencing the sub-topic it tests.
