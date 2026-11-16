# Shared Calendar (Linear Algebra — Math 279)

- **C-ID alignment:** [Introduction to Linear Algebra (C-ID MATH 250, descriptor record 267)](https://data-c-idsystem.org/descriptors/final/show/267), 3.0 units.
- **Prerequisite assumption:** Calculus I (C-ID MATH 210, MATH 211, or MATH 900S), as required by the descriptor.
- **Spine:** Math 279 Canvas Units 1–7 ([canvas/](canvas/)).
- **Enrich from:** Math 56 textbook/projects and EECS 16A applied labs where they complement 279.
- **Coding:** Week 0 bootcamp, then tools reappear the week they are first required.
- **Proof:** Short proof-writing tasks are embedded throughout the term to meet the C-ID objective; coding supports but does not replace mathematical reasoning.

| Wk | Math topics | Skills / applications | Canvas / textbook | 56 / 16A reference | Assignments / labs |
|---|---|---|---|---|---|
| 0 | Pre-term coding readiness | Jupyter, Python basics, NumPy arrays/slicing/broadcasting/matmul, `solve`/`inv`, matplotlib | — | 16A Python Bootcamp | **279 Lab 0** + Bootcamp |
| 1 | Systems of linear equations; substitution and elimination; matrix form | Translate among equations, augmented matrices, and geometry of lines/planes | Unit 1; 56 §§3.1–3.2 | 16A Notes 0–1 (imaging / tomography hook) | Canvas Unit 1 reading + systems worksheet; justify solution equivalence |
| 2 | Gauss–Jordan; RREF; parametric solutions; consistency | Decide and justify unique / infinite / no solution; start `sympy.rref` and `np.linalg.solve` | Unit 1; 56 §§3.1–3.2 | 16A Lec 3 (Gaussian elimination) | **279 Lab 1** + RREF quiz |
| 3 | Matrix operations, transpose, diagonal / triangular / symmetric matrices; inverse | Compose transforms in code; connect invertibility to solution behavior; solve `Ax=b` via inverse when appropriate | Units 2.1–2.2; 56 §§5.1–5.2, 6.1 | — | Canvas 2.1–2.2; **279 Lab 2** (ops / inverse); invertibility proof |
| 4 | Elementary matrices; LU / PLU factorization | Factor once, solve many right-hand sides with `scipy.linalg.lu` | Unit 2.3; 56 §6.2 | — | Canvas 2.3; **279 Lab 2 / Test 1** (LU) |
| 5 | Determinants and their properties | Use det as an independence / invertibility test (`np.linalg.det`) | Units 3.1–3.2; 56 Ch.7 | — | Canvas 3.1–3.2 + determinants quiz |
| 6 | Vectors in Rn; real vector spaces; subspaces | pandas CSV + light EDA; data-as-vectors; check space axioms and prove a subset is / is not a subspace | Units 4.1–4.3; 56 §§1.1–1.3 | — | Canvas 4.1–4.3; **279 Lab 4** (AAPL / axioms); subspace proof |
| 7 | Span; linear independence / dependence; basis and dimension | Build and test bases with RREF; interpret dimension of a feature space; write an independence proof | Units 4.4–4.5; 56 §1.4 | — | Canvas 4.4–4.5; **279 Lab 4-2**; proof checkpoint |
| 8 | Rank, nullity, and column / row / null spaces; coordinates and change of basis | **Gap fill:** compute all matrix-generated spaces and apply rank–nullity; Midterm 1 | Units 4.6–4.7; 56 §§4.1–4.2, Ch.8 | — | Canvas 4.6–4.7; null-space / nullity add-on; Midterm 1 (Wks 1–7) |
| 9 | Dot product, length, angle; inner product spaces; orthogonal projections | Similarity / correlation; projection formula preview | Units 5.1–5.2; 56 §§1.5, 12.1 | 16A APS Task 1 (cross-correlation) | Canvas 5.1–5.2; **279 Lab 5** (dot) + correlation mini-lab |
| 10 | Orthonormal bases; Gram–Schmidt; QR factorization | **Gap fill:** name and compute QR (279 outcome, thin in labs) | Unit 5.3; 56 §11.1 | — | Canvas 5.3; **279 Lab 5** + QR notebook |
| 11 | Least squares; normal equations; linear regression | Fit models on CSVs; interpret residual as orthogonal to column space | 56 §12.2 (+ Canvas 5.2 projections) | **16A APS Task 6** (GPS / positioning) | **279 Labs 4-3, 5** (housing / insurance); optional APS Task 6 |
| 12 | Linear transformations; kernel and range; injective / surjective / inverse maps; matrices for transforms | Map geometry (stretch/rotate); use kernel and range to justify injectivity / surjectivity; Midterm 2 | Units 6.1–6.3; 56 Ch.2 | 56 projects: Linear Classifiers / Computer Graphics (optional) | Canvas 6.1–6.3; linearity / invertibility proof; Midterm 2 (Wks 8–11) |
| 13 | Eigenvalues, eigenvectors, eigenspaces; diagonalization | Interpret eigen-directions; PageRank / Markov as apps | Units 7.1–7.2; 56 §§10.1–10.2 | 16A Lec 9 (PageRank); 56 Markov project | Canvas 7.1–7.2; `np.linalg.eig` lab; PageRank mini-lab |
| 14 | Break / catch-up |  |  |  |  |
| 15 | Symmetric matrices; orthogonal diagonalization; SVD; PCA | **Named SVD** then `sklearn.PCA`; classify with nearest-centroid | Units 7.3–7.4; 56 §§13.1–13.3 | **16A VR1** (SVD→PCA; adapt off audio OK) | Canvas 7.3–7.4; **279 Lab 7**; VR1-adapted notebook |
| 16 | Cumulative review | Connect systems → subspaces → projections → transformations → eigen → SVD; synthesize computational and proof methods |  |  | **279 Test 2**-style blend + proof portfolio + practice final |
| 17 | Final |  |  |  | Cumulative final covering C-ID content and objectives |

## C-ID MATH 250 alignment check

| Descriptor requirement | Calendar coverage |
|---|---|
| Systems; Gaussian / Gauss–Jordan elimination; inverse matrices | Weeks 1–4 |
| Matrix algebra, transpose, invertibility, and special matrices | Weeks 3–5 |
| Determinants and their properties | Week 5 |
| Vectors in Rn; real vector spaces and subspaces | Week 6 |
| Independence / dependence; basis and dimension | Week 7 |
| Row, column, and null spaces; rank and nullity | Week 8 |
| Change of basis | Week 8 |
| Inner products; dot product, norm, angle, and orthogonality | Weeks 9–10 |
| Orthogonal / orthonormal bases and Gram–Schmidt | Week 10 |
| Linear transformations; kernel, range, matrices, and inverse maps | Week 12 |
| Eigenvalues, eigenvectors, eigenspaces, and diagonalization | Weeks 13 and 15 |
| Orthogonal diagonalization of symmetric matrices | Week 15 |
| Applications of eigenvalues and eigenvectors | Weeks 13 and 15 |
| Proof writing: subspaces, independence, linearity, injectivity, and surjectivity | Weeks 3, 6–7, 12, and 16 |

The inserted least-squares, QR, SVD, PCA, and coding work enriches the course without replacing any required C-ID content.

## Notes

- Week **11** is inserted (not a Canvas unit title) because least squares is essential for DS and already appears in 279/56/16A materials.
- Canvas HTML readings: [canvas/README.md](canvas/README.md).
- Still out: 16A circuits / touchscreens; Shazam/DFT as required content.
- Open: recover 279 Labs 3 and 6 when available.
