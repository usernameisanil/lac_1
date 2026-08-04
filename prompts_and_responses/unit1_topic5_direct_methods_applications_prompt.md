# Generated Prompt — Topic: Direct Methods & Applications

**Unit:** Unit 1 — Matrix Algebra and Linear Systems
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)
**Target Audience:** B.Tech Engineering Students

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Direct Methods — Cramer's Rule, Matrix Inversion Method, and Applications to Engineering Systems"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers **3 atomic sub-topics**. Each MUST appear as a separate named `\subsection{}` with its own `infobox`, at least one dedicated worked example, and at least one viva/MCQ question.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|---|---|
| 1 | **Cramer's Rule** | `infobox`: formal statement — for n×n system Ax=b with det(A)≠0: x_i = det(A_i)/det(A) where A_i is matrix A with i-th COLUMN replaced by b. Proof sketch: multiply Ax=b by adj(A) on left → adj(A)·b = det(A)·x. Conditions: square system, non-singular A. Limitation: O(n·n!) — impractical for n>3. Worked Example: solve a 3×3 system fully — compute det(A) by cofactor expansion, form A1, A2, A3 (show column replacement clearly), compute each det, divide — all steps shown. Verify by back-substitution. |
| 2 | **Matrix Inversion Method** | `infobox`: x = A^{-1}b; A^{-1} = adj(A)/det(A); full adjugate derivation — cofactor C_{ij}=(−1)^{i+j}M_{ij}, cofactor matrix, adjugate = transpose of cofactor matrix; left-multiply: x = A^{-1}b NOT b·A^{-1} (non-commutativity). Properties: (AB)^{-1}=B^{-1}A^{-1}; (A^T)^{-1}=(A^{-1})^T. Advantage: compute A^{-1} once, solve for multiple b vectors cheaply. Cost: O(n³). Worked Example: solve a 3×3 engineering system (e.g., 3-mesh circuit) using matrix inversion — compute all 9 cofactors individually showing each 2×2 determinant, build adjugate, compute A^{-1}, multiply A^{-1}·b step by step, verify A·x=b. |
| 3 | **Applications to Engineering Systems** | `infobox`: modelling framework — identify unknowns, write governing equations (KVL, KCL, equilibrium, material balance), form Ax=b, choose method (Cramer's for n≤3, matrix inversion for repeated b, Gauss for large n), interpret solution physically. Decision framework table: problem type vs recommended method. Worked Examples (2 required): (a) 3-mesh electrical circuit — apply Cramer's rule to find mesh currents, compute power P=IV; (b) 3-reactor chemical plant material balance — form 3×3 system, solve via matrix inversion, interpret concentrations physically. |

**ENFORCEMENT RULE:** 3 named `\subsection{}` entries required. Sub-Topic 3 must contain TWO engineering application examples (electrical + chemical/mechanical). Decision framework table comparing all 5 methods mandatory. Assessment must have at least 2 viva questions and 2 MCQs per sub-topic.

---

## 1. LATEX PREAMBLE & CONFIGURATION REQUIREMENTS

```latex
\documentclass[12pt,a4paper]{article}
\usepackage{amsmath, amssymb, geometry, booktabs, xcolor, hyperref,
            listings, pgfplots, tcolorbox, enumitem, fancyhdr, tikz, array}
\usepgfplotslibrary{fillbetween}
\geometry{margin=2.5cm}
\pgfplotsset{compat=1.18}
\tcbuselibrary{skins, breakable}

\newtcolorbox{curiositybox}[1][]{colback=yellow!10, colframe=orange!80, title=#1, breakable}
\newtcolorbox{infobox}[1][]{colback=blue!5, colframe=blue!60, title=#1, breakable}
\newtcolorbox{mistakebox}[1][]{colback=red!5, colframe=red!60, title=#1, breakable}
\newtcolorbox{learnbox}[1][]{colback=green!5, colframe=green!60, title=#1, breakable}

\pagestyle{fancy}
\fancyhf{}
\lhead{Direct Methods \& Applications}
\rhead{Unit 1 — Matrix Algebra}
\cfoot{\thepage}

\title{\textbf{Direct Methods: Cramer's Rule, Matrix Inversion \& Engineering Applications} \\ \large Unit 1 — Matrix Algebra and Linear Systems}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: Robot arm inverse kinematics → Jacobian^{-1} · velocity = joint rates (matrix inversion in real time). Electrical mesh analysis → Cramer's rule for symbolic closed-form current expressions. Chemical process material balances → matrix inversion for steady-state concentrations. These are the tools engineers reach for first before scaling to larger numerical solvers.

### Section 2: Theory vs Real-World Impact
- `booktabs` table covering all 3 sub-topics + 2 supporting methods (Gauss, GS) for comparison.
- `learnbox`: "Choose your method based on system size, structure, and whether A is reused — be pragmatic."

### Section 3: Definitions (3 Subsections)
- `\subsection{Cramer's Rule}`
- `\subsection{Matrix Inversion Method}`
- `\subsection{Applications to Engineering Systems}`
Each: conversational intuition → `infobox` with full formal content from Section 0.

### Section 4: Visual Artifacts (MANDATORY)
- **Visual 1 (TikZ):** Cramer's rule column-replacement diagram — show 3×3 matrix A; then A1 (col 1 replaced, highlighted), A2 (col 2 replaced), A3 (col 3 replaced) — label which column is b in each.
- **Visual 2 (TikZ):** Matrix inversion pipeline flowchart — A → cofactor matrix C → transpose → adj(A) → ÷det(A) → A^{-1} → ×b → x. Boxes with arrows.
- **Visual 3 (pgfplots):** Horizontal grouped bar chart — computational operations for Cramer's, Matrix Inversion, Gauss Elimination, Gauss-Jordan for n=2,3,4 — `ybar` style with legend.
- **Visual 4 (TikZ):** 3-mesh circuit diagram — three loops with resistors and voltage sources labeled; mesh current arrows I1, I2, I3 shown.

### Section 5: Step-by-Step Algorithmic Workflows
1. **Cramer's Rule Algorithm** — check det(A)≠0 → compute det(A) → for each i: replace col i with b → compute det(A_i) → x_i = det(A_i)/det(A).
2. **Matrix Inversion Algorithm** — check det(A)≠0 → compute all n² cofactors → build cofactor matrix → transpose → divide by det → x = A^{-1}b → verify.
3. **Engineering Modelling Algorithm** — identify unknowns → write governing equations → form Ax=b → select method using decision table → solve → interpret physically.

### Section 6: Fully Worked Examples (5 — covering all sub-topics with required depth)

**Example 1 — Cramer's Rule (2×2, Basic):**
Solve 3x+2y=7, x−y=1. Show det(A), form A1 and A2 with column replacement shown explicitly, compute each determinant, compute x and y, verify.
`learnbox`: "For 2×2 systems, Cramer's rule is the fastest hand-calculation method."

**Example 2 — Cramer's Rule (3×3, Full):**
Solve a 3×3 system — compute det(A) by cofactor expansion, form A1,A2,A3 showing each column replacement, compute all 3 determinants, divide, verify. Every arithmetic step shown.
`learnbox`: "For 3×3 systems, Cramer's rule requires 4 full determinant evaluations — check det(A)≠0 first."

**Example 3 — Matrix Inversion (3×3):**
Solve 2x+y+z=5, 4x−6y=−2, −2x+7y+2z=9 via matrix inversion. Compute all 9 cofactors individually (each as 2×2 determinant shown fully), build cofactor matrix, transpose to adj(A), divide by det(A), multiply A^{-1}·b, verify A·x=b.
`learnbox`: "Computing A^{-1} costs more upfront but pays off when solving for multiple b vectors."

**Example 4 — Engineering Application (3-Mesh Circuit, Cramer's Rule):**
KVL on 3 meshes: 5I1−2I2=10, −2I1+6I2−I3=0, −I2+4I3=8. Solve for I1,I2,I3 using Cramer's rule. Compute power at source P=I·V. Interpret current directions.
`learnbox`: "Cramer's rule gives mesh currents as exact fractions — ideal for symbolic circuit analysis."

**Example 5 — Engineering Application (Material Balance, Matrix Inversion):**
Three reactors in series: 3C1−C2=10, −C1+4C2−C3=5, −C2+3C3=8 (concentrations in mol/L). Solve using matrix inversion. Interpret each concentration physically and verify units.
`learnbox`: "Matrix inversion elegantly handles any number of coupled balance equations — the foundation of process simulation."

### Section 7: Decision Framework Table (MANDATORY)
Full `booktabs` table: Method | Formula | Prerequisite | Time Complexity | Memory | Best Use Case — 5 methods: Cramer's, Matrix Inversion, Gauss Elimination, Gauss-Jordan, Gauss-Seidel.

### Section 8: Common Student Mistakes
`mistakebox` — one per sub-topic plus extras:
- Wrong column replaced in Cramer's (row instead of column)
- x = b·A^{-1} instead of x = A^{-1}·b (non-commutativity)
- Not transposing cofactor matrix to get adj(A)
- Using Cramer's for n>3 (computationally infeasible)
- Not verifying A·x=b after computation

### Section 9: Assessment Suite
**Viva-Voce (min 9 — 3 per sub-topic):**
1–3: Cramer's — state rule, column replacement rule, when it fails.
4–6: Matrix inversion — adjugate definition, left multiply rule, advantage for multiple b.
7–9: Applications — modelling steps, decision framework, how to verify solution physically.

**Descriptive Problems (5 — matching 5 worked examples). MCQs (min 6 — 2 per sub-topic).**

### Section 10: Quick Recap
`learnbox` (9 bullets):
- Cramer's: x_i = det(A_i)/det(A); replace COLUMN i (not row) with b
- Cramer's requires det(A)≠0; O(n·n!) — use only for n≤3
- Matrix inversion: x = A^{-1}b; A^{-1} = adj(A)/det(A)
- adj(A) = TRANSPOSE of cofactor matrix
- ALWAYS left-multiply: x = A^{-1}·b, NOT b·A^{-1}
- (AB)^{-1} = B^{-1}A^{-1}; (A^T)^{-1} = (A^{-1})^T
- Matrix inversion O(n³) — efficient for repeated solves with same A
- Engineering modelling: unknowns → equations → Ax=b → method selection → interpret
- Always verify: compute A·x and confirm = b

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] Exactly 3 `\subsection{}` entries in Section 3.
- [ ] Sub-Topic 3 contains exactly 2 engineering application examples (electrical + chemical).
- [ ] Decision framework table covers all 5 methods.
- [ ] All 9 cofactors in Example 3 computed individually — no skipping.
- [ ] Column replacement (not row) explicitly labeled in all Cramer's examples.
- [ ] Verification (A·x = b) shown in all 5 worked examples.
- [ ] TikZ circuit diagram includes mesh current arrows and component labels.
- [ ] pgfplots bar chart has valid axis, legend, and numeric coordinates.
- [ ] All tcolorboxes closed; `\begin{document}...\end{document}` wraps everything.
