# Shared Book Overview

**Status:** Internal working doc (not in Jupyter Book TOC).  
**Spine:** Math 279 (LACC) — Canvas *Linear Algebra for DS* Units 1–7 + student notebooks.  
**Enrich from:** Math 56 (rigor/gaps/projects) and EECS 16A (applied LA labs/notes) where they complement 279.

## Sources

| Source | Role |
|---|---|
| Math 279 Canvas readings | Topic set + teaching order — see [canvas/](canvas/) |
| Math 279 notebooks ([MATH279-Students](https://github.com/lamkt1/MATH279-Students)) | Coding labs, CSVs, tests |
| Math 56 textbook / schedule | Fill theory gaps; optional projects; alternate exposition |
| EECS 16A notes/labs | Imaging/systems hook, correlation, PageRank, APS least squares, SVD–PCA |

## Design rules

1. Follow **Canvas Unit 1→7 order** (systems first, then matrices, dets, vectors, geometry, maps, eigen/SVD).
2. Teach **required coding** up front (Week 0 tooling) and again when a tool is first needed for the math.
3. Merge **56 / 16A only when they strengthen a 279 topic** or close a gap (null space exercise, named QR/SVD, least squares depth, strong apps).
4. Skip 16A circuits/touchscreens and DSP-only labs (Shazam).

## Taught vs not (high level)

**Taught (279 Canvas + notebooks):** systems/Gauss–Jordan; matrix ops/inverse/LU; determinants; vectors/spaces/subspaces/span/independence/basis/dim/rank/change of basis; dot product/inner products/Gram–Schmidt; linear maps/kernel/range; eigen/diagonalization/symmetric/SVD; pandas EDA; regression; PCA via eig/`sklearn`.

**Add from 56/16A (important, slotted into calendar):**  
Week-0 coding bootcamp; imaging motivator for `Ax=b`; explicit null-space lab; QR as named factorization; orthogonal projections → least squares (normal equations); PageRank; APS-style positioning; named SVD before/with PCA; nearest-centroid classification.

**Not taught:** 16A hardware/circuits; heavy DSP; Math 56 full proof track / similar-matrices deep dive as required core.

## Coding stack (must cover)

| Skill | When |
|---|---|
| Jupyter + Python basics | Wk 0 |
| NumPy create / index / slice / reshape / elementwise ops | Wk 0 (reuse all term) |
| matplotlib (simple 2D arrows) | Wk 0 |
| matmul `@`, `solve`, `inv` | With systems / matrix chapters — **not** Wk 0 |
| pandas read_csv + light EDA | With Unit 4 / Lab 4 |
| Manual row ops + `np.linalg.solve` | Unit 1 / Lab 1 |
| `sympy.rref` | Unit 1 / Unit 4.4–4.6 |
| `scipy.linalg.lu` | Unit 2.3 / Lab 2 |
| `np.linalg.lstsq` / normal equations | After Unit 5 (projections) |
| `np.linalg.eig` | Unit 7.1 / Lab 7 |
| `np.linalg.svd` + `sklearn.PCA` | Unit 7.4 / Lab 7 + 16A VR1 |

## Related docs

- [calendar.md](calendar.md) — week plan  
- [canvas/README.md](canvas/README.md) — Canvas file index  
- [course-comparison.md](course-comparison.md) — 279 × 56 × 16A detail  
- [Math56.md](Math56.md) — Math 56 TOC / schedule snapshot  
