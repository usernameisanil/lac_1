# LAC Lecture Note Generation -- Execution Meta-Prompt (Self-Driving)

**Repo:** `usernameisanil/lac_1`
**Branch:** `main`
**Directory:** `prompts_and_responses/`

---

## PURPOSE

This is the **one and only prompt** you need to run for every topic.
You do NOT copy-paste any topic file. The LLM reads it from GitHub directly.

### How to trigger a run

Start a new session with an LLM that has GitHub MCP access, then send:

```
Read EXECUTION_META_PROMPT.md from the repo usernameisanil/lac_1,
follow it exactly, and process this topic file:
prompts_and_responses/unit1_topic1_matrix_fundamentals_prompt.md
```

Change the last filename for each of the 23 topics. That is all.

---

## ALL 23 TOPIC FILES (for reference)

### Unit 1 -- Matrix Algebra and Linear Systems
1. `prompts_and_responses/unit1_topic1_matrix_fundamentals_prompt.md`
2. `prompts_and_responses/unit1_topic2_determinants_and_rank_prompt.md`
3. `prompts_and_responses/unit1_topic3_system_of_linear_equations_prompt.md`
4. `prompts_and_responses/unit1_topic4_iterative_methods_prompt.md`
5. `prompts_and_responses/unit1_topic5_direct_methods_applications_prompt.md`

### Unit 2 -- Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms
6. `prompts_and_responses/unit2_topic1_eigenvalues_eigenvectors_prompt.md`
7. `prompts_and_responses/unit2_topic2_characteristic_equation_prompt.md`
8. `prompts_and_responses/unit2_topic3_cayley_hamilton_theorem_prompt.md`
9. `prompts_and_responses/unit2_topic4_diagonalization_similarity_transformation_prompt.md`
10. `prompts_and_responses/unit2_topic5_powers_inverse_cayley_hamilton_prompt.md`
11. `prompts_and_responses/unit2_topic6_quadratic_forms_canonical_form_prompt.md`
12. `prompts_and_responses/unit2_topic7_rank_index_signature_definite_forms_prompt.md`
13. `prompts_and_responses/unit2_topic8_special_matrices_prompt.md`

### Unit 3 -- Single Variable Calculus and Series Expansions
14. `prompts_and_responses/unit3_topic1_mean_value_theorems_prompt.md`
15. `prompts_and_responses/unit3_topic2_series_expansions_prompt.md`
16. `prompts_and_responses/unit3_topic3_curvature_concepts_prompt.md`

### Unit 4 -- Multivariable Differentiation and Optimization
17. `prompts_and_responses/unit4_topic1_differential_calculus_several_variables_prompt.md`
18. `prompts_and_responses/unit4_topic2_differential_geometry_fields_prompt.md`
19. `prompts_and_responses/unit4_topic3_jacobians_functional_dependence_taylor_prompt.md`
20. `prompts_and_responses/unit4_topic4_optimization_maxima_minima_lagrange_prompt.md`

### Unit 5 -- Multiple Integrals and Coordinate Transformations
21. `prompts_and_responses/unit5_topic1_multiple_integrals_prompt.md`
22. `prompts_and_responses/unit5_topic2_coordinate_systems_prompt.md`
23. `prompts_and_responses/unit5_topic3_applications_multiple_integration_prompt.md`

---

---

# INSTRUCTIONS FOR THE LLM

You are reading this file because the user asked you to process a specific topic.
Follow every step below in strict sequence. Do not skip any step.

---

## STEP 0: AUTHENTICATE AND READ THE TOPIC FILE

Using your GitHub MCP tool:

1. Call `get_file_contents` with:
   - `owner`: `usernameisanil`
   - `repo`: `lac_1`
   - `path`: *(the topic file path the user specified)*
2. Read the returned content **completely and carefully** before writing a single line of LaTeX.
3. Extract and note these values from the prompt file:

| What to extract | Where to find it |
|----------------|------------------|
| Topic name | First heading or `**Unit:**` line |
| Unit number | `**Unit:**` line |
| Unit title | `**Unit:**` line |
| N = number of atomic sub-topics | Count rows in the Section 0 table |
| Exact `\lhead{}` value | Section 1 preamble block |
| Exact `\rhead{}` value | Section 1 preamble block |
| Exact `\title{}` value | Section 1 preamble block |
| Output filename | Same as prompt filename, replace `_prompt.md` with `.tex` |

Example:
- Input: `unit2_topic3_cayley_hamilton_theorem_prompt.md`
- Output: `unit2_topic3_cayley_hamilton_theorem.tex`

**Do not proceed to Step 1 until you have read and understood the entire topic file.**

---

## STEP 1: GENERATE THE COMPLETE LaTeX FILE

