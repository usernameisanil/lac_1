# Generated Prompt — Topic: Optimization — Maxima, Minima, and Lagrange Multipliers

**Unit:** Unit 4 — Multivariable Differentiation and Optimization  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Optimization: Maxima, Minima, and Lagrange Multipliers"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Optimization"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Maxima and Minima (Critical Points) | Define critical points: ∂f/∂x = 0 and ∂f/∂y = 0 simultaneously; classify as local maximum, local minimum, or saddle point using the discriminant; at least one worked example finding all critical points of a two-variable function; one viva and one MCQ on classification. |
| 2 | Second Derivative Test (Discriminant Method) | Define discriminant D = fₓₓfᵧᵧ − (fₓᵧ)²; classification rules: D>0 and fₓₓ>0 → local min; D>0 and fₓₓ<0 → local max; D<0 → saddle; D=0 → inconclusive; at least one worked example applying the discriminant test with a borderline/saddle point case; one viva and one MCQ. |
| 3 | Lagrange Multipliers and Constrained Optimization | Define method of Lagrange multipliers: optimize f(x,y) subject to g(x,y)=0 by solving ∇f = λ∇g simultaneously with g=0; extension to two constraints; geometric interpretation (tangency of level curves); at least one worked example minimizing/maximizing with a constraint; one viva and one MCQ. |

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
\lhead{Optimization: Maxima, Minima, Lagrange Multipliers}
\rhead{Unit 4 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Optimization: Maxima, Minima, and Lagrange Multipliers} \\ \large Unit 4 -- Multivariable Differentiation and Optimization}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: structural design optimization — minimizing material cost (weight) while satisfying stress constraints; rocket trajectory optimization; antenna shape design. Explain how missing a saddle point or applying an unconstrained method to a constrained problem leads to structural failure or cost overruns.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include `booktabs` table with one row per sub-topic (critical points row, discriminant row, Lagrange row).
- Conclude with `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 3 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition (e.g., saddle point = mountain pass, Lagrange = finding highest point on a curved hill while staying on a path).
- `infobox` with formal definitions, discriminant formula, Lagrange conditions.

### Section 4: Visual Artifacts & Geometric Interpretation
- `pgfplots` 3D surface plot of f(x,y) = x³ − 3x + y² showing saddle point and local minimum.
- `tikz` 2D level curve diagram showing the geometric meaning of Lagrange multipliers (tangency of ∇f and ∇g).
- `pgfplots` contour plot with constraint curve overlaid.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow A (unconstrained): find critical points → compute D → classify.
- Workflow B (Lagrange): write Lagrange equations ∇f = λ∇g and g=0 → solve system → evaluate f at solutions → classify.
- Include decision tree for interpreting D values.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Find and classify all critical points of f(x,y) = x³ + y³ − 3x − 12y + 20.
- **Example 2:** Find the critical points of f(x,y) = x⁴ + y⁴ − 2x² — demonstrate the inconclusive case (D=0) and handle it by inspection.
- **Example 3 (Engineering):** Minimize the surface area of a rectangular box with volume 8 m³ (no lid) using Lagrange multipliers; interpret the optimal dimensions in engineering terms.

### Section 7: Tabular Comparison / Workflow Reference
- Table: unconstrained optimization (critical point + discriminant) vs constrained optimization (Lagrange multipliers) — when to use, equation setup, number of equations, saddle interpretation, engineering example.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic (e.g., forgetting to test D=0 case, confusing global vs local extrema, incorrect Lagrange system setup).

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (6–8):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (5+):** Bold correct option, one-line explanation, distributed across sub-topics.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: critical point conditions, discriminant D formula and classification table, Lagrange multiplier system of equations, when each method applies.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 3 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Discriminant D is defined clearly before use; classification table included in the `infobox`.
- [ ] Assessment section has at least **one viva and one MCQ per atomic sub-topic**.
