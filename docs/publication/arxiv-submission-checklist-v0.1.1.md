# arXiv submission checklist — Nielsen reductio refutation v0.1.1

**Status:** Ready for Dan human approval  
**Category suggestion:** `math.OA` (Operator Algebras); secondary `math.GR` optional  
**License on arXiv:** match report CC-BY-4.0 or arXiv default + note Zenodo CC-BY-4.0  

## Immutable freeze objects
| Object | Pin |
|--------|-----|
| Science git | `dda001b` / tag `v0.1.1-report` |
| Lean git | `c1e6dfb` / tag `v0.1.1-obstruction` |
| Science version DOI | https://doi.org/10.5281/zenodo.21859308 |
| Science concept DOI | https://doi.org/10.5281/zenodo.21845586 |
| Lean version DOI | https://doi.org/10.5281/zenodo.21859309 |
| Lean concept DOI | https://doi.org/10.5281/zenodo.21845588 |

## Title (camera-ready)
Hypothesis failure for Ioana's Theorem 8.2 under a twisted comultiplication

## Abstract (camera-ready, ≤~1920 chars)
We examine J. L. Nielsen’s argument that applies Ioana’s Theorem 8.2
(J. Amer. Math. Soc. 24 (2011)) to the twisted comultiplication
Θ(f u_g) = f u_g ⊗ Φ(u_g) built from an assumed isomorphism
Φ : L(G) → L(H), in order to obtain injective group morphisms and run a
reductio related to Connes’ rigidity conjecture. We show that this
application does not go through: by construction,
Θ(A_G) ⊆ A_G ⊗̄ L(H), which is the forbidden tensor leg in Ioana’s
hypothesis (2). Consequently Theorem 8.2 does not license the rigid-case
output for this map, and the reductio that depends on that output does
not start. The argument is supported by primary-source pins of Nielsen
NIEWTC and Ioana JAMS 2011, and by a machine-checked Lean 4 packaging
(v0.1.1-obstruction) that imports one classical Nielsen by-construction
package and proves failure of hypothesis (2) and non-licensing of rigid
output for that application. We do not claim that Connes’ rigidity
conjecture is true or false, and we do not validate or refute the
OpenAI or Zhou counterexample constructions.

## MSC (suggested)
46L10, 46L35, 22D25, 03B35

## Keywords
Connes rigidity; Ioana theorem; twisted comultiplication; Popa intertwining; Lean 4; formal verification

## Body source
- Markdown (long form): `docs/reports/2026-08-08-nielsen-ioana-theta-reductio-refutation.md`
- **arXiv TeX (A001-style):** `docs/notes/nielsen-ioana-theta-reductio-arxiv.tex`
- **Rendered PDF:** `docs/notes/nielsen-ioana-theta-reductio-arxiv.pdf`
- **PDF SHA-256:** `C573090FE2AA13661229D4C75E88A61476762310350A62DBBB3E90DEFF920E60`
- **Pages:** 4 (after quality-gap close: notation, Popa cite, Lean verify recipe, Remarks)
- **Build:** two-pass `pdflatex`; packages `array`, `seqsplit`, `xurl` (margin-safe hashes/paths)

Ensure before upload:
- [x] DOI table uses v0.1.1 version + concept DOIs
- [x] Lean declaration names match `NielsenThetaImage` exports
- [x] Module paths + tag tree URL + cold-clone verify commands
- [x] Non-claims section intact in PDF
- [x] No third-party PDF dumps attached as “our” content
- [x] Bibliography: Ioana DOI; Popa 2006; Nielsen NIEWTC pin; Zenodo DOIs
- [x] Re-hash PDF after quality-gap TeX edit; attach PDF+TeX to GitHub release

## Quality bar (lane) — all required
- [x] Four-role freeze (proof-adversarial, non-claims, package/metadata, Lean/build)
- [x] Freeze packet on disk
- [x] Lean build + no-sorry + axiom register at cited SHA
- [x] `#print axioms` profile disclosed
- [x] GitHub releases cut
- [x] Zenodo concept + version DOIs live
- [ ] Dan final approval for arXiv upload
- [ ] ORCID works import (version DOIs)

## Comments to moderator (optional)
Bounded audit note in math.OA: obstruction to a specific published application of Ioana Thm 8.2; companion Lean formalization on Zenodo; no claim on Connes T/F.

## After accept
1. Replace arXiv id in report + CITATION.cff  
2. Link arXiv ↔ Zenodo related identifiers  
3. ORCID import both version DOIs  
4. Optional: short MathOverflow/community pointer with DOIs only  