Generate the **complete, fully written, self-contained LaTeX source file**
following every instruction in the topic file with zero omissions.

### 1a. Structure Rules (Non-Negotiable)

1. **Start with the exact preamble** from Section 1 of the topic file -- copy verbatim.
2. After `\begin{document}`, write `\maketitle` then `\tableofcontents` then `\newpage`.
3. **Generate ALL 10 sections** in this exact order:
   - Section 1: Real-World Engineering Hook (curiositybox)
   - Section 2: Why This Topic Exists (booktabs table + learnbox)
   - Section 3: Intuition + Definitions -- **exactly N subsections**, one per atomic sub-topic
   - Section 4: Visual Artifacts (TikZ / pgfplots diagrams)
   - Section 5: Step-by-Step Algorithmic Workflow
   - Section 6: Fully Worked Numerical Examples
   - Section 7: Tabular Reference / Comparison
   - Section 8: Common Mistakes (mistakebox tabular)
   - Section 9: Assessment Suite (Viva + Descriptive + MCQ)
   - Section 10: Quick Recap and Formula Sheet (learnbox)
4. **Section 3 must contain exactly N `\subsection{}` entries** -- one per row in the Section 0 table.
   Never merge two sub-topics. Never add extra sub-topics not in the table.
5. Each subsection must follow this internal order:
   - 2--3 lines of conversational intuition (plain text)
   - `infobox` with all formal definitions, theorems, formulas, properties
   - At least one dedicated worked example with full step-by-step arithmetic

### 1b. Content Rules (Non-Negotiable)

6. Every **infobox** must contain the exact definitions and formulas listed in the
   Section 0 table for that sub-topic. No generic placeholders.
7. Every **worked example** must use distinct numerical values not reused across examples.
   Show every arithmetic step. Never write:
   - "it can be shown"
   - "the reader can verify"
   - "similarly"
   - "(details omitted)"
   - "continuing in the same way"
8. **Section 2 table**: one row per atomic sub-topic, genuine engineering consequence per row.
9. **Section 7 table**: revision-useful, topic-specific -- not a copy of Section 3.
10. **Section 8 mistakebox tabular**: minimum one row per atomic sub-topic (>= N rows).
11. **Section 9 assessment** must meet ALL minimums from the topic file enforcement rules.
    Typical minimums: viva >= 6, descriptive >= 4, MCQ >= 5.
    MCQs: 4 options each, bold correct answer with `\textbf{}`, one-line explanation.
12. **Section 10 learnbox**: exactly the bullet count specified in the topic file (usually 6--8).
    Each bullet must be topic-specific -- not generic math advice.
13. **Engineering hook (Section 1)**: must describe a specific realistic failure scenario
    by name (e.g., "finite element analysis of a truss", "GPS satellite orbit correction").
    Never write "mathematics is important for engineers."

### 1c. LaTeX Correctness Rules (Non-Negotiable)

14. **pmatrix for all matrices:**
    `\begin{pmatrix} a & b \\\ c & d \end{pmatrix}`
15. **Vectors:** use `\mathbf{v}` consistently throughout the entire file.
    Never switch between `\mathbf{}` and `\vec{}` in the same file.
16. **tcolorbox syntax:** `\newtcolorbox{name}[1]{..., title=#1, breakable}`
    NOT `[1][]` -- the title argument is positional, not keyword.
17. **Every box opened must be closed:**
    `\begin{infobox}{Title}` ... `\end{infobox}`
    `\begin{curiositybox}{Title}` ... `\end{curiositybox}`
    `\begin{learnbox}{Title}` ... `\end{learnbox}`
    `\begin{mistakebox}{Title}` ... `\end{mistakebox}`
18. **No bare special characters in text mode:**
    - Use `\%` not `%`
    - Use `\$` not `$` in text
    - Use `\&` not `&` outside tabular
    - Use `\_` not `_` outside math
19. **No Unicode in LaTeX source:**
    - `---` not `--` not the Unicode em-dash character
    - `\geq` not `>=` or `>=` Unicode
    - `\leq`, `\to`, `\ldots`, `\cdot` not their Unicode equivalents
    - `\times` not the Unicode times character
20. **TikZ and pgfplots visuals:**
    - Fully self-contained (no `\input{}`, no `\includegraphics{}`)
    - Every `\begin{tikzpicture}` closed with `\end{tikzpicture}`
    - Every `\begin{axis}` closed with `\end{axis}` inside tikzpicture
    - 3D surf plots: use `samples=40` maximum
    - Every axis: `xlabel`, `ylabel` at minimum
21. **Document boundaries:**
    - First line of file: `\documentclass[12pt,a4paper]{article}`
    - Last line of file: `\end{document}`
    - Nothing before `\documentclass`, nothing after `\end{document}`
