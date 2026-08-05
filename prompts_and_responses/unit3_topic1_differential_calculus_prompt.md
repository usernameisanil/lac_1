# Generated Prompt — Topic: Differential Calculus (Limits, Continuity, Differentiability, Mean Value Theorems)

**Unit:** Unit 3 — Differential Calculus  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Differential Calculus — Limits, Continuity, Differentiability, and Mean Value Theorems"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Differential Calculus"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Limits and Continuity | Epsilon-delta definition of limit; continuity at a point and on an interval; one worked example using the epsilon-delta definition; one viva and one MCQ. |
| 2 | Differentiability | Definition of derivative as limit of difference quotient; relationship between differentiability and continuity; one worked example showing a function continuous but not differentiable; one viva and one MCQ. |
| 3 | Rolle's Theorem | Statement: f continuous on [a,b], differentiable on (a,b), f(a)=f(b) \Rightarrow \exists c \in (a,b) with f'(c)=0; geometric meaning; one worked example verifying hypotheses and finding c; one viva and one MCQ. |
| 4 | Lagrange's Mean Value Theorem (LMVT) | Statement and geometric interpretation (secant slope = tangent slope); one fully worked example finding c; one viva and one MCQ. |
| 5 | Cauchy's Mean Value Theorem (CMVT) | Statement; relation to LMVT (special case g(x)=x); one worked example; one viva and one MCQ. |

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
\lhead{Differential Calculus}
\rhead{Unit 3 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Differential Calculus: Limits, Continuity, Differentiability \& Mean Value Theorems} \\ \large Unit 3 -- Differential Calculus}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: using MVT to prove that a robot arm must reach a certain angular velocity between two positions; using continuity to ensure no abrupt jumps in a control signal; using differentiability to ensure smooth cam profiles in mechanical engineering.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- pgfplots: graph of a function with a limit illustrated (epsilon-delta bands).
- pgfplots: Rolle's Theorem — function with horizontal tangent between two equal-height points.
- pgfplots: LMVT — secant line and tangent line with equal slopes.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) check continuity, (b) check differentiability, (c) verify MVT hypotheses, (d) find c.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Epsilon-delta proof that lim_{x->2} (3x-1) = 5.
- **Example 2:** Verify Rolle's Theorem for f(x) = x(x-3) on [0,3]; find c.
- **Example 3 (Engineering):** Apply LMVT to f(x) = sin(x) on [0, pi/2]; find c; interpret as average rate of change of a sinusoidal signal.

### Section 7: Tabular Comparison / Workflow Reference
- Table: Rolle's vs LMVT vs CMVT — hypotheses, conclusion, geometric meaning, special relationship.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, \geq 1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: limit definition, continuity conditions, MVT statements, c-finding procedure.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (\geq 1 per sub-topic)**.
