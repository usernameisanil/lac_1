# Generated Prompt — Topic: System of Linear Equations

**Unit:** Unit 1 — Matrix Algebra and Linear Systems
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)
**Target Audience:** B.Tech Engineering Students

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"System of Linear Equations — Consistency, Gauss Elimination and Gauss-Jordan Method"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers **3 atomic sub-topics**. Each MUST appear as a separate named `\subsection{}` with its own `infobox`, at least one dedicated worked example, and at least one viva/MCQ question.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|---|---|
| 1 | **Consistency Conditions (Rouché–Capelli Theorem)** | `infobox`: matrix form Ax=b; augmented matrix [A\|b]; **Rouché–Capelli Theorem** (state formally by name, with proof sketch): rank[A]=rank[A\|b] → consistent; rank[A]=rank[A\|b]=n → unique solution; rank[A]=rank[A\|b]=r<n → infinite solutions with (n−r) free variables; rank[A]≠rank[A\|b] → inconsistent. The theorem MUST be displayed in a named `infobox` titled "Rouché–Capelli Theorem". Include geometric interpretation: 2 equations = 2 lines → unique (intersect), infinite (same line), none (parallel). Worked Example: for each of 3 systems (unique, infinite, inconsistent), form augmented matrix, compute both ranks, apply theorem by name, state nature of solution — all three cases in one example. |
| 2 | **Gauss Elimination Method** | `infobox`: forward elimination to upper triangular form + back substitution; multiplier formula m_{ik}=a_{ik}/a_{kk}; row operation Ri→Ri−m_{ik}Rk; partial pivoting note (swap rows if pivot is zero). Full step-by-step algorithm boxed. Worked Example: solve a 3×3 system with unique solution — write augmented matrix, perform ALL elimination steps with labeled operations, back-substitute from last equation upward, write final solution, VERIFY by substituting into all 3 original equations. |
| 3 | **Gauss-Jordan Method** | `infobox`: extend Gauss elimination upward — eliminate both ABOVE and BELOW each pivot to reach RREF; solution read directly from last column with no back-substitution needed. Difference from Gauss: Gauss stops at upper triangular; Gauss-Jordan continues to RREF. Worked Example: solve a 3×3 system using Gauss-Jordan — show all upward elimination steps labeled, display final RREF, read off solution directly. Then solve a 3×4 system with infinite solutions — express general solution in parametric vector form. |

**ENFORCEMENT RULE:** 3 named `\subsection{}` entries required. Sub-Topic 1 subsection MUST be titled `\subsection{Consistency Conditions and the Rouché–Capelli Theorem}` and contain a dedicated `infobox` with the theorem stated formally by that exact name. Geometric visualization (3 cases) mandatory for Sub-Topic 1. Assessment must contain at least 2 viva questions and 2 MCQs per sub-topic. At least one viva question must ask students to state the Rouché–Capelli Theorem by name.

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
\lhead{System of Linear Equations}
\rhead{Unit 1 — LAC}
\cfoot{\thepage}

\title{\textbf{System of Linear Equations: Consistency, Gauss Elimination \& Gauss-Jordan Method} \\ \large Unit 1 — Matrix Algebra and Linear Systems}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

### Section 1: Real-World Engineering Hook (Curiosity Box)
- `curiositybox` titled **"Why Should an Engineer Care?"**
- Scenario: Every engineering simulation (FEA in ANSYS, traffic optimization, power grid load balancing) reduces to Ax=b. A 100-member truss → 100×100 linear system. Gauss elimination is the backbone of all numerical solvers. Consistency check tells you whether a valid design solution exists at all before any computation.

### Section 2: Why This Topic Exists — Theory vs Real-World Impact
- `booktabs` table: 5 rows covering consistent (unique), consistent (infinite), inconsistent, Gauss elimination, Gauss-Jordan.
- `learnbox`: "Knowing whether a solution exists — and how many — is the first question every engineer must answer."

### Section 3: Intuition First & Definitions (3 Subsections)
- `\subsection{Consistency Conditions and the Rouché–Capelli Theorem}`
- `\subsection{Gauss Elimination Method}`
- `\subsection{Gauss-Jordan Method}`
Each: conversational intuition → dedicated `infobox` with formal theorem/algorithm from Section 0. Sub-Topic 1 MUST have a distinct `infobox` titled **"Rouché–Capelli Theorem"** containing the formal statement.

### Section 4: Visual Artifacts (MANDATORY)
- **Visual 1 (pgfplots):** Three side-by-side 2D plots — Case 1: intersecting lines (unique solution, mark point); Case 2: parallel lines (no solution, label "Inconsistent"); Case 3: identical lines (infinite solutions, label "Infinite").
- **Visual 2 (TikZ):** Augmented matrix transformation stages — [A|b] original → after forward elimination → upper triangular → after back-sub → solution vector. Color-code pivot entries.
- **Visual 3 (TikZ):** Decision flowchart — Ax=b → compute rank[A] and rank[A|b] → compare → branch to three outcome boxes labelled with Rouché–Capelli cases.
- **Visual 4 (TikZ):** Gauss vs Gauss-Jordan comparison — show same matrix being reduced: Gauss stops at upper triangular, Gauss-Jordan continues to RREF.

