# Generated Prompt — Topic: Rank, Index, Signature and Definite Forms

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Rank, Index, Signature, and Definite Forms"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Rank, Index, Signature, and Definite Forms"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Rank of a Quadratic Form | Define rank as number of non-zero eigenvalues (equivalently, rank of associated matrix A); one worked example; one viva and one MCQ. |
| 2 | Index of a Quadratic Form | Define index p as number of positive eigenvalues (positive terms in canonical form); one worked example computing index; one viva and one MCQ. |
| 3 | Signature of a Quadratic Form | Define signature as p − q where q = rank − p (number of negative eigenvalues); one worked example; one viva and one MCQ. |
| 4 | Sylvester's Law of Inertia | State: any two congruent real symmetric matrices have the same rank, index, and signature; invariance under non-singular linear transformations; one worked example verifying invariance; one viva and one MCQ. |
| 5 | Definite Forms and Sylvester's Criterion | Classify positive definite (all leading principal minors > 0), negative definite, semi-definite, indefinite; Sylvester's criterion; one worked example applying the criterion; one viva and one MCQ. |

**ENFORCEMENT RULES:**

1. The document must contain **exactly 5 named `\subsection{}` entries** in the main definitions section (Section 3).
2. The **assessment section** (Section 9) must contain **at least 5 viva-voce questions (≥1 per sub-topic)** and **at least 5 MCQs (≥1 per sub-topic)**.
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
\lhead{Rank, Index, Signature and Definite Forms}
\rhead{Unit 2 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Rank, Index, Signature, and Definite Forms} \\ \large Unit 2 -- Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: Lyapunov stability analysis requires the Lyapunov function V(x) = xᵀPx to be positive definite; checking Sylvester's criterion on P confirms the system is stable. Explain what indefinite P means for control design.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- TikZ diagram: sign pattern of eigenvalues → classification of quadratic form (PD, ND, indefinite, etc.).
- pgfplots: 3D plots of positive definite vs indefinite quadratic forms.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: (a) find eigenvalues, (b) compute rank/index/signature, (c) apply Sylvester's criterion, (d) classify definiteness.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** For Q = xᵀAx, compute rank, index, signature of A.
- **Example 2:** Apply Sylvester's criterion to a 3×3 symmetric matrix; classify.
- **Example 3 (Engineering):** Test if a Lyapunov matrix P from a control problem is positive definite.

### Section 7: Tabular Comparison / Workflow Reference
- Table: all five definiteness classes — eigenvalue condition, Sylvester criterion condition, geometric interpretation.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, ≥1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: rank/index/signature definitions, Sylvester's Law of Inertia, Sylvester's criterion steps, definiteness classification table.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (≥1 per sub-topic)**.
