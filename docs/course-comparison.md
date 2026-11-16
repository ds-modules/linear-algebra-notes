# Course Comparison: Math 279 (LACC) × Math 56 (UCB) × EECS 16A (UCB)

**Status:** Internal working document — not part of the published Jupyter Book TOC.
**Purpose:** Support the joint Jupyter Book effort. Goal: identify what's duplicative, what's excellent, what's CC-level vs. UCB-level, and how to sequence a shared book "by weeks."
**Spine decision (2026-11):** **Math 279 Canvas Units 1–7** set topic order; merge complementary Math 56 / EECS 16A material where it fills gaps or strengthens applications. See [overview.md](overview.md), [calendar.md](calendar.md), [canvas/](canvas/).

**Last updated:** 2026-11-15

---

## 0. Context & Sources

| Course | Institution | Audience | Role in this project | Primary local source |
|---|---|---|---|---|
| **Math 279** — Linear Algebra for Data Science | LA City College (community college) | CC students, DS-focused | The book's home course; the audience we're building *for* | `/Users/jedwin321/linear_algebra/MATH279-Students` (student notebook repo) |
| **EECS 16A** — Foundations of Signals, Dynamical Systems & Info. Processing (formerly *Designing Info. Devices & Systems I*) | UC Berkeley | Large intro EE/CS majors course | Source of applied LA labs (GPS, PCA/SVD via voice recognition) to borrow from | `/Users/jedwin321/linear_algebra/sp26-labs` (Sp26 software labs) + [eecs16ab.github.io/16a.html](https://eecs16ab.github.io/16a.html) (full lecture/note sequence) |
| **Math 56** — Linear Algebra | UC Berkeley | Math majors, more rigorous/proof-based | Being rebuilt by Alex Paulin as an accompanying textbook; source of a clean, complete rigorous topic progression | `Math56.md` in this repo (TOC + lecture schedule copy-pasted from the textbook) |

**Key caveat about EECS 16A sources:** the local `sp26-labs` repo only contains **5 software notebooks** (Python Bootcamp, Shazam, APS, VR1, VR2) — a *subset* of the full course. The full course also has **26 lectures** with accompanying written notes (Notes 0–23) covering topics like Imaging/Tomography and Touchscreens that currently have **no corresponding notebook** in `sp26-labs` (they exist as lecture notes / discussion / homework instead, and appeared in some older lab repos like `fa24`). Both layers are captured below and distinguished as "Lecture/Note" vs. "Lab notebook."

---

## 1. Topic Coverage Summary Matrix

Legend: ● Full coverage &nbsp;·&nbsp; ◐ Partial / implicit coverage &nbsp;·&nbsp; ○ Not covered

| # | Topic | Math 56 (UCB) | EECS 16A (UCB) | Math 279 (LACC) |
|---|---|---|---|---|
| 1 | Vectors: definition, notation, geometric visualization | ● Ch.1.1 (Wk1) | ● Lec 1–3 (Imaging/Tomography framing) | ● Lab 4 |
| 2 | Vector algebra: addition, scaling, linear combinations | ● Ch.1.2 (Wk2) | ◐ implicit in Lec 2–5, Bootcamp NumPy ops | ● Lab 4 |
| 3 | Subspaces & span | ● Ch.1.3 (Wk2) | ● Lec 4–5, Notes 2A/2B/4 | ◐ implicit in Lab 4-2 (spanning/basis mentioned, not a dedicated exercise) |
| 4 | Linear independence, basis, dimension | ● Ch.1.4 (Wk2) | ● Lec 4–5, Note 11A | ● Lab 4-2 (independence, RREF/basis via `sympy`) |
| 5 | Dot product, norm, angle, orthogonal complement (geometry) | ● Ch.1.5 (Wk3) | ◐ APS Task 1 (cross-correlation as inner products) | ● Lab 5 (dot product intro) |
| 6 | Linear functions on Rⁿ | ● Ch.2.1 (Wk3) | ◐ folded into Lec 6 matrix mult. | ○ |
| 7 | Linear transformations Rⁿ→Rᵘ, matrix equations | ● Ch.2.2 (Wk4) | ● Lec 6, Note 3/5 | ○ (mentioned conceptually via graphics/NN examples, no dedicated lab) |
| 8 | Column space, null space, image, rank-related subspaces | ● Ch.2.3 (Wk4) | ● Lec 8, Note 7/8 (null space, column space) | ◐ Lab 4-2/4-3 (column space via RREF pivots; null space is a stated course outcome but **no notebook exercise exists**) |
| 9 | RREF / parametric solutions | ● Ch.3.1 (Wk5) | ● Lec 3, Note 1A/1B | ● Lab 4-2 (`sympy.rref`) |
| 10 | Gaussian elimination algorithm | ● Ch.3.2 (Wk5) | ● Lec 3 | ● Lab 1 (manual row ops + `np.linalg.solve`) |
| 11 | Existence & uniqueness, rank–nullity theorem | ● Ch.4.1 (Wk6) | ◐ implicit | ◐ Lab 4-3 (rank-nullity *stated*, not derived) |
| 12 | Basis/dimension computations (col/row/null space) | ● Ch.4.2 (Wk6) | ◐ Note 7/8 | ◐ Lab 4-2 (column space basis only) |
| 13 | Matrix operations (add, scale, multiply), transpose | ● Ch.5.1–5.2 (Wk7) | ● Lec 6, Bootcamp | ● Lab 2 |
| 14 | Matrix inverse | ● Ch.6.1 (Wk7) | ● Lec 7 | ● Lab 2 (`np.linalg.inv`) |
| 15 | LU / PLU factorization | ● Ch.6.2 (Wk7–8, not on lecture table but in text) | ○ | ● Lab 2, Test 1 (`scipy.linalg.lu`) |
| 16 | Determinants | ● Ch.7 (Wk8) | ○ | ◐ Lab 4-2 (as alt. independence test), Test 2 |
| 17 | Coordinates w.r.t. a basis, change of basis | ● Ch.8 (Wk9) | ○ | ◐ Lab 4-3 (centering / PCA framed loosely as "change of basis") |
| 18 | Similar matrices, diagonalizability (via coordinates) | ● Ch.9 (Wk9) | ○ | ○ |
| 19 | Eigenvalues, eigenvectors, eigenspaces | ● Ch.10.1 (Wk10) | ● Lec 9–11, Note 7/8/9 (incl. PageRank) | ● Lab 7 (`np.linalg.eig` on covariance matrix) |
| 20 | Diagonalization | ● Ch.10.2 (Wk10) | ◐ | ○ |
| 21 | Markov chains / PageRank application | ● §10.4 Project (Wk10) | ● Lec 9 (PageRank) | ○ |
| 22 | Orthogonal bases, Gram–Schmidt, QR factorization | ● Ch.11.1 (Wk11) | ○ | ● Lab 5 (Gram–Schmidt); **QR is a stated course outcome but has no notebook exercise** |
| 23 | Orthogonal matrices, coordinate systems | ● Ch.11.2–11.3 (Wk11) | ○ | ○ |
| 24 | Orthogonal projections | ● Ch.12.1 (Wk11) | ● VR1 (projection onto PCA basis, `QQᵗy`) | ◐ implicit in Gram-Schmidt (Lab 5) |
| 25 | Least squares / normal equations / linear regression | ● Ch.12.2 + Project (Wk13) | ● APS Task 6 (manual normal eqns for 2D positioning) | ● Lab 4-3, Lab 5 (`lstsq`, normal eqns, housing/insurance regression) |
| 26 | Symmetric matrices, spectral theorem, quadratic forms | ● Ch.13.1–13.2 (Wk13) | ○ | ○ |
| 27 | Singular Value Decomposition (SVD) | ● Ch.13.3 (Wk15) | ● VR1/VR2 (`np.linalg.svd` for voice PCA) | ○ (PCA done via `sklearn.PCA`/covariance eigendecomposition, **SVD itself never named/used**) |
| 28 | PCA / dimensionality reduction / low-rank approximation | ● §13.3 Dimensional Reduction (Wk15) | ● VR1/VR2 (SVD→PCA→classification) | ● Lab 4-2, 4-3, 7 (`sklearn.PCA`, explained variance) |
| 29 | Data-as-vectors / EDA with real datasets | ○ (pure math text) | ◐ (audio/voice as data) | ● Labs 4, 4-3, 5, 7, Test 2 (stocks, housing, insurance, wine, Titanic) |
| 30 | Classification (correlation, nearest-centroid) | ○ | ● VR1/VR2 (nearest-centroid classifier) | ○ |
| 31 | Signals/DSP (Fourier, DFT, spectrograms) — *not core LA* | ○ | ● Shazam, VR2 (Mel spectrograms) | ○ |
| 32 | Circuits/hardware (touchscreens, op-amps, capacitors) — *not LA* | ○ | ● Lec 12–22, Notes 11–19 | ○ |
| 33 | GPS/positioning, tomography/imaging as linear-system applications | ○ | ● Lec 1–2, 23 (Imaging, GPS); APS lab | ○ |

**Read this table as:** Math 56 is the only source with *full, systematically ordered* coverage of every core topic (it's a complete rigorous textbook). EECS 16A and Math 279 each cover a real subset, chosen for their own applications — and the two subsets **only partially overlap**.

---

## 2. Shared vs. Unique Topics

### Covered by all three (the common core)
Vectors & vector algebra · linear independence/basis · RREF & Gaussian elimination · matrix operations & inverse · eigenvalues/eigenvectors · least squares/regression · PCA-flavored dimensionality reduction.

### Covered by Math 56 + EECS 16A, but **missing or only implicit in Math 279**
- Subspaces, span, column/null space as formal objects (279 uses RREF mechanically but doesn't build the column-space/null-space theory around it)
- Rank–nullity theorem (stated in 279, not developed)
- Formal linear transformations Rⁿ→Rᵘ (279 never names this explicitly)

### Covered by Math 56 + Math 279, but **missing from the EECS 16A software labs** (though present in 16A lecture notes)
- Determinants
- LU/PLU factorization
- Change of basis / coordinate systems (formal)

### **Unique to Math 56** (rigor/theory not needed at either applied level)
- Similar matrices & diagonalizability via coordinate changes
- Orthogonal matrices as a formal object; full spectral theorem & quadratic forms
- Full symmetric-matrix theory
- Formal "linear function" (Ch 2.1) before jumping to matrices

### **Unique to EECS 16A** (applied EE/signals context, not LA per se)
- Circuits (touchscreens, op-amps, capacitors) — hardware, not linear algebra
- Signal processing (DFT/FFT, spectrograms, Mel scale) — adjacent, used as *feature engineering* before the LA (PCA/SVD) step
- PageRank as a named application of eigenvectors
- GPS/tomography as the motivating narrative for "why linear systems"

### **Unique to Math 279** (data-science / CC-applied context)
- Direct pandas/EDA workflow on tabular real-world datasets (stocks, housing, insurance, wine, Titanic) — no analogous "load a CSV and explore" exercise in Math 56 or 16A
- `sklearn.PCA` used as a black box before/alongside manual eigendecomposition (bridges theory → practitioner tooling)
- Explicit "vector space axiom checking" exercise on custom vectors (pedagogically closer to a first-encounter than 16A's applied jump-in)

### Notable gaps *within* Math 279 itself (relative to its own stated outcomes)
- **QR decomposition** and **null space** are explicit **README learning outcomes** but have **no corresponding notebook exercise** anywhere in the repo.
- **Lab 3** and **Lab 6** are missing from the repo (numbering jumps 2→4 and 5→7) — likely just not yet shared, but worth flagging to Kee.
- **SVD is never explicitly taught** — PCA is only reached via `sklearn.PCA` or manual covariance-eigendecomposition, so students get the *result* of SVD/PCA without the *decomposition* Math 56 and 16A (VR1/VR2) both build from.
- Determinant is a stated Lab 2 learning goal but the actual determinant computation only shows up later (Lab 4-2, as an alternate independence test) and on Test 2 — there's a lecture/lab mismatch.

---

## 3. Depth & Pacing — Where They Diverge (CC vs. UCB level)

| Dimension | Math 56 (UCB) | EECS 16A (UCB) | Math 279 (LACC) |
|---|---|---|---|
| **Proof rigor** | High — theorem/proof structure throughout, formal definitions before applications | Low–Medium — notes state results, minimal proof; labs are purely applied | Low — informal, "why this matters" framing, almost no proofs |
| **Pace** | 17 weeks, 24 numbered lecture topics, ~1.4 topics/week, two midterms + final, homework+quiz+project every week | Comparable pace but split: 26 lectures (theory, weekly) *plus* only 5 major lab modules (each ~2 weeks incl. buffer) | Slower/sparser: 10 notebooks total across a semester, several combined into multi-part "Units" (e.g. Unit 4 = 3 labs) suggesting more time per topic cluster |
| **Primary artifact** | Textbook chapter (read → exercises → challenge problems) | Lecture + written Note (theory) **decoupled from** Lab notebook (application); labs are large multi-week "systems" projects (GPS, voice ID) | Single notebook blending short theory recap + fill-in-the-blank code + real dataset + reflection questions, submitted per-lab to Canvas |
| **Assessment style** | Midterms/final (traditional proof + computation) | Autograded coding (Otter/custom) + live in-person checkoff (VR1/VR2 require 80% live classification accuracy) | Points-based notebook submissions + two "Test_LAB" notebooks (coding-based tests, not full traditional exams — those likely exist in Canvas, outside repo) |
| **Motivating narrative** | None needed — it's the math itself, with projects (Markov chains, linear classifiers, computer graphics, neural nets) as short "electives" at chapter ends | Strong overarching narrative: build a working system (imaging device → GPS locator → voice-recognition system) that LA makes possible | Narrative is dataset-driven ("predict housing prices," "predict insurance costs") rather than system-building |
| **Where CC-level pragmatism shows** | N/A (this *is* the UCB-level source) | N/A (this *is* the UCB-level source) | Skips formal null-space/column-space theory, doesn't require proof-writing, leans on `numpy`/`sklearn` functions rather than manual derivation for anything past Lab 5 |

**Implication for the shared book:** Math 56 gives us the *rigorous skeleton and correct ordering*; EECS 16A gives us *compelling, built-up applications* (esp. GPS/least-squares and PCA/SVD via voice) that could be adapted to a DS context; Math 279 tells us what a CC DS audience can actually absorb in one semester and what "hooks" (pandas EDA, real messy datasets) keep them engaged. None of the three alone is the right shape for the joint book — it should borrow Math 56's sequencing, 16A's applied narrative structure, and 279's dataset-first, low-rigor delivery style.

---

## 4. Sequence Alignment (when is each topic taught?)

Approximate position in the term ("Early" = first third, "Mid" = middle third, "Late" = final third), based on lecture/week numbers.

| Topic cluster | Math 56 | EECS 16A | Math 279 |
|---|---|---|---|
| Vectors, span, independence | Early (Wk 1–2) | Early (Lec 1–5) | Early (Lab 0–1, before Unit 4) |
| Linear transformations & matrix equations | Early–Mid (Wk 3–4) | Early (Lec 6–8) | Not explicit; matrix ops in Lab 2 (Early) |
| Gaussian elimination / solving systems | Mid (Wk 5) | Early (Lec 3, before independence even) | Early (Lab 1, *before* vectors formally — reversed order vs. the other two!) |
| Matrix algebra, inverse, LU, determinants | Mid (Wk 7–8) | Early (Lec 6–7; no det./LU in labs) | Early–Mid (Lab 2, Test 1) |
| Eigenvalues/eigenvectors | Mid–Late (Wk 10) | Early–Mid (Lec 9–11 — taught *much earlier* than in Math 56/279!) | Late (Lab 7, last topic in repo) |
| Orthogonality, Gram–Schmidt, QR | Late (Wk 11) | Not in labs (circuits dominate Lec 12–22) | Mid (Lab 5) |
| Least squares / regression | Late (Wk 13) | Mid–Late (APS, Lec 25–26) | Mid (Labs 4-3, 5 — taught *earlier* than 16A) |
| SVD / PCA | Late (Wk 15, last topic) | Late (VR1/VR2, final two labs) | Mid–Late (Labs 4-2, 4-3, 7 — spread across the term, introduced *earlier* than either UCB course) |

**Key pacing insight:** Math 279 introduces PCA concepts (via `sklearn`) as early as Lab 4-2, well before eigenvalues are formally covered in Lab 7 — the reverse of both UCB courses, which build eigenvalues/SVD theory first, then apply it. This "use the tool before deriving it" ordering is a deliberate (and defensible) CC pedagogical choice, but it's a genuine structural divergence worth discussing with Kee — the shared book needs to pick one philosophy (theory→tool vs. tool→theory) or explicitly support both paths.

Also notable: **EECS 16A teaches eigenvalues remarkably early** (Lecture 9–11 of 26, right after null/column space) because PageRank/eigen-analysis is core to the imaging/systems narrative — much earlier than a traditional syllabus (Math 56: week 10 of 17; Math 279: last lab). This is likely *too early* for a DS-focused CC course and probably shouldn't be copied directly.

---

## 5. Applications & Real-Datasets Matrix

| Application | Math 56 | EECS 16A | Math 279 |
|---|---|---|---|
| Linear classifiers | ● Ch.2.5.1 project | ● VR1/VR2 (nearest-centroid) | ○ |
| Computer graphics | ● Ch.2.5.2 project | ○ | ○ |
| Neural networks | ● Ch.2.5.3 project | ○ | ◐ (mentioned once re: transpose) |
| Markov chains / PageRank | ● Ch.10.4 project | ● Lec 9 | ○ |
| GPS / acoustic positioning | ○ | ● APS lab (core) | ○ |
| Audio/voice recognition | ○ | ● VR1/VR2, Shazam | ○ |
| Stock price data | ○ | ○ | ● Lab 4 (AAPL) |
| Housing price regression | ○ | ○ | ● Lab 4-3 (Boston Housing) |
| Insurance cost regression | ○ | ○ | ● Lab 5 |
| Wine quality / PCA | ○ | ○ | ● Lab 7 |
| Titanic EDA | ○ | ○ | ● Test 2 |
| Areas/Hadamard matrices | ● Ch.11.5 project | ○ | ○ |

**Takeaway:** Math 279's applications are squarely "tabular data science" (regression/PCA on CSVs); EECS 16A's are "signal/systems" (audio, GPS); Math 56's are classic pure-math electives (graphics, Markov chains, neural nets as linear-algebra illustrations, not full projects). A joint DS-for-CC book probably wants Math 279's dataset style as the primary vehicle, with 1–2 borrowed 16A-style "build a system" projects (least-squares GPS is a great, self-contained, low-hardware-dependency candidate) as enrichment/optional modules.

---

## 6. Granular Inventory — All Materials, In Teaching Order

### 6.1 Math 56 (UC Berkeley) — from `Math56.md` (textbook TOC + lecture schedule)

17-week schedule, each week ~2 lecture-topics + homework/quiz/project:

| Wk | Lecture topics | Textbook §§ |
|---|---|---|
| 1 | 1. What is a Vector? | 1.1 |
| 2 | 2. What is a Subspace? · 3. Efficiently Encoding Vectors | 1.2–1.4 |
| 3 | 4. Geometry of Vectors and Subspaces · 5. Linear Functions | 1.5, 2.1 |
| 4 | 6. Linear Transformations · 7. Subspaces Associated to Linear Transformations | 2.2, 2.3 |
| 5 | 8. Solving Systems in RREF · 9. Solving Systems via Gaussian Elimination | 3.1, 3.2 |
| 6 | 10. Existence and Uniqueness Properties · 11. Basis and Dimension Computations | 4.1, 4.2 |
| 7 | 12. Operations on Matrices · 13. Invertible Matrices | 5.1–5.2, 6.1 |
| 8 | Midterm 1 · 14. Determinants | 7.1–7.2 |
| 9 | 15. Coordinates w.r.t. a Basis · 16. Linear Transformations and Coordinates | 8.1–8.2, 9.1–9.2 |
| 10 | 17. Eigenvalues, Eigenvectors, Eigenspaces · 18. Diagonalizing Matrices | 10.1, 10.2 |
| 11 | 19. Orthogonal Bases and Matrices · 20. What is a Projection? | 11.1–11.3, 12.1 |
| 12 | Midterm 2 | — |
| 13 | 21. Optimization via Orthogonal Projections · 22. Symmetric Matrices and Spectral Theorem | 12.2, 13.1 |
| 14 | Thanksgiving | — |
| 15 | 23. Singular Value Decompositions · 24. Dimensional Reduction | 13.2 |
| 16 | Review | — |
| 17 | Final Exam | — |

Full textbook structure (5 parts, 13 chapters) with a **Review + Projects + Challenge Problems** section at the end of nearly every chapter — projects include Sparse Vectors, Linear Classifiers, Computer Graphics, Neural Networks, Markov Chains, Areas in Higher Dimensions, Hadamard Matrices, Linear Regression.

### 6.2 EECS 16A (UC Berkeley)

**Layer A — Lecture/Note sequence** (26 lectures, from [eecs16ab.github.io/16a.html](https://eecs16ab.github.io/16a.html)):

| Lec | Topic | Notes |
|---|---|---|
| 1 | Introduction to Imaging | Note 0 |
| 2 | Tomography and Linear Equations | Note 1A |
| 3 | Gaussian Elimination | Note 1A/1B |
| 4–5 | Span, linear independence and dependence | Note 2A/2B/4, Note 11A |
| 6 | Linear Transformations, Matrix Multiplication | Note 3/5 |
| 7 | Inversion | Note 5/6 |
| 8 | Vector Spaces: Null Space and Column Space | Note 7/8 |
| 9 | PageRank, Eigenvalues and Eigenspaces | Note 7 |
| 10–11 | Eigenvalues and Eigenspaces (continued) | Note 8/9 |
| 12 | Node Voltage Analysis, Voltage Divider *(circuits, not LA)* | Note 11A/11B |
| 13 | 1D Touchscreen *(circuits)* | Note 11B |
| 14 | 2D Resistive Touchscreens *(circuits)* | Note 12 |
| 15–16 | Superposition and Equivalence *(circuits)* | Note 13/14 |
| 17–18 | Capacitors *(circuits)* | Note 15/16 |
| 19 | Capacitive Touchscreen *(circuits)* | Note 17 |
| 20 | Op-amps and Negative Feedback *(circuits)* | Note 17 |
| 21 | Op-amp circuit analysis *(circuits)* | Note 18 |
| 22 | Circuit Design Examples *(circuits)* | Note 19 |
| 23 | Introduction to GPS | Note 20 |
| 24 | Correlation and Classification | Note 21 |
| 25–26 | Least Squares Algorithm | Note 22/23 |

**Layer B — Software lab notebooks** (`sp26-labs`, 5 notebooks, released in this order):

| Lab | Topic | LA relevance | Key techniques |
|---|---|---|---|
| Python Bootcamp | Python/NumPy fluency | Low–Moderate | array ops, slicing, transpose, inverse, `Ax=b` |
| Shazam | Audio fingerprinting | Low | FFT, spectrograms, hashing (DSP, not LA) |
| APS | Acoustic positioning ("mini-GPS") | **High** in Task 6 | cross-correlation as inner products; manual least-squares/normal equations for 2D position |
| VR1 | Voice recognition, PCA via SVD | **Very High** | `np.linalg.svd`, projection onto PC basis, nearest-centroid classification |
| VR2 | Voice recognition + spectral features | **Very High** | Mel spectrograms → flatten/aggregate → same SVD/PCA/classification pipeline |

*Not present in `sp26-labs` but part of 16A's broader tradition: Imaging (single-pixel camera / tomography, high LA relevance) and Touchscreen (mostly circuits, low LA relevance) labs, found in older repos like `fa24`.*

### 6.3 Math 279 (LA City College) — from `MATH279-Students`

Flat repo, no subfolders, 10 notebooks + 6 CSV datasets. Inferred order (numbering + prerequisite text; **Lab 3 and Lab 6 are missing from the repo**):

| Order | Notebook | Topic | Dataset(s) | Type |
|---|---|---|---|---|
| 0 | Lab 0 | Python/Jupyter onboarding | — | Coding |
| 1 | Lab 1 | Linear systems, Gaussian elimination, `np.linalg.solve` | — | Blend |
| 2 | Lab 2 | Matrix ops, inverse, LU/PLU factorization | — | Blend |
| — | *Lab 3* | **missing** | — | — |
| 3a | Lab 4 | Vectors, vector-space axioms, linear combinations, data-as-vectors | AAPL stock | Blend |
| 3b | Lab 4-2 | Linear independence (solve + determinant), RREF/basis, PCA intro | synthetic | Blend |
| 3c | Lab 4-3 | Rank, least squares (`lstsq`), housing regression, change of basis via PCA | Boston Housing | Blend (applied) |
| 4 | Lab 5 | Dot product, Gram–Schmidt, normal equations, insurance regression | Insurance | Blend (applied) |
| — | *Lab 6* | **missing** | — | — |
| 5 | Lab 7 | Covariance, eigenvalues (`np.linalg.eig`), manual vs. `sklearn.PCA` | Wine Quality | Blend (applied) |
| T1 | Test 1 (LAB) | Matrix construction, multiplication, LU, `solve` | — | Coding assessment |
| T2 | Test 2 (LAB) | Linear combos, independence, column-space basis, Titanic EDA | Titanic | Blend |

Stated README learning outcomes not matched by any notebook exercise: **null space**, **QR decomposition**.

---

## 7. Recommendations for the Shared Jupyter Book

1. **Adopt Math 279 Canvas Units 1–7 as the book's backbone** (systems → matrices → dets → vectors/spaces → geometry/QR → linear maps → eigen/SVD). Local copies live in [canvas/](canvas/). Week plan: [calendar.md](calendar.md).
2. **Keep Math 279's DS / low-rigor delivery** (motivate-first, notebooks, real CSVs) as the default voice.
3. **Merge Math 56 where 279 is thin or missing:** null space / rank–nullity exercises, named QR, orthogonal projections → least squares, named SVD, optional chapter projects (Sparse Vectors, Classifiers, Markov, Regression).
4. **Borrow 16A applied modules that complement 279:**
   - Imaging/tomography notes as the Unit 1 systems motivator
   - APS Task 1 (correlation as inner product) with Unit 5
   - APS Task 6 (least-squares positioning) in the inserted least-squares week
   - PageRank with Unit 7.1
   - VR1 SVD→PCA→classify with Unit 7.4 (adapt off audio if needed)
   - Skip touchscreens/op-amps/capacitors and Shazam/DFT-as-core
5. **Front-load coding (Wk 0):** Jupyter, NumPy, matplotlib (279 Lab 0 + 16A Bootcamp); then pandas with Unit 4; sympy.rref with systems/independence; SciPy LU with Unit 2.3; `lstsq`/`eig`/`svd`/`sklearn.PCA` at the matching units.
6. **Insert an explicit least-squares / regression week** after Unit 5 (projections/QR) — essential LA for DS, present in 56/16A/279 labs but not a Canvas unit title.
7. **Teach SVD by name** in Unit 7.4 before/with `sklearn.PCA` (279 Lab 7 currently can skip SVD).
8. **Recover Math 279 Labs 3 and 6** from Kee when possible (numbering gaps in the student repo).
9. **Pace on a ~16–17 week calendar** aligned to Canvas units (see [calendar.md](calendar.md)); compress for LACC term dates as needed.
10. **Use Math 56 textbook as a reference companion**, not the weekly order — Paulin/Nadler/Gupta remains the rigor/completeness check ([Math56.md](Math56.md)).

---

## 8. Source Links (from email thread, for reference)

- Math 279 student notebooks: https://github.com/lamkt1/MATH279-Students
- EECS 16A Sp26 labs: https://github.com/ee16a/sp26-labs
- EECS 16A lecture notes/outline: https://eecs16ab.github.io/16a.html
- EECS 16A assignments: https://eecs16a.org/
