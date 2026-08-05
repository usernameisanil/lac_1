# Generated Prompt — Topic: Functional Dependence & Approximations

**Unit:** Unit 4 — Multivariable Differentiation and Optimization  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Functional Dependence and Approximations: Jacobians and Taylor Expansion"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Functional Dependence and Approximations"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Jacobians and Functional Dependence | Define Jacobian J = ∂(u,v)/∂(x,y) as a 2×2 (and 3×3) determinant of partial derivatives; functional dependence test: functions u, v are functionally dependent iff J=0; Jacobian in coordinate transformations (Cartesian to polar); at least one worked example computing a Jacobian and testing functional dependence; one viva and one MCQ. |
| 2 | Taylor Expansion of Two-Variable Functions | State Taylor's theorem for f(x,y) about (a,b) up to second-order terms: f(a+h,b+k) = f(a,b) + [hfₓ+kfᵧ] + ½[h²fₓₓ+2hkfₓᵧ+k²fᵧᵧ] + …; Maclaurin's series as special case about (0,0); at least one worked example expanding a two-variable function to second order; one viva and one MCQ. |

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
\lhead{Jacobians, Functional Dependence, Taylor Expansion}
\rhead{Unit 4 -- Multivariable Differentiation}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Functional Dependence and Approximations} \\ \large Unit 4 -- Multivariable Differentiation and Optimization}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: coordinate transforms in robotics (Jacobian maps joint velocities to end-effector velocities; singular configurations occur at J=0, causing loss of control) and linearization of nonlinear systems around operating points using Taylor expansion (control design, sensor error analysis). Explain consequences of singularity and poor linearization.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include `booktabs` table with one row per sub-topic.
- Conclude with `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 2 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, determinant layout, Taylor series formula with all notation explained.

### Section 4: Visual Artifacts & Geometric Interpretation
- `tikz` diagram showing Cartesian-to-polar coordinate transform with area element interpretation of the Jacobian.
- `pgfplots` 3D surface of a function with its second-order Taylor approximation (paraboloid) plotted at a point.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) steps to compute a 2×2 and 3×3 Jacobian; (b) testing functional dependence using J=0; (c) constructing a Taylor expansion of f(x,y) to degree 2 about a given point.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Compute the Jacobian of u = x²−y², v = 2xy and test if u, v are functionally dependent.
- **Example 2:** Find the Jacobian of the polar transformation x = r cosθ, y = r sinθ; verify J = r.
- **Example 3 (Engineering):** Expand f(x,y) = eˣ cos y about (0,0) up to second-order terms; interpret the linear approximation as a sensor linearization in instrumentation.

### Section 7: Tabular Comparison / Workflow Reference
- Table: 1-variable Taylor series vs 2-variable Taylor series — formula, terms, radius of convergence concept, engineering use.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (6–8):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (5+):** Bold correct option, one-line explanation, distributed across sub-topics.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: Jacobian determinant formula, functional dependence test, 2-variable Taylor series up to second order, Maclaurin form.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 2 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Jacobian displayed as `\begin{vmatrix}...\end{vmatrix}` (determinant bars) consistently.
- [ ] Assessment section has at least **one viva and one MCQ per atomic sub-topic**.
