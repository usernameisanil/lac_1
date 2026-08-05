# Generated Prompt — Topic: Differential Calculus of Several Variables

**Unit:** Unit 4 — Multivariable Differentiation and Optimization  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Differential Calculus of Several Variables"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Differential Calculus of Several Variables"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Functions of Several Variables, Limits and Continuity | Define f(x,y), domain, level curves; formal epsilon-delta limit definition; continuity conditions; at least one worked example showing a limit exists (path-independent) and one showing a limit does not exist (path-dependent); one viva and one MCQ on limit evaluation. |
| 2 | Partial Derivatives and Higher-Order Partial Derivatives | Define ∂f/∂x and ∂f/∂y as limits; second-order partials ∂²f/∂x², ∂²f/∂y², ∂²f/∂x∂y; Clairaut's theorem on equality of mixed partials; at least one worked example computing all second-order partials; one viva and one MCQ on higher-order partials. |
| 3 | Total Derivative and Chain Rule | Define total differential df = (∂f/∂x)dx + (∂f/∂y)dy; chain rule for z=f(x(t),y(t)) and for z=f(x(s,t),y(s,t)); implicit differentiation dy/dx via total derivative; at least one worked example using the chain rule; one viva and one MCQ. |

**ENFORCEMENT RULES:**

1. The document must contain **exactly 3 named `\subsection{}` entries** in the main definitions section (Section 3).
2. The **assessment section** (Section 9) must contain **at least one viva-voce question and one MCQ per atomic sub-topic**.
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
\newtcolorbox{curiositybox}[1]{colback=yellow!10, colframe=orange!80, title=#1, breakable}
\newtcolorbox{infobox}[1]{colback=blue!5, colframe=blue!60, title=#1, breakable}
\newtcolorbox{mistakebox}[1]{colback=red!5, colframe=red!60, title=#1, breakable}
\newtcolorbox{learnbox}[1]{colback=green!5, colframe=green!60, title=#1, breakable}

% Header and Footer
\pagestyle{fancy}
\fancyhf{}
\lhead{Differential Calculus of Several Variables}
\rhead{Unit 4 -- Multivariable Differentiation}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Differential Calculus of Several Variables} \\ \large Unit 4 -- Multivariable Differentiation and Optimization}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Use a heat distribution scenario: temperature T(x,y,z) in a metal plate, where partial derivatives determine heat flux and continuity ensures no thermal shocks. Explain what happens in FEM simulation if limits/continuity are violated.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Contrast understanding vs misunderstanding of limits and partial derivatives in multivariable settings.
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 3 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- 3D surface plot of z = x²+y² using `pgfplots` (surf, with colormap).
- Level curves (contour plot) of a function in 2D using `pgfplots`.
- Geometric arrow diagram showing the gradient vector direction in `tikz`.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow for: (a) checking if a limit exists using paths, (b) computing all partial derivatives up to order 2, (c) applying the chain rule step-by-step.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Evaluate lim(x,y)→(0,0) of xy/(x²+y²) and show it does not exist.
- **Example 2:** Find all second-order partial derivatives of f(x,y) = x³y² − 2x²y + y³ and verify Clairaut's theorem.
- **Example 3 (Engineering):** A thin rectangular plate has temperature T(x,y) = 100 − 2x² − 3y². Find ∂T/∂x, ∂T/∂y, and the total derivative dT along a path x=t, y=2t.

### Section 7: Tabular Comparison / Workflow Reference
- Table comparing: ordinary derivative vs partial derivative vs total derivative — definition, notation, when used, geometric meaning.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic covering typical errors.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (6–8):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (5+):** 4 options each, bold correct answer, one-line explanation, distributed across sub-topics.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: core formulas for partial derivatives, chain rule, total differential, limit existence criteria.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 3 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters (`%`, `&`, `_` outside math, `#` outside commands).
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}` where applicable.
- [ ] Assessment section has at least **one viva and one MCQ per atomic sub-topic**.