### Section 5: Step-by-Step Algorithmic Workflows
1. **Consistency Check Algorithm (Rouché–Capelli)** — compute rank[A], rank[A|b], apply theorem by name, determine nature.
2. **Gauss Elimination Algorithm** — forward sweep with partial pivoting note, back-substitution from last row upward.
3. **Gauss-Jordan Algorithm** — forward AND backward sweep, RREF, direct solution read-off.
4. **General Solution for Infinite Cases** — identify free variables, parametrize, write vector form.

### Section 6: Fully Worked Examples (4 — covering all sub-topics with extra depth)

**Example 1 — All Three Consistency Cases:**
Present three 3×3 systems. For each: form augmented matrix, row-reduce, compute rank[A] and rank[A|b], apply the Rouché–Capelli theorem by name, state nature of solution.
`learnbox`: "Always apply the Rouché–Capelli theorem first — saves time and avoids meaningless computation."

**Example 2 — Gauss Elimination (Unique Solution):**
Solve x+y+z=6, 2x−y+3z=14, 3x+2y−z=2. Write [A|b], perform R2→R2−2R1, R3→R3−3R1, then R3→R3−(8/3)R2. Back-substitute upward — show every arithmetic step. Verify all 3 original equations.
`learnbox`: "Back-substitution starts from the LAST equation and works upward."

**Example 3 — Gauss-Jordan (Unique Solution):**
Solve the same system using Gauss-Jordan. After upper triangular form, continue upward elimination. Display RREF. Read solution directly.
`learnbox`: "Gauss-Jordan gives solution directly from the last column — no back-substitution needed."

**Example 4 — Gauss-Jordan (Infinite Solutions + Engineering Application):**
Solve a 3×4 underdetermined system. Identify r free variables. Write general solution in parametric vector form: x = x_particular + t·x_homogeneous. Apply to a power network nodal analysis problem.
`learnbox`: "Infinite solutions mean free variables exist — always express the complete general solution in vector form."

### Section 7: Tabular Reference
`booktabs` table: Method | Reduction Target | Back-Sub Needed | Cost | Best For.
Second table: Rouché–Capelli theorem — all 3 cases with rank conditions, solution type, geometric meaning, engineering example.

### Section 8: Common Student Mistakes & Pitfalls
`mistakebox` — one per sub-topic plus extras:
- Not checking consistency (Rouché–Capelli) before solving
- Misidentifying inconsistency (zero row ≠ inconsistency; 0=nonzero is inconsistency)
- Arithmetic error in multiplier m_{ik} — write it explicitly before applying
- Back-substituting in wrong order (starting from x1 instead of last variable)
- Stopping at upper triangular and calling it RREF (Gauss vs Gauss-Jordan confusion)

### Section 9: Comprehensive Assessment Suite
**Viva-Voce (min 9 — 3 per sub-topic):**
1–3: State the Rouché–Capelli theorem by name and in full; geometric meaning of inconsistency; free variable count formula (n−r).
4–6: Gauss elimination steps; partial pivoting purpose; verification method.
7–9: Gauss-Jordan vs Gauss difference; RREF definition; parametric vector form.

**Descriptive Problems (4). MCQs (min 6 — 2 per sub-topic).**

### Section 10: Quick Recap & Formula Sheet
`learnbox` (9 bullets):
- Rouché–Capelli Theorem: Ax=b consistent ⇔ rank[A]=rank[A|b]
- Unique solution: rank[A]=rank[A|b]=n
- Infinite solutions: rank[A]=rank[A|b]=r<n → (n−r) free variables
- Inconsistent: rank[A] ≠ rank[A|b]
- Gauss: forward elimination → upper triangular → back-substitute
- Gauss-Jordan: forward + backward elimination → RREF → direct read-off
- Row op notation: $R_i \leftarrow R_i - m_{ik}R_k$, $m_{ik}=a_{ik}/a_{kk}$
- General solution = particular + homogeneous (for infinite case)
- ALWAYS verify: substitute solution into ALL original equations

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS
- [ ] Exactly 3 `\subsection{}` entries in Section 3.
- [ ] Rouché–Capelli theorem stated formally in its own named `infobox` titled "Rouché–Capelli Theorem".
- [ ] Augmented matrix format: `\left[\begin{array}{ccc|c}...\end{array}\right]`.
- [ ] All 3 consistency cases demonstrated in Example 1 with explicit reference to Rouché–Capelli.
- [ ] Back-substitution in Example 2 shown starting from last equation upward.
- [ ] Verification (substituting back into ALL 3 original equations) shown in Example 2.
- [ ] Parametric vector form in Example 4 uses column vector notation.
- [ ] pgfplots 3-case visual has distinct colors, axis labels, intersection point marked.
- [ ] All tcolorboxes closed; document wrapped in `\begin{document}...\end{document}`.
