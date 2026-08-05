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
| 1 | Characteristic Polynomial Definition | Define p(λ) = det(A − λI); state degree = n for n×n matrix; sign convention; one worked example computing p(λ) for a 2×2 matrix; one viva and one MCQ. |
| 2 | Roots as Eigenvalues | Explain roots of p(λ)=0 are eigenvalues; sum of eigenvalues = trace; product = determinant; one worked example verifying trace/det relations; one viva and one MCQ. |
| 3 | Cofactor Expansion for 3×3 | Step-by-step cofactor expansion to compute det(A−λI) for 3×3; one fully worked 3×3 example; one viva and one MCQ. |
| 4 | Shortcuts and Special Cases | Characteristic polynomial of diagonal, triangular, block-diagonal matrices; eigenvalues of A², A⁻¹, Aᵀ; one worked example using shortcuts; one viva and one MCQ. |
| 5 | Algebraic Multiplicity | Define algebraic multiplicity as root multiplicity in p(λ); examples of repeated eigenvalues; relation to diagonalizability; one viva and one MCQ. |

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
\lhead{Characteristic Equation}
\rhead{Unit 2 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Characteristic Equation} \\ \large Unit 2 -- Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: control systems — the characteristic equation of a system's transfer function determines stability (Routh-Hurwitz criterion); repeated roots cause marginally stable or unstable behaviour. Connect to vibration modes in mechanical systems.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- pgfplots plot of a cubic characteristic polynomial with roots clearly marked on the λ-axis.
- TikZ diagram showing how trace and determinant relate to sum/product of eigenvalues for a 2×2 matrix.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Full procedure for computing the characteristic polynomial and finding all eigenvalues for 2×2 and 3×3 matrices.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** 2×2 matrix — characteristic polynomial, eigenvalues, trace/det verification.
- **Example 2:** 3×3 matrix — cofactor expansion to get cubic polynomial, solve for eigenvalues.
- **Example 3 (Engineering):** System stability — characteristic equation of a 3×3 state matrix; determine if all eigenvalues have negative real part.

### Section 7: Tabular Comparison / Workflow Reference
- Table: characteristic polynomial for diagonal vs triangular vs general matrix — complexity, shortcut, example.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, ≥1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: characteristic polynomial formula, trace/det relations, cofactor expansion steps, shortcut rules, algebraic multiplicity definition.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (≥1 per sub-topic)**.
