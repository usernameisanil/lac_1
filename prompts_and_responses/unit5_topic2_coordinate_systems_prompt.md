# Generated Prompt — Topic: Coordinate Systems (Change of Variables, Polar, Cylindrical, Spherical)

**Unit:** Unit 5 — Multiple Integrals and Coordinate Transformations  
**Course:** Linear Algebra and Calculus (B.Tech 1st Year)  
**Target Audience:** B.Tech Engineering Students  

---

## PROMPT INSTRUCTIONS

You are an expert engineering mathematics professor writing a **complete, 100% compilable LaTeX (.tex) lecture note** on the topic **"Coordinate Systems — Change of Variables, Polar, Cylindrical, and Spherical Coordinates"**.

Write as an enthusiastic, patient teacher who builds deep intuition, connects abstract concepts to real-world engineering applications, and ensures students never feel overwhelmed by mathematical notation.

---

## 0. SUB-TOPIC COVERAGE MANDATE (STRICT ENFORCEMENT)

This prompt covers a set of **atomic sub-topics** from the syllabus for the group topic **"Coordinate Systems"**.

The generated LaTeX document MUST treat **EACH atomic sub-topic** as a **separate, named subsection** with:

- A dedicated `infobox` containing formal definitions/properties/algorithms for that sub-topic.
- At least **one fully worked numerical/symbolic example** explicitly targeting that sub-topic.
- At least **one assessment item** (viva question or MCQ) explicitly tied to that sub-topic.

No atomic sub-topic may be merged into another or only mentioned in passing.

| # | Atomic Sub-Topic | Mandatory Coverage Requirements |
|---|------------------|---------------------------------|
| 1 | Change of Variables (General Jacobian Transformation) | `infobox` must define the Jacobian determinant \(J = \partial(x,y)/\partial(u,v)\), state the change-of-variables formula \(\iint_R f(x,y)\,dA = \iint_S f(g,h)\,|J|\,du\,dv\), and note when \(J=0\) causes problems; provide one fully worked example transforming a double integral using a non-trivial substitution; include one viva question on the geometric meaning of \(|J|\) and one MCQ on computing the Jacobian. |
| 2 | Polar Coordinates | `infobox` must state \(x = r\cos\theta,\; y = r\sin\theta\), the Jacobian \(|J| = r\), and \(dA = r\,dr\,d\theta\); provide one worked example converting a double integral over a circular/annular region from Cartesian to polar; include one viva question on why \(r\) appears in \(dA\) and one MCQ on setting polar limits. |
| 3 | Cylindrical Coordinates | `infobox` must define \(x = r\cos\theta,\; y = r\sin\theta,\; z = z\) with Jacobian \(|J| = r\) and volume element \(dV = r\,dr\,d\theta\,dz\); provide one worked example evaluating a triple integral over a cylinder or cone using cylindrical coordinates; include one viva question distinguishing cylindrical from polar and one MCQ on setting up limits in cylindrical form. |
| 4 | Spherical Coordinates | `infobox` must define \(x = \rho\sin\phi\cos\theta,\; y = \rho\sin\phi\sin\theta,\; z = \rho\cos\phi\) with Jacobian \(|J| = \rho^2\sin\phi\) and volume element \(dV = \rho^2\sin\phi\,d\rho\,d\phi\,d\theta\); provide one worked example evaluating a triple integral over a sphere or hemisphere; include one viva question on the ranges of \(\rho, \phi, \theta\) and one MCQ on identifying the correct spherical Jacobian. |

**ENFORCEMENT RULES:**

