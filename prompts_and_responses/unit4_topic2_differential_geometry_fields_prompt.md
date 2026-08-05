# Generated Prompt — Topic: Differential Geometry & Fields

**Unit:** Unit 4 — Multivariable Differentiation and Optimization  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Differential Geometry and Fields"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Differential Geometry and Fields"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Gradient and Tangent Plane / Normal Line | Define gradient ∇f = (∂f/∂x, ∂f/∂y, ∂f/∂z); equation of tangent plane and normal line to surface F(x,y,z)=0 at a point; directional derivative as dot product of gradient with unit vector; at least one worked example finding tangent plane and normal to a surface; one viva and one MCQ. |
| 2 | Divergence and Curl | Define divergence div **F** = ∇·**F** and curl **F** = ∇×**F** for a vector field **F** = (P,Q,R); physical interpretation (source/sink for div, rotation for curl); solenoidal and irrotational fields; at least one worked example computing div and curl; one viva and one MCQ. |

**ENFORCEMENT RULES:**

1. The document must contain **exactly 2 named `\subsection{}` entries** in the main definitions section (Section 3).
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
\lhead{Differential Geometry and Fields}
\rhead{Unit 4 -- Multivariable Differentiation}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Differential Geometry and Fields} \\ \large Unit 4 -- Multivariable Differentiation and Optimization}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: electromagnetic field analysis — how the gradient gives the electric field **E** = −∇V from potential V, divergence of **E** relates to charge density (Gauss's law), and curl of **E** = 0 for electrostatics. Explain what happens if divergence/curl are computed wrongly in finite element analysis of EM devices.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per sub-topic (gradient/tangent plane row and divergence/curl row) linking theory to engineering consequence.
- Conclude with `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 2 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition with geometric/physical interpretation.
- `infobox` with formal definitions, vector notation, key identities.

### Section 4: Visual Artifacts & Geometric Interpretation
- `tikz` diagram showing gradient vector perpendicular to level curve in 2D.
- `pgfplots` 3D surface with tangent plane drawn at a point.
- `tikz` diagram illustrating divergence (outward flux arrows) vs curl (circulation arrows) around a point.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) computing gradient and using it to write tangent plane equation; (b) computing divergence and curl of a given vector field; (c) checking if a field is solenoidal or irrotational.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Find the gradient of f(x,y,z) = x²y + yz² at (1,2,1); find the equation of the tangent plane to x²+y²+z² = 14 at (1,2,3).
- **Example 2:** Given **F** = (x²y, yz², zx²), compute ∇·**F** and ∇×**F**; determine if **F** is solenoidal or irrotational.
- **Example 3 (Engineering):** In fluid mechanics, velocity field **V** = (2x, −2y, 0). Verify it is solenoidal (incompressible flow). Compute curl and interpret physically.

### Section 7: Tabular Comparison / Workflow Reference
- Table comparing scalar fields vs vector fields: gradient vs divergence vs curl — input type, output type, formula, physical meaning, engineering example.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (6–8):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (5+):** Bold correct option, one-line explanation, distributed across sub-topics.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: gradient formula, tangent plane equation, divergence formula, curl formula, solenoidal/irrotational conditions.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 2 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Vector fields use bold notation `\mathbf{F}` or `\vec{F}` consistently.
- [ ] Assessment section has at least **one viva and one MCQ per atomic sub-topic**.
