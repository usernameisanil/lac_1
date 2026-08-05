# Generated Prompt — Topic: Partial Derivatives and Applications

**Unit:** Unit 3 — Differential Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Partial Derivatives and Applications"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Partial Derivatives and Applications"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Partial Derivatives (First and Higher Order) | Define \partial f/\partial x, \partial f/\partial y; mixed partials and Clairaut's theorem; one worked example computing all second-order partials; one viva and one MCQ. |
| 2 | Euler's Theorem for Homogeneous Functions | Define homogeneous function of degree n; state Euler's theorem: x(\partial f/\partial x) + y(\partial f/\partial y) = nf; extension to second order; one worked example verifying Euler's theorem; one viva and one MCQ. |
| 3 | Total Derivative and Chain Rule | Total differential df; chain rule for composite functions (one and two independent variables); one worked example using chain rule; one viva and one MCQ. |
| 4 | Jacobian Determinants | Define Jacobian J = \partial(u,v)/\partial(x,y); properties (product rule, inverse); one worked example computing a Jacobian; one viva and one MCQ. |
| 5 | Maxima and Minima of Functions of Two Variables | Second-order conditions: D = f_{xx}f_{yy} - f_{xy}^2; saddle point; Lagrange multipliers for constrained optimisation; one fully worked example finding critical points and classifying; one viva and one MCQ. |

**ENFORCEMENT RULES:**

1. The document must contain **exactly 5 named `\subsection{}` entries** in the main definitions section (Section 3).
2. The **assessment section** (Section 9) must contain **at least 5 viva-voce questions (\geq 1 per sub-topic)** and **at least 5 MCQs (\geq 1 per sub-topic)**.
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
\lhead{Partial Derivatives and Applications}
\rhead{Unit 3 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Partial Derivatives and Applications} \\ \large Unit 3 -- Differential Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: optimising the shape of a heat fin (maximising heat dissipation subject to volume constraint using Lagrange multipliers); computing sensitivity of a circuit output to component variations using partial derivatives.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- pgfplots 3D surface showing partial derivatives as slopes of cross-sections.
- pgfplots 3D surface with saddle point and local maximum labelled.
- TikZ contour diagram with gradient direction.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) compute first partials, (b) solve f_x=0, f_y=0 for critical points, (c) compute D and classify, (d) for constrained: set up Lagrangian.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Compute all second-order partial derivatives of f(x,y) = x^3 y^2 + e^{xy}; verify Clairaut's theorem.
- **Example 2:** Verify Euler's theorem for f(x,y) = (x^2 + y^2)^{1/2}.
- **Example 3 (Engineering):** Find dimensions of a rectangular box of maximum volume with fixed surface area using Lagrange multipliers.

### Section 7: Tabular Comparison / Workflow Reference
- Table: critical point classification using D and f_{xx} — all four cases.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: partial derivative definitions, Euler's theorem, total differential, Jacobian formula, second-order test.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