1. Section 3 must contain **exactly 4 named `\subsection{}` entries**, one per row above.
2. The assessment section (Section 9) must contain **at least one viva-voce question and one MCQ per atomic sub-topic**.
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
\newtcolorbox{curiositybox}[1]{colback=yellow!10, colframe=orange!80, title=#1, breakable}
\newtcolorbox{infobox}[1]{colback=blue!5, colframe=blue!60, title=#1, breakable}
\newtcolorbox{mistakebox}[1]{colback=red!5, colframe=red!60, title=#1, breakable}
\newtcolorbox{learnbox}[1]{colback=green!5, colframe=green!60, title=#1, breakable}

% Header and Footer
\pagestyle{fancy}
\fancyhf{}
\lhead{Coordinate Systems}
\rhead{Unit 5 — LAC}
\cfoot{\thepage}

% Document Title Setup
\title{\textbf{Coordinate Systems: Change of Variables, Polar, Cylindrical \& Spherical Coordinates} \\ \large Unit 5: Multiple Integrals and Coordinate Transformations}
\author{Department of Mathematics}
\date{\today}
```

---

## 2. MANDATORY DOCUMENT SECTIONS & ARCHITECTURE

Generate a document containing ALL of the following sections in strict logical sequence.

### Section 1: Real-World Engineering Hook (Curiosity Box)

- Open with a `curiositybox` titled **"Why Should an Engineer Care?"**.
- Scenario: Computing the gravitational field of a uniform solid sphere (spherical coordinates), analyzing current distribution in a cylindrical conductor (cylindrical coordinates), or determining the pressure distribution over a circular turbine blade cross-section (polar coordinates). Show that switching to the wrong coordinate system makes limits impossible to write cleanly and inflates error risk.

### Section 2: Why This Topic Exists (Theory vs Real-World Impact)

- 2-column `booktabs` table with at least one row per atomic sub-topic:

  | Theoretical Concept | Engineering Application / Consequence of Misunderstanding |
  |---------------------|-----------------------------------------------------------|
  | General Jacobian (change of variables) | Finite element mesh mapping — wrong Jacobian → physically incorrect stiffness matrix entries |
  | Polar coordinates | Pressure/flux over circular/annular cross-sections — Cartesian limits unmanageable for disks |
  | Cylindrical coordinates | Heat conduction in cylindrical pipes — decouples radial and axial dependencies cleanly |
  | Spherical coordinates | Gravitational/electrostatic potential around spherical bodies — natural symmetry alignment |

- Conclude with a `learnbox` on the core objective.

### Section 3: Intuition First & Mathematical Definitions (Subsections per Sub-Topic)

Create exactly **4 subsections**:

1. `\subsection{Change of Variables and the Jacobian Determinant}`
2. `\subsection{Polar Coordinates}`
3. `\subsection{Cylindrical Coordinates}`
4. `\subsection{Spherical Coordinates}`

For each: 2–4 lines of conversational intuition (geometric interpretation), then a dedicated `infobox` with formal transformation equations, Jacobian, volume/area element, and key assumptions.

### Section 4: Visual Artifacts & Geometric Interpretation

- TikZ diagram illustrating polar coordinate grid (circles and radial lines) vs Cartesian grid.
- TikZ 3D diagram of cylindrical coordinates showing \(r, \theta, z\) axes and a cylindrical volume element.
- TikZ 3D diagram of spherical coordinates showing \(\rho, \phi, \theta\) and a spherical volume element \(\rho^2 \sin\phi\, d\rho\, d\phi\, d\theta\).
- pgfplots plot showing Jacobian \(|J| = r\) growing linearly with \(r\) (area-scaling intuition).
- All visuals self-contained, compilable with `pdflatex`.

### Section 5: Step-by-Step Algorithmic Solution / Workflow

Boxed workflow:
1. Identify symmetry of the region (circular → polar/cylindrical; spherical → spherical coords).
2. Write transformation equations and compute Jacobian determinant.
3. Express integrand in new variables.
4. Set up new limits for transformed region.
5. Evaluate the integral.
6. Decision table: which coordinate system to choose based on region shape.

### Section 6: Fully Worked Step-by-Step Numerical Examples

1. **Example 1 — Polar (Basic):** Evaluate \(\iint_R e^{-(x^2+y^2)}\,dA\) over the unit disk using polar coordinates. Show full conversion, limit setup, and all integration steps. Conclude with `learnbox`.
2. **Example 2 — Cylindrical (Intermediate):** Find the volume of the region inside the cylinder \(x^2+y^2=4\), above \(z=0\), and below \(z=3-r\). Show cylindrical setup and full evaluation. Conclude with `learnbox`.
3. **Example 3 — Spherical (Applied Engineering):** Compute the mass of a solid hemisphere of radius \(a\) with density \(\rho = k z\) (density proportional to height — models sedimentation in a hemispherical tank). Interpret the result. Conclude with `learnbox`.

> Optionally add Example 4: A general change-of-variables example using a non-standard substitution to reinforce Jacobian computation.

### Section 7: Tabular Comparison / Workflow Reference

`booktabs` table comparing all four coordinate systems: transformation formulas, Jacobian, volume element, ideal use case (region shape), and a one-line engineering example.

### Section 8: Common Student Mistakes & Pitfalls

`mistakebox` with `tabular`: Mistake | Why | Correct Approach. At least one row per sub-topic:
- Forgetting the \(r\) factor in polar/cylindrical \(dA\) or \(dV\).
- Using \(\sin\theta\) instead of \(\sin\phi\) in spherical Jacobian.
- Computing \(J\) as \(J = \partial(u,v)/\partial(x,y)\) instead of its reciprocal when needed.
- Setting \(\theta\) range incorrectly for partial sectors.

### Section 9: Comprehensive Assessment Suite

1. **Viva-Voce Questions (6–8):** At least one per sub-topic on Jacobian meaning, coordinate conversion formulas, and when to use which system.
2. **Descriptive Exam Questions (4–5):** Full problems with structured answer hints.
3. **MCQs (5+):** At least one per sub-topic; bold correct option; single-line explanation.

### Section 10: Quick Recap & Formula Sheet

`learnbox` with 6–8 bullets: Jacobian formula, polar/cylindrical/spherical transformation equations, their respective area/volume elements, and decision rule for coordinate system selection.

---

## 3. STRICT QUALITY & COMPILATION SAFEGUARDS

- [ ] `\begin{document}` and `\end{document}` wrap entire content.
- [ ] Section 3 contains **exactly 4 `\subsection{}` entries**.
- [ ] No missing brackets, undefined control sequences, or unescaped special characters.
- [ ] Every `curiositybox`, `infobox`, `mistakebox`, and `learnbox` properly opened and closed.
- [ ] All TikZ/pgfplots visuals self-contained and compilable with `pdflatex`.
- [ ] Consistent notation: \(\rho\) for spherical radial distance, \(r\) for cylindrical/polar radial distance.
- [ ] All derivations show intermediate steps.
- [ ] Assessment includes at least one viva and one MCQ per atomic sub-topic.
