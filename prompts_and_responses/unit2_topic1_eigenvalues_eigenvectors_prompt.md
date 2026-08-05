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
| 1 | Definition of Eigenvalues and Eigenvectors | Define eigenvalue λ and eigenvector **x** via A**x** = λ**x**; explain eigenspace; provide one worked example finding eigenvalues from det(A − λI) = 0; one viva and one MCQ on definition. |
| 2 | Characteristic Equation and Characteristic Polynomial | Define characteristic polynomial p(λ) = det(A − λI); state degree = matrix order; provide one worked example computing characteristic polynomial; one viva and one MCQ. |
| 3 | Finding Eigenvectors via Row Reduction | For each eigenvalue, solve (A − λI)**x** = **0** using row reduction; show free variables and eigenspace basis; provide one fully worked example; one viva and one MCQ. |
| 4 | Geometric vs Algebraic Multiplicity | Define algebraic multiplicity (root multiplicity in characteristic polynomial) vs geometric multiplicity (dimension of eigenspace); state the inequality geo ≤ alg; provide one example where they differ; one viva and one MCQ. |
| 5 | Eigenvalues of Special Matrices | State eigenvalue properties: triangular matrix (diagonal entries), symmetric matrix (real eigenvalues), orthogonal matrix (|λ|=1), idempotent (λ=0 or 1), nilpotent (λ=0 all); one viva and one MCQ. |

**ENFORCEMENT RULES:**

1. The document must contain **exactly 5 named `\subsection{}` entries** in the main definitions section (Section 3).
2. The **assessment section** (Section 9) must contain **at least 5 viva-voce questions (≥1 per sub-topic)** and **at least 5 MCQs (≥1 per sub-topic)**.
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

% Define custom environments
\newtcolorbox{curiositybox}[1][]{colback=yellow!10, colframe=orange!80, title=#1, breakable}
\newtcolorbox{infobox}[1][]{colback=blue!5, colframe=blue!60, title=#1, breakable}
\newtcolorbox{mistakebox}[1][]{colback=red!5, colframe=red!60, title=#1, breakable}
\newtcolorbox{learnbox}[1][]{colback=green!5, colframe=green!60, title=#1, breakable}

% Header and Footer
\pagestyle{fancy}
\fancyhf{}
\lhead{Eigenvalues and Eigenvectors}
\rhead{Unit 2 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Eigenvalues and Eigenvectors} \\ \large Unit 2 -- Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: structural vibration analysis — natural frequencies of a building or bridge are the eigenvalues of the stiffness matrix; mode shapes are eigenvectors. Explain what happens when a bridge's natural frequency matches wind frequency (resonance — Tacoma Narrows). Connect to Google PageRank (dominant eigenvector of web graph), PCA in data science.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Contrast understanding vs misunderstanding eigenvalues.
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- TikZ diagram showing eigenvector direction preserved under matrix transformation (before/after vectors for a 2×2 matrix).
- pgfplots plot of characteristic polynomial p(λ) vs λ for a 2×2 example, roots clearly marked.
- TikZ diagram illustrating geometric vs algebraic multiplicity (eigenspace dimension).

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Full procedure: (a) form A−λI, (b) compute det=0 to get characteristic polynomial, (c) find roots λ, (d) for each λ solve (A−λI)**x**=**0** by row reduction, (e) identify eigenspace basis.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** 2×2 matrix — find eigenvalues and eigenvectors; verify A**x**=λ**x**.
- **Example 2:** 3×3 triangular matrix — eigenvalues by inspection, eigenvectors by row reduction.
- **Example 3 (Engineering):** Vibration of a 2-DOF spring-mass system — stiffness matrix K, find natural frequencies (√λ) and mode shapes.

### Section 7: Tabular Comparison / Workflow Reference
- Table: algebraic multiplicity vs geometric multiplicity — definition, example, implication for diagonalizability.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, ≥1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: eigenvalue equation, characteristic polynomial, row-reduction workflow, multiplicity definitions, special matrix eigenvalue rules.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters (`%`, `&`, `_` outside math, `#` outside commands).
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (≥1 per sub-topic)**.
