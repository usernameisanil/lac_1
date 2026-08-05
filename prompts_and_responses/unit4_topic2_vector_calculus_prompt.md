# Generated Prompt — Topic: Vector Calculus (Gradient, Divergence, Curl)

**Unit:** Unit 4 — Multivariable Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Vector Calculus — Gradient, Divergence, and Curl"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Vector Calculus (Gradient, Divergence, Curl)"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Gradient of a Scalar Field | Define \nabla f = (\partial f/\partial x)\mathbf{i} + ...; directional derivative D_u f = \nabla f \cdot \hat{u}; steepest ascent direction; one worked example; one viva and one MCQ. |
| 2 | Divergence of a Vector Field | Define \nabla \cdot \mathbf{F}; physical meaning (source/sink density); solenoidal field (div=0); one worked example; one viva and one MCQ. |
| 3 | Curl of a Vector Field | Define \nabla \times \mathbf{F} via 3x3 determinant form; physical meaning (rotation/vorticity); irrotational field (curl=0); one worked example; one viva and one MCQ. |
| 4 | Vector Identities | Key identities: div(curl F)=0, curl(grad f)=0, Laplacian \nabla^2 f; one worked example verifying an identity; one viva and one MCQ. |
| 5 | Engineering Applications | Gauss's divergence theorem (statement only); Stokes' theorem (statement only); physical interpretation in fluid flow and electromagnetism; one applied example; one viva and one MCQ. |

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
\lhead{Vector Calculus}
\rhead{Unit 4 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Vector Calculus: Gradient, Divergence and Curl} \\ \large Unit 4 --- Multivariable Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: gradient of temperature field tells a heat-seeking robot which direction to move; divergence of velocity field tells a CFD engineer where fluid is being created or destroyed; curl tells a turbomachinery engineer how much swirl exists in a flow.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- TikZ vector field diagram showing gradient vectors perpendicular to level curves.
- TikZ: source (div>0) and sink (div<0) vector field patterns.
- TikZ: curl as rotation of a small paddle wheel in a velocity field.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) identify scalar vs vector field, (b) compute gradient/divergence/curl using nabla, (c) check solenoidal/irrotational conditions, (d) verify vector identity if required.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Compute gradient of f = x^2 y + yz^2; find directional derivative in direction (1,1,1)/sqrt(3).
- **Example 2:** Compute divergence and curl of F = (xy, yz, zx); check if solenoidal or irrotational.
- **Example 3 (Engineering):** Given a velocity field V = (2x, -2y, 0), compute div V and curl V; interpret as incompressible irrotational flow.

### Section 7: Tabular Comparison / Workflow Reference
- Table: gradient vs divergence vs curl — input type, output type, operator, physical meaning, zero condition and its name.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: gradient formula, divergence formula, curl determinant form, key vector identities, solenoidal/irrotational definitions.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] **Cross product MUST be written as `\times` (e.g. `\nabla \times \mathbf{F}`). Do NOT use `\cross` as it is undefined in standard LaTeX and will cause a compilation error.**
- [ ] **Divergence MUST be written as `\nabla \cdot` (e.g. `\nabla \cdot \mathbf{F}`). Do NOT use `\div` alone as a vector-calculus operator (it renders as the division symbol \div, not divergence).**
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
