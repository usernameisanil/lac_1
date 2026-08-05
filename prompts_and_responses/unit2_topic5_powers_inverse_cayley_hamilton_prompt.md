# Generated Prompt — Topic: Powers and Inverse via Cayley-Hamilton

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Powers and Inverse via Cayley-Hamilton"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Powers and Inverse via Cayley-Hamilton"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Power Recurrence via CH | Use p(A)=0 to write Aⁿ as a linear combination of I, A, ..., A^{n-1}; compute A³, A⁴ etc. by substitution; one worked example; one viva and one MCQ. |
| 2 | Finding A⁻¹ via CH | From p(A)=0, solve for A⁻¹ as polynomial in A (requires det≠0); one fully worked example; one viva and one MCQ. |
| 3 | Matrix Polynomials and Expressions | Evaluate f(A) = αA² + βA + γI using CH reduction; one worked example; one viva and one MCQ. |
| 4 | CH vs Diagonalization for Powers | Compare efficiency: CH (always works if p(A) known) vs diagonalization (requires n independent eigenvectors); decision criteria; one viva and one MCQ. |
| 5 | Engineering Applications of Matrix Powers | Discrete dynamical systems xₙ = Axₙ₋₁ → xₙ = Aⁿx₀; long-term behaviour via dominant eigenvalue; Markov chain steady state; one applied example; one viva and one MCQ. |

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
\lhead{Powers and Inverse via Cayley-Hamilton}
\rhead{Unit 2 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Powers and Inverse via Cayley-Hamilton} \\ \large Unit 2 -- Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: computing Aⁿ for large n in discrete-time state-space models (robotics, signal processing); efficiently evaluating matrix expressions in real-time control without repeated matrix multiplication.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- TikZ diagram: CH reduction workflow — Aⁿ → express using p(A)=0 → lower-degree terms.
- pgfplots plot showing exponential growth of entries in Aⁿ vs n for an unstable 2×2 matrix.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Algorithm: (a) compute p(λ), (b) write p(A)=0, (c) reduce Aⁿ step by step, (d) extract A⁻¹ if needed.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Compute A⁶ for a 2×2 matrix using CH power recurrence.
- **Example 2:** Find A⁻¹ using CH for a 3×3 matrix; verify AA⁻¹ = I.
- **Example 3 (Engineering):** Discrete population model: x_{n+1} = Ax_n; compute x₅ using Aⁿ via CH; interpret steady-state.

### Section 7: Tabular Comparison / Workflow Reference
- Table: CH method vs Diagonalization method for computing Aⁿ — conditions, steps, efficiency, when to use.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, ≥1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: CH power recurrence formula, A⁻¹ via CH, matrix polynomial reduction, CH vs diagonalization comparison.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (≥1 per sub-topic)**.
