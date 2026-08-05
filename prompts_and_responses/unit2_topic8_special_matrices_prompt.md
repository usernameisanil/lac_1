# Generated Prompt — Topic: Special Matrices

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Special Matrices"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Special Matrices"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Symmetric and Skew-Symmetric Matrices | Define A = Aᵀ (symmetric) and A = −Aᵀ (skew-symmetric); eigenvalue properties (real for symmetric, pure imaginary or 0 for skew-symmetric); one worked example; one viva and one MCQ. |
| 2 | Orthogonal Matrices | Define QᵀQ = I; properties: det = ±1, eigenvalues |λ|=1, columns orthonormal; one worked example verifying orthogonality; one viva and one MCQ. |
| 3 | Hermitian and Skew-Hermitian Matrices | Define A = Aᴴ (Hermitian) and A = −Aᴴ (skew-Hermitian) for complex matrices; real eigenvalues for Hermitian; one worked example; one viva and one MCQ. |
| 4 | Idempotent and Nilpotent Matrices | Idempotent: A² = A (eigenvalues 0 or 1); nilpotent: Aᵏ = 0 for some k (all eigenvalues 0); one worked example of each; one viva and one MCQ. |
| 5 | Unitary and Normal Matrices | Unitary: UᴴU = I (complex analogue of orthogonal); normal: AAᴴ = AᴴA (unitarily diagonalizable); one worked example; one viva and one MCQ. |

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
\lhead{Special Matrices}
\rhead{Unit 2 -- LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Special Matrices} \\ \large Unit 2 -- Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)
- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: orthogonal matrices used in 3D rotation (robotics, computer graphics); Hermitian matrices in quantum mechanics (observables are Hermitian operators); idempotent matrices in projection operators used in regression and signal filtering.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)
- Include a `booktabs` table with one row per atomic sub-topic linking theory to engineering consequence.
- Conclude with a `learnbox` on core objectives.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)
For **each of the 5 atomic sub-topics**:
- Named `\subsection{}` entry.
- 2–4 lines conversational intuition.
- `infobox` with formal definitions, notation, key theorems.

### Section 4: Visual Artifacts & Geometric Interpretation
- TikZ diagram: 2D rotation matrix (orthogonal) showing unit circle invariance.
- TikZ diagram: idempotent matrix as projection onto a subspace.

### Section 5: Step-by-Step Algorithmic Solution / Workflow
- Workflow: how to verify each matrix type — systematic checklist for all 5 types.

### Section 6: Fully Worked Step-by-Step Numerical Examples
- **Example 1:** Verify a given 3×3 matrix is orthogonal; find its eigenvalues.
- **Example 2:** Show a complex 2×2 matrix is Hermitian; find its real eigenvalues.
- **Example 3 (Engineering):** Projection matrix P = A(AᵀA)⁻¹Aᵀ — show it is idempotent and symmetric; engineering context (least squares projection in regression).

### Section 7: Tabular Comparison / Workflow Reference
- Table: all 5 special matrix types — defining property, eigenvalue constraint, inverse formula, engineering application.

### Section 8: Common Student Mistakes & Pitfalls
- `mistakebox` with `tabular`: at least one row per atomic sub-topic.

### Section 9: Comprehensive Assessment Suite
1. **Viva-Voce Questions (8–10):** At least one per sub-topic.
2. **Descriptive Exam Questions (4–5):** Full problems with answer hints.
3. **MCQs (6+):** 4 options each, bold correct answer, one-line explanation, ≥1 per sub-topic.

### Section 10: Quick Recap & Formula Sheet
- `learnbox` with 6–8 bullet points: definitions and eigenvalue rules for all 5 special matrix types.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 5 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every custom box is properly opened and closed.
- [ ] All TikZ/pgfplots visuals are self-contained and compilable with `pdflatex`.
- [ ] Matrix notation uses `\begin{pmatrix}...\end{pmatrix}`.
- [ ] Assessment section has at least **5 viva questions and 5 MCQs (≥1 per sub-topic)**.
