# OpenAI ten-proofs — Connes rigidity artifact pin

**Status:** Primary artifact **pinned**.  
**Date:** 2026-08-07  
**NON-CLAIMS:** Pinning ≠ endorsement. Does not assert Connes false or Lean correctness of OpenAI’s classical intent.

## Primary pointers

| Item | Value |
|------|--------|
| GitHub | https://github.com/openai/ten-proofs |
| Pinned commit (shallow clone) | `94bc0feb6a9ff12c7d31d6de640a725c9d43d2b6` |
| Paper PDF | https://cdn.openai.com/pdf/ten-proofs-oai.pdf |
| Local PDF | `docs/sources/openai-ten-proofs-oai.pdf` |
| PDF SHA256 | `EBC561AB5C53DBD240E17A8FDB6FFFEB648591ECA85DBFC7466F563638F8C566` |
| Reasoning walkthroughs | https://cdn.openai.com/pdf/reasoning-walkthroughs.pdf |
| Index page | https://openai.com/index/ten-advances-in-mathematics/ |
| Lean module | `ConnesRigidity.lean` (~37k lines) |
| Comparator | `ComparatorChallenges/E_ConnesRigidity.json` |
| formalization.yaml decl | `ConnesRigidity.exists_infinite_pairwise_nonisomorphic_propertyT_icc_groups_with_isomorphic_factors` |
| Also | `exists_nonisomorphic_propertyT_icc_groups_with_isomorphic_factors` |

**Note:** Full git tree of `openai/ten-proofs` is **not** vendored in this repo (gitignored). Re-clone at pinned SHA for rebuild audits.

## Claimed result (as stated by OpenAI)

From paper abstract / § on Connes:

- Conjecture 1.1 (Connes): ICC property-(T) groups with isomorphic group factors are isomorphic as groups.
- Theorem 1.2 (claimed): There exist finitely generated ICC property-(T) groups that are non-isomorphic but have isomorphic group factors; strengthened to infinitely many pairwise non-isomorphic realizations with isomorphic factors.

Lean export names match the infinite-family form.

## Relationship to Zhou

- Zhou arXiv:2608.02327 claims concurrent independent counterexample with GPT-5.6 Sol assistance, citing OpenAI as concurrent.
- Constructions may differ; do not assume identity of groups without card-level compare (S007).

## Rebuild status

| Check | Status |
|-------|--------|
| Clone at SHA | Done locally (gitignored) |
| `lake build ConnesRigidity` | **Not run this turn** (mathlib-heavy; Blocker/Soft — schedule separate CI machine time) |
| Independent Mathlib def fidelity | Open (definition-drift risk) |

## Gaps

1. Full rebuild + axiom/sorry audit of OpenAI module at pinned SHA.  
2. Object map: Lean `HasKazhdanPropertyT` / `IsICC` / `TracialGroupFactorsIsomorphic` vs classical definitions.  
3. Comparison to Zhou \(\Gamma_1,\Gamma_2\).  
4. Nielsen ICC/(T) failure claims vs this codebase (needs Nielsen text).
