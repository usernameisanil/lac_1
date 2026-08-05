# Generated Prompt — Topic: Limits and Continuity of Multivariable Functions

**Unit:** Unit 4 — Multivariable Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Limits and Continuity of Multivariable Functions"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Limits and Continuity of Multivariable Functions"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Limits of Multivariable Functions | Epsilon-delta definition of limit for f(x,y); path-independence requirement; one worked example evaluating a limit; one viva and one MCQ. |
| 2 | Non-Existence of Limits (Two-Path Test) | Method: if f gives different values along two distinct paths to (a,b), limit does not exist; one worked example **explicitly showing two different paths (e.g. y=0 and y=x) each evaluated separately, with clearly different limiting values, proving non-existence**; one viva and one MCQ. |
| 3 | Continuity of Multivariable Functions | Definition: f continuous at (a,b) iff limit exists, equals f(a,b); joint continuity vs separate continuity; one worked example testing continuity; one viva and one MCQ. |
| 4 | Iterated Limits | Define iterated limits lim_{x->a} lim_{y->b} f and lim_{y->b} lim_{x->a} f; show they can differ even when the double limit exists; one worked example where iterated limits differ; one viva and one MCQ. |
| 5 | Engineering Relevance of Continuity | Explain why discontinuities in temperature fields, stress fields, or fluid velocity fields signal physical phenomena (shocks, phase boundaries); one applied example discussing continuity of a given field function; one viva and one MCQ. |

**ENFORCEMENT RULES:**

1. The document must contain **exactly 5 named `\subsection{}` entries** in the main definitions section (Section 3).
2. The **assessment section** (Section 9) must contain **at least 5 viva-voce questions (\geq 1 per sub-topic)** and **at least 5 MCQs (\geq 1 per sub-topic)**.
3. Each atomic sub-topic must have a dedicated `infobox`, at least one fully worked example, and at least one assessment item.
4. **Sub-topic 2 non-existence example MUST show two explicitly named paths, compute the limit along each path separately, and state the conclusion that limit does not exist because the two path-limits differ.**

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
\lhead{Limits and Continuity --- Multivariable}
\rhead{Unit 4 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Limits and Continuity of Multivariable Functions} \\ \large Unit 4 --- Multivariable Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: temperature distribution T(x,y,z) across a metal plate; pressure field p(x,y) in a fluid flow; stress field \sigma(x,y) in a structural member. Show that a discontinuity in these fields signals a physical boundary, crack, or shock.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- pgfplots 3D surface plot of a function approaching (0,0) along different paths.
- TikZ top-view diagram showing multiple paths to the origin (y=0, y=x, y=x^2).
- pgfplots 3D plot of a function with a discontinuity at origin.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) try direct substitution, (b) if 0/0 form, try path test, (c) if paths agree, attempt formal limit proof, (d) test continuity.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Evaluate lim_{(x,y)->(1,2)} (x^2 + y) by direct substitution.
- **Example 2 (Two-Path Test):** Show lim_{(x,y)->(0,0)} xy/(x^2+y^2) does not exist. **Explicitly evaluate along path 1: y=0 (giving limit 0), then path 2: y=x (giving limit 1/2). State conclusion: since the two path-limits differ, the limit does not exist.**
- **Example 3 (Engineering):** Test continuity of a piecewise-defined temperature field T(x,y) at the origin; interpret the result physically.

### Section 7: Tabular Comparison / Workflow Reference
- Table: limit exists vs limit does not exist — conditions, test method, example.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: epsilon-delta definition, path-independence rule, two-path test procedure, continuity definition, iterated limits caution.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] **Sub-topic 2 Example 2 must show two explicitly named paths with separately computed limits and a stated conclusion.**
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
