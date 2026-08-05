# Generated Prompt — Topic: Ordinary Differential Equations

**Unit:** Unit 3 — Differential Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Ordinary Differential Equations"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Ordinary Differential Equations"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | First-Order ODEs (Separable and Linear) | Separable equations dy/dx = f(x)g(y); integrating factor for linear dy/dx + P(x)y = Q(x); one worked example of each type; one viva and one MCQ. |
| 2 | Exact Differential Equations | Condition M_y = N_x; finding integrating factor when not exact; one fully worked example; one viva and one MCQ. |
| 3 | Second-Order Linear ODEs with Constant Coefficients | Homogeneous: auxiliary equation; three cases (distinct real, repeated, complex roots); particular integral for non-homogeneous; one worked example; one viva and one MCQ. |
| 4 | Applications to Engineering Systems | Spring-mass-damper system mx'' + cx' + kx = F(t); RLC circuit analogy; free vs forced vibration; resonance condition; one fully worked engineering example; one viva and one MCQ. |
| 5 | Series Solution / Special Functions (Intro) | Power series method for ODEs near ordinary point; concept of Frobenius method; introduction to Bessel functions of first kind; one worked example using power series; one viva and one MCQ. |

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
\lhead{Ordinary Differential Equations}
\rhead{Unit 3 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Ordinary Differential Equations} \\ \large Unit 3 -- Differential Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: spring-mass-damper system modelling vibration isolation in a car suspension; RLC circuit transient response; population growth ODE in resource management. Emphasise that virtually every dynamic engineering system is governed by an ODE.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- pgfplots: solution curves for a separable ODE (direction field + family of curves).
- pgfplots: overdamped, critically damped, underdamped second-order responses on one plot.
- TikZ: spring-mass-damper mechanical system diagram.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) identify ODE type, (b) choose solution method, (c) find general solution, (d) apply ICs/BCs, (e) interpret physically.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Solve dy/dx + 2y = 4e^{-x} using integrating factor; verify solution.
- **Example 2:** Solve the homogeneous second-order ODE y'' - 3y' + 2y = 0; find particular solution given ICs.
- **Example 3 (Engineering):** Spring-mass-damper: m=1, c=3, k=2, F=0; find x(t) given x(0)=1, x'(0)=0; classify damping type.

### Section 7: Tabular Comparison / Workflow Reference
- Table: ODE types — form, method, integrating factor, solution structure.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: integrating factor formula, auxiliary equation cases, PI method, spring-mass-damper analogy, resonance condition.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] **Derivative notation:** All time derivatives MUST use `\dot{x}`, `\ddot{x}` (LaTeX commands) --- do NOT use Unicode dot characters or prime symbols (˙, ´, \u2019) as these will cause compilation errors.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
