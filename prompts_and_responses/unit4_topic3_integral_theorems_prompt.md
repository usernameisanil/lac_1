# Generated Prompt — Topic: Integral Theorems (Green's, Stokes', Gauss's)

**Unit:** Unit 4 — Multivariable Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Integral Theorems — Green's, Stokes', and Gauss's Divergence Theorem"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Integral Theorems"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Line Integrals | Define \int_C F \cdot dr; work done by a force field; one worked example computing a line integral along a given path; one viva and one MCQ. |
| 2 | Green's Theorem | State Green's theorem relating line integral around closed curve C to double integral over region D: \oint_C (P dx + Q dy) = \iint_D (Q_x - P_y) dA; one worked example; one viva and one MCQ. |
| 3 | Surface Integrals | Define \iint_S F \cdot dS (flux integral); parametric surface; one worked example computing flux through a given surface; one viva and one MCQ. |
| 4 | Stokes' Theorem | State Stokes' theorem: \oint_C F \cdot dr = \iint_S (\nabla \times F) \cdot dS; relationship to Green's theorem as special case; one worked example; one viva and one MCQ. |
| 5 | Gauss's Divergence Theorem | State: \iint_S F \cdot dS = \iiint_V (\nabla \cdot F) dV; physical interpretation as total outward flux = total source strength inside; one fully worked example; one viva and one MCQ. |

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
\lhead{Integral Theorems}
\rhead{Unit 4 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Integral Theorems: Green's, Stokes' and Gauss's Divergence Theorem} \\ \large Unit 4 --- Multivariable Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: Gauss's theorem in electrostatics (Gauss's law) — total electric flux through a closed surface equals enclosed charge / epsilon_0; Stokes' theorem in fluid mechanics — circulation of velocity equals flux of vorticity; Green's theorem for area calculation in CAD/CAM.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- TikZ: oriented closed curve C bounding region D for Green's theorem.
- TikZ: surface S with boundary curve C for Stokes' theorem, showing orientation.
- TikZ: closed surface S enclosing volume V for Gauss's theorem with outward normals.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) identify theorem type (line-to-area, line-to-surface, surface-to-volume), (b) verify orientation and conditions, (c) identify F, compute curl F or div F as needed, (d) set up and evaluate the resulting integral.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Green's Theorem: evaluate \oint_C (y^2 dx + x dy) over the unit circle.
- **Example 2:** Stokes' Theorem: evaluate \oint_C F \cdot dr for F = (y, z, x) over the boundary of the upper hemisphere.
- **Example 3 (Engineering):** Gauss's Divergence Theorem: compute the total flux of F = (x, y, z) out of the unit sphere; compare direct surface integral vs divergence theorem approach.

### Section 7: Tabular Comparison / Workflow Reference
- Table: Green's vs Stokes' vs Gauss's — domain dimension, converts, formula, orientation rule, engineering application.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: Green's, Stokes', Gauss's theorem statements; orientation conventions; when to use each theorem.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
