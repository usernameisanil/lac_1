# Generated Prompt — Topic: Iterative Methods (Jacobi & Gauss-Seidel)

**Unit:** Unit 1 — Matrix Algebra and Linear Systems
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)
**Target Audience:** B.Tech Engineering Students

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Iterative Methods — Jacobi Method and Gauss-Seidel Method"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers **2 atomic sub-topics** plus 2 essential supporting concepts. Each MUST appear as a separate named `\subsection{}` with its own `infobox`, dedicated worked examples, and assessment questions.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|---|---|
| 1 | **Jacobi Method** | `infobox`: full derivation of iteration formula x_i^{(k+1)} = (1/a_{ii})[b_i − Σ_{j≠i} a_{ij}x_j^{(k)}]; matrix form x^{(k+1)} = D^{-1}(b−(L+U)x^{(k)}); all values at iteration k used simultaneously (parallel update). Convergence condition: diagonal dominance |a_{ii}| > Σ_{j≠i}|a_{ij}|. Stopping criterion: max_i|x_i^{(k+1)}−x_i^{(k)}| < ε. Worked Example: 3×3 diagonally dominant system — perform 4 complete iterations from x^{(0)}=(0,0,0), show ALL arithmetic at every iteration in a tabular format, compare final iterate with exact solution. |
| 2 | **Gauss-Seidel Method** | `infobox`: full derivation of formula x_i^{(k+1)} = (1/a_{ii})[b_i − Σ_{j<i}a_{ij}x_j^{(k+1)} − Σ_{j>i}a_{ij}x_j^{(k)}]; matrix form x^{(k+1)} = (D+L)^{-1}(b−Ux^{(k)}); key distinction: uses updated values immediately (sequential update). Convergence condition: same diagonal dominance; converges faster than Jacobi (typically ≈2× fewer iterations). Worked Example: SAME 3×3 system as Jacobi example — perform 4 iterations — create side-by-side comparison table: Iteration | Jacobi x1,x2,x3 | GS x1,x2,x3 | Exact — demonstrate Gauss-Seidel convergence advantage explicitly. |
| S1 | **Diagonal Dominance (Supporting Concept)** | `infobox`: define strictly diagonally dominant matrix; row-wise condition |a_{ii}| > Σ_{j≠i}|a_{ij}| for ALL rows; theorem: strictly diagonally dominant → both Jacobi and Gauss-Seidel converge. Worked Example: test a given 3×3 matrix for diagonal dominance — check each row, show arithmetic, conclude convergence. If not dominant, show how to rearrange equations to achieve dominance. |
| S2 | **Convergence Analysis & Matrix Splitting** | `infobox`: define spectral radius ρ(B) for iteration matrix B; convergence iff ρ(B)<1; Jacobi iteration matrix B_J = D^{-1}(L+U); Gauss-Seidel iteration matrix B_GS = (D+L)^{-1}U. Error reduction per iteration proportional to ρ(B). Worked Example: compute spectral radius for a 2×2 system for both methods — confirm ρ<1 for convergence. |

**ENFORCEMENT RULE:** 4 named `\subsection{}` entries required. Iteration tables mandatory — formatted as `tabular` with columns: Iteration k | x1^{(k)} | x2^{(k)} | x3^{(k)} | Max Error. Side-by-side Jacobi vs GS comparison table required.

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
\lhead{Iterative Methods}
\rhead{Unit 1 — Matrix Algebra}
\cfoot{\thepage}

\title{\textbf{Iterative Methods: Jacobi Method and Gauss-Seidel Method} \\ \large Unit 1 — Matrix Algebra and Linear Systems}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook
- `curiositybox`: IEEE 118-bus power system — load flow analysis via Gauss-Seidel; flat start; convergence to operating voltages. Also: heat conduction FD solvers, Google PageRank.

### Section 2: Theory vs Real-World Impact
- `booktabs` table: Jacobi vs GS vs Direct methods — convergence, parallelism, memory, application.
- `learnbox`: "Iterative methods are the engine of large-scale engineering simulation — master them."

### Section 3: Definitions (4 Subsections)
- `\subsection{Diagonal Dominance — Convergence Precondition}`
- `\subsection{Jacobi Iteration Method}`
- `\subsection{Gauss-Seidel Iteration Method}`
- `\subsection{Convergence Analysis and Matrix Splitting}`
Each: intuition → `infobox` with full formula derivation and properties from Section 0.

