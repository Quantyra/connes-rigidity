# Reconstruction card — OpenAI Connes rigidity (ten-proofs)

**Date:** 2026-08-07  
**Pin:** `docs/reconstruction/openai-ten-proofs-connes-pin.md`  
**NON-CLAIMS:** Does not endorse the counterexample or Lean-classical fidelity.

## 1. Claimed main theorems (Lean names)

From `ConnesRigidity.lean` / `formalization.yaml` at `94bc0feb`:

1. `exists_nonisomorphic_propertyT_icc_groups_with_isomorphic_factors`  
2. `exists_infinite_pairwise_nonisomorphic_propertyT_icc_groups_with_isomorphic_factors`

Paper Theorem 1.2 / infinite-family strengthening: finitely generated ICC property-(T) groups, non-isomorphic, isomorphic group factors; infinitely many pairwise non-isomorphic with common factor class.

## 2. Construction outline (from paper section titles + Lean names)

Paper TOC signals:

- Group factors, property (T), Fourier duality  
- ICC, property (T), and the basic counterexample  
- Analytic inputs: `PaperAnalyticInput`, `lambdaGroup` / `gammaGroup n`  
- Spectral detection / finite spectral detection → property (T)  
- Module orbits → ICC  
- `paper_factors_isomorphic`  
- Pairwise non-isomorphism of \(\gamma\) family  

Lean endgame uses `manuscriptInfinitePropertyTFiber` assembling FG, ICC, (T), factor isomorphisms, non-isomorphism.

**Gap:** Full algebraic presentation (generators/relations or semidirect data) needs dedicated extract from paper §5+ and Lean defs (`paperVector`, dual actions, etc.) — partial only this turn.

## 3. ICC outline

- Lean: `IsICC`, `lambda_isICC`, `gamma_icc`  
- Paper: infinite non-identity conjugacy classes  
- **Gap:** Map Lean conjugacy definition to classical ICC; orbit infinitude lemmas.

## 4. Property (T) outline

- Lean: `HasKazhdanPropertyT`, spectral detection gap theorems, `lambda_hasKazhdanPropertyT_unconditional`  
- **Gap:** Equivalence of Lean Kazhdan def to classical Delorme–Guichardet / almost-invariant vectors; no independent human audit this turn.

## 5. Factor isomorphism outline

- Lean: `TracialGroupFactorsIsomorphic`, `paper_factors_isomorphic`, `groupVonNeumannAlgebra`  
- **Gap:** Confirm von Neumann closure / trace implementation matches classical \(L(G)\).

## 6. vs Zhou

| | OpenAI | Zhou |
|--|--------|------|
| Surface | Lean megafile + paper | arXiv PDF, explicit \(\Gamma_i=D_i\rtimes H\) |
| Field | Appears \(\mathbb{F}_2\)-flavored (ZMod 2 in file head) | \(k=\mathbb{Z}/2\mathbb{Z}\), SL₃(k[t])×Sp₄ |
| Concurrent | Cited by Zhou | Claims concurrent with OpenAI |

**Do not merge** constructions without isomorphism proof.

## 7. Nielsen failure-path claims

Cannot check — Nielsen fulltext Blocker.

## 8. Rebuild

Not executed this turn. Soft Blocker: schedule `lake build ConnesRigidity` at `94bc0feb` on a mathlib-cached runner; record axiom/sorry audit.
