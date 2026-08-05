# Generated Prompt — Topic: Multiple Integrals (Double and Triple)

**Unit:** Unit 4 — Multivariable Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Multiple Integrals — Double and Triple Integrals"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Multiple Integrals"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Double Integrals over Rectangles | Iterated integral \int_a^b \int_c^d f(x,y) dy dx; Fubini's theorem; one worked example; one viva and one MCQ. |
| 2 | Double Integrals over General Regions | Type I (y-simple) and Type II (x-simple) regions; setting up limits for non-rectangular regions; one worked example; one viva and one MCQ. |
| 3 | Change of Order of Integration | Sketch region, swap limits, re-express bounds; one worked example where changing order makes the integral tractable; one viva and one MCQ. |
| 4 | Triple Integrals | Extension to \iiint_E f(x,y,z) dV; six possible iteration orders; limits for a tetrahedron or other standard solid; one worked example; one viva and one MCQ. |
| 5 | Applications: Area, Volume, Mass | Area = \iint_R dA; volume under surface; mass = \iint_R \rho dA; one worked application example; one viva and one MCQ. |

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
\lhead{Multiple Integrals}
\rhead{Unit 4 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Multiple Integrals: Double and Triple Integrals} \\ \large Unit 4 --- Multivariable Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: computing the mass of a non-uniform plate; finding the volume of a complex mould cavity; computing the centroid of a turbine blade cross-section. Show that all reduce to setting up and evaluating a multiple integral over a region with the right density function.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- pgfplots: filled Type I region between two curves, with limits labelled.
- pgfplots: filled Type II region with limits labelled.
- TikZ: 3D tetrahedron with integration limits for a triple integral.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) sketch region, (b) identify Type I or II, (c) write limits, (d) evaluate inner integral, (e) evaluate outer integral, (f) interpret result.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** \iint_R (x+y) dA over rectangle [0,2]x[0,3].
- **Example 2 (Change of Order):** \int_0^1 \int_x^1 e^{y^2} dy dx — change order to make tractable; evaluate to (e-1)/2.
- **Example 3 (Engineering):** Triple integral to find the mass of a solid with density \rho = 6 over the tetrahedron bounded by x+y+z=1 and coordinate planes.

### Section 7: Tabular Comparison / Workflow Reference
- Table: Type I vs Type II regions — definition, x-limits, y-limits, when to use.
- Table: six iteration orders for triple integrals — dz dy dx, dy dz dx, dx dy dz, etc.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: Fubini's theorem, Type I/II region setup, change-of-order procedure, triple integral limits for tetrahedron, mass/volume formulas.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
