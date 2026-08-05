# Unit 2 — Prompts and Responses Index

**Unit:** Unit 2 — Eigenvalues, Eigenvectors, Diagonalization and Quadratic Forms  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Architecture:** Master Prompt with Sub-Topic Coverage Mandate (Section 0)  
**Last Refactored:** 2026-08-05  

---

## Overview

All 8 topic prompt files for Unit 2 now follow the **Master Prompt Architecture** with **Section 0: Sub-Topic Coverage Mandate**. Each prompt enforces:
- Exactly N named `\subsection{}` entries in Section 3 (one per atomic sub-topic)
- At least one `infobox`, one worked example, and one assessment item per sub-topic
- At least one viva-voce question and one MCQ per sub-topic in Section 9

---

## Topic Files

| # | File | Topic | Sub-Topics (N) |
|---|------|-------|----------------|
| 1 | [unit2_topic1_eigenvalues_eigenvectors_prompt.md](unit2_topic1_eigenvalues_eigenvectors_prompt.md) | Eigenvalues and Eigenvectors | 5 |
| 2 | [unit2_topic2_characteristic_equation_prompt.md](unit2_topic2_characteristic_equation_prompt.md) | Characteristic Equation | 5 |
| 3 | [unit2_topic3_cayley_hamilton_theorem_prompt.md](unit2_topic3_cayley_hamilton_theorem_prompt.md) | Cayley-Hamilton Theorem | 5 |
| 4 | [unit2_topic4_diagonalization_similarity_transformation_prompt.md](unit2_topic4_diagonalization_similarity_transformation_prompt.md) | Diagonalization and Similarity Transformation | 5 |
| 5 | [unit2_topic5_powers_inverse_cayley_hamilton_prompt.md](unit2_topic5_powers_inverse_cayley_hamilton_prompt.md) | Powers and Inverse via Cayley-Hamilton | 5 |
| 6 | [unit2_topic6_quadratic_forms_canonical_form_prompt.md](unit2_topic6_quadratic_forms_canonical_form_prompt.md) | Quadratic Forms and Canonical Form | 5 |
| 7 | [unit2_topic7_rank_index_signature_definite_forms_prompt.md](unit2_topic7_rank_index_signature_definite_forms_prompt.md) | Rank, Index, Signature, and Definite Forms | 5 |
| 8 | [unit2_topic8_special_matrices_prompt.md](unit2_topic8_special_matrices_prompt.md) | Special Matrices | 5 |

---

## How to Use

1. Open the relevant topic file.
2. Copy the entire prompt.
3. Paste into a **new chat conversation** with an AI assistant (Claude, GPT-4, etc.).
4. The AI will generate a complete, 100% compilable LaTeX lecture note covering all 5 atomic sub-topics for that topic.
5. Compile the resulting `.tex` file with `pdflatex` (run twice for cross-references).

---

## Sub-Topic Coverage Summary (Unit 2)

| Topic | Sub-Topic 1 | Sub-Topic 2 | Sub-Topic 3 | Sub-Topic 4 | Sub-Topic 5 |
|-------|------------|------------|------------|------------|------------|
| Eigenvalues & Eigenvectors | Definition & eigenspace | Characteristic equation | Row reduction for eigenvectors | Geometric vs algebraic multiplicity | Eigenvalues of special matrices |
| Characteristic Equation | Polynomial definition | Roots (eigenvalues) | Cofactor expansion | Shortcuts & special cases | Algebraic multiplicity |
| Cayley-Hamilton | Theorem statement | Verification | Finding inverse | Computing powers | Minimal polynomial |
| Diagonalization | Similarity transformation | Diagonalizability condition | Diagonalization procedure | Powers via diagonalization | Orthogonal diagonalization |
| Powers & Inverse | Recurrence formula | Finding $A^{-1}$ | Matrix polynomials | CH vs Diagonalization | Engineering applications |
| Quadratic Forms | Definition & matrix form | Orthogonal transformation | Lagrange's method | Nature (definite/indefinite) | Rank, index, signature |
| Rank/Index/Signature | Rank | Index | Signature | Sylvester's Law of Inertia | Definite forms & Sylvester's criterion |
| Special Matrices | Symmetric & skew-symmetric | Orthogonal | Hermitian & skew-Hermitian | Idempotent & nilpotent | Unitary & normal |