### Section 4: Visual Artifacts (MANDATORY)
- **Visual 1 (pgfplots):** Convergence plot — x-axis: iteration number (0–10); y-axis: value of x1; plot Jacobi curve and GS curve with different colors; horizontal dashed line at exact solution; legend; grid.
- **Visual 2 (TikZ):** Update dependency diagram — Jacobi: all arrows from x^{(k)} (old); GS: x1 updated from old x2,x3; x2 updated from NEW x1 and old x3; x3 from NEW x1,x2.
- **Visual 3 (TikZ):** Diagonal dominance illustration — 3×3 matrix, circle diagonal, mini bar chart per row: |a_{ii}| vs Σ|a_{ij}|.
- **Visual 4 (pgfplots):** Error convergence plot — log scale y-axis showing error ||x^{(k)}−x*|| vs iteration — Jacobi vs GS.

### Section 5: Step-by-Step Algorithmic Workflows
1. **Pre-Check Algorithm** — test diagonal dominance for all rows; rearrange if needed.
2. **Jacobi Algorithm** — derive iteration formulas → initialize → iterate → check convergence.
3. **Gauss-Seidel Algorithm** — same structure but with sequential update rule clearly shown.
4. **Stopping Criterion** — max absolute change; relative error; residual norm.

### Section 6: Fully Worked Examples (4)

**Example 1 — Diagonal Dominance Check:**
Test 4x1+x2−x3=5, 2x1+7x2+x3=19, x1−3x2+12x3=22 for diagonal dominance — row by row with arithmetic.
`learnbox`: "Always rearrange to achieve diagonal dominance before applying iterative methods."

**Example 2 — Jacobi Method (4 Iterations):**
Solve the above system. Derive all 3 Jacobi formulas explicitly. Perform 4 iterations from (0,0,0). Present in full iteration table. Compare with exact solution.
`learnbox`: "Jacobi uses ONLY old values — compute all three updates before using any of them."

**Example 3 — Gauss-Seidel (4 Iterations + Comparison):**
Solve same system with Gauss-Seidel. Show sequential update within each iteration. Present side-by-side comparison table with Jacobi. Demonstrate faster convergence.
`learnbox`: "Gauss-Seidel uses updated values immediately — converges in roughly half the iterations of Jacobi."

**Example 4 — Applied (Heat Conduction):**
3-node 1D heat conduction: 2T1−T2=50, −T1+2T2−T3=0, −T2+2T3=30. Apply Gauss-Seidel until max change < 0.01°C. Interpret temperatures physically.
`learnbox`: "Iterative methods naturally suit FD/FEA problems where the matrix is large, sparse, and diagonally dominant."

### Section 7: Tabular Reference
Full comparison table: Feature | Jacobi | Gauss-Seidel — covering update rule, convergence speed, memory, parallelism, application.
Iteration summary table format template for student use.

### Section 8: Common Student Mistakes
`mistakebox` — 5 rows:
- Using updated values in Jacobi (mixing with GS)
- Not checking diagonal dominance before iterating
- Using only one variable for convergence check (should be max over all)
- Not rearranging equations to dominant form
- Stopping at wrong iteration (too early or too late)

### Section 9: Assessment Suite
**Viva-Voce (min 8 — 2 per sub-topic).**
**Descriptive Problems (4). MCQs (min 6 — at least 2 per sub-topic, 4 options, bold correct).**

### Section 10: Quick Recap
`learnbox` (8 bullets):
- Diagonal dominance: |a_{ii}| > Σ_{j≠i}|a_{ij}| — sufficient for convergence
- Jacobi: x_i^{(k+1)} uses ONLY x^{(k)} — all old values
- Gauss-Seidel: x_i^{(k+1)} uses x_j^{(k+1)} for j<i — updated values
- GS converges ≈2× faster than Jacobi
- Convergence check: max_i|x_i^{(k+1)}−x_i^{(k)}| < ε
- Initial guess: x^{(0)} = zero vector
- Matrix splitting: Jacobi uses D^{-1}; GS uses (D+L)^{-1}
- Best for: large, sparse, diagonally dominant systems

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] Exactly 4 `\subsection{}` entries in Section 3.
- [ ] Iteration table formatted as `tabular` with booktabs rules — columns: k | x1 | x2 | x3 | Max Error.
- [ ] Side-by-side Jacobi vs GS comparison table present.
- [ ] Jacobi derivation and GS derivation shown from scratch in separate `infobox` environments.
- [ ] Diagonal dominance check arithmetic shown row by row for all examples.
- [ ] pgfplots convergence plot: named coordinates, axis labels, legend, grid.
- [ ] All tcolorboxes closed; `\begin{document}...\end{document}` wraps everything.