22. **Never truncate:**
    Do not end any section with:
    - "(add more questions as needed)"
    - "(remaining sub-topics follow the same pattern)"
    - "..."
    - "etc."
    Every question, every row, every bullet must be fully written out.

---

## STEP 2: PRE-PUSH SELF-CHECK

Before pushing, verify every item in this checklist.
If any item fails, fix it before proceeding.

```
PRE-PUSH CHECKLIST
------------------
[ ] Preamble copied verbatim from topic file (lhead, rhead, title, packages)
[ ] \newtcolorbox uses [1] not [1][] -- verified
[ ] \begin{document} present immediately after preamble
[ ] \maketitle and \tableofcontents present after \begin{document}
[ ] Section 3 contains exactly N \subsection{} entries (N = from Step 0)
[ ] Every \begin{infobox}, \begin{learnbox}, \begin{curiositybox}, \begin{mistakebox} is closed
[ ] Every \begin{tikzpicture} is closed with \end{tikzpicture}
[ ] Every \begin{axis} is closed with \end{axis}
[ ] No bare _ or ^ outside math mode
[ ] No bare & outside tabular/align
[ ] No bare % in text (use \% or write percent)
[ ] No Unicode characters in LaTeX source
[ ] All N sub-topics have: infobox + worked example + assessment item
[ ] Section 8 mistakebox has >= N rows
[ ] Section 9 meets all count minimums from topic file
[ ] Section 10 learnbox has the exact bullet count specified
[ ] No section ends with placeholder text or ellipsis
[ ] \end{document} is the very last line
```

---

## STEP 3: PUSH TO GITHUB

Using your GitHub MCP tool, call `create_or_update_file` with:

| Parameter | Value |
|-----------|-------|
| `owner` | `usernameisanil` |
| `repo` | `lac_1` |
| `branch` | `main` |
| `path` | `prompts_and_responses/<output_filename>.tex` |
| `message` | `response: <output_filename>.tex -- LaTeX lecture note for <Topic Name>, Unit <N>` |
| `content` | The complete .tex file as a string |

If the file already exists in the repo (a previous attempt),
you MUST fetch its current SHA first using `get_file_contents`
and pass it as the `sha` parameter. Omitting SHA on an existing file will cause a 422 error.

**Do NOT push if any checklist item above is unchecked.**
Fix the issue, recheck, then push.

---

## STEP 4: REPORT COMPLETION

After a successful push, output this exact report:

```
===========================================
LAC LECTURE NOTE -- GENERATION COMPLETE
===========================================
File pushed : prompts_and_responses/<output_filename>.tex
Commit SHA  : <sha from push response>
Commit URL  : <html_url from push response>
Topic       : <Topic Name>
Unit        : Unit <N> -- <Unit Title>
-------------------------------------------
Sub-topics covered (<N> total):
  1. <sub-topic 1 name>
  2. <sub-topic 2 name>
  ... (all N)
-------------------------------------------
Sections generated:
  1  Real-World Hook        [curiositybox]
  2  Why This Topic         [booktabs table + learnbox]
  3  Definitions            [N subsections x infobox]
  4  Visuals                [TikZ/pgfplots count: X]
  5  Algorithmic Workflow   [boxed steps]
  6  Worked Examples        [count: X]
  7  Reference Table        [booktabs]
  8  Common Mistakes        [mistakebox, X rows]
  9  Assessment             [viva: X | descriptive: X | MCQ: X]
  10 Formula Sheet          [learnbox, X bullets]
-------------------------------------------
All checklist items: PASSED
===========================================
```

---

## KNOWN FAILURE MODES -- PREVENT THESE

| # | Failure | Prevention |
|---|---------|------------|
| 1 | `\newtcolorbox{infobox}[1][]` | Use `[1]` only -- not `[1][]` |
| 2 | Unclosed tcolorbox | Write `\end{infobox}` immediately after planning each box |
| 3 | Unicode em-dash in .tex | Type `---` not the Unicode character |
| 4 | 3D plot compilation timeout | `samples=40` maximum for surf plots |
| 5 | Wrong subsection count | Re-count rows in Section 0 table before writing Section 3 |
| 6 | Truncated assessment | Every question written in full -- no ellipsis, no "add more" |
| 7 | Missing `\maketitle` | Always: `\begin{document}` then `\maketitle` then `\tableofcontents` |
| 8 | SHA missing on update | Always fetch existing file SHA before pushing an update |
| 9 | Bare `%` in text | Write `\%` or spell out "percent" |
| 10 | Mixed `\mathbf` and `\vec` | Pick one at start, use it everywhere |
