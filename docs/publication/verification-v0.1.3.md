# Verification record — v0.1.3-report candidate

Date: 2026-10-28. **Author verification only; independent publication gate pending.** This file is the public-safe closeout surface to update after independent reviews. It is not a final-review PASS or a fresh Lean build certificate.

## Source and version checks

Science started clean at `c2d61f5179507af2c2184d837ee9458e8d766a57`. `git fetch origin --tags` and `git ls-remote origin 'refs/heads/*' 'refs/tags/*'` confirmed the canonical remote and existing tags before selecting v0.1.3-report. The last public deposit remains v0.1.2-report; no tag or new DOI was created.

The new Nielsen PDF was checked with PyMuPDF and SHA256: 49 pages, 564856 bytes, `BC201CC37F897EEEDA2446D1926AB7945405E5A96CF27176CA0E4157476D324E`. Its title and substantive passages were checked against the local primary source. Both archived source PDF hashes were rechecked unchanged. See [source identities](../sources/nielsen-2026-10-28-identity.md). Page citations use published JAMS pagination and Nielsen PDF pagination, not control-character-sensitive text line numbers.

## Typesetting and packaging

Compiler: **Tectonic 0.17.0**, existing user-local installation. Initial build command, from the science root (the output directory is an external private build directory, represented here as `<build-dir>`):

```text
tectonic --keep-logs --keep-intermediates --outdir <build-dir> docs/notes/nielsen-ioana-theta-reductio-arxiv.tex
```

Tectonic automatically reran TeX and completed with exit code 0. The resulting PDF was copied unchanged to `docs/notes/nielsen-ioana-theta-reductio-arxiv.pdf`. It is **6 pages**. The final log has no unresolved references/citations, LaTeX warnings, overfull/underfull boxes or missing-character warnings. PDF text extraction has no replacement character or unresolved-reference markers. All six final pages were rendered with PyMuPDF and visually inspected: formulas, citations, hashes, declaration table, margins and page breaks are legible. The revision note begins on page two. Hashes and byte counts are in [the artifact manifest](artifact-manifest-v0.1.3.json).

The source ZIP contains exactly four files: manuscript TeX with inline bibliography, source identities, build README, and license notice. It contains no generated PDF, auxiliary files, third-party PDFs, runtime logs, secrets or external figure dependencies. ZIP integrity was checked, and the archive was extracted into a fresh directory and compiled using:

```text
tectonic --keep-logs <extracted-dir>/nielsen-ioana-theta-reductio-arxiv.tex
```

This clean-source build also exited 0. Its six-page text and rendered pages were compared with the candidate PDF. Byte-for-byte PDF reproducibility is not asserted across build timestamps or engines. Conventional two-pass pdflatex instructions are supplied as an alternative recipe, but were not tested in this revision.

**Nonfatal environment diagnostic:** both Tectonic invocations printed `Fontconfig error: Cannot load default config file: No such file: (null)`. The bundled TeX fonts loaded, both builds completed, and visual inspection found no missing glyphs. This diagnostic is recorded rather than hidden. Build logs and page renders remain outside the public repository.

## Lean source inspection and coverage

Repository: https://github.com/Quantyra/connes-rigidity-lean
Tag: `v0.1.1-obstruction`
Exact peeled SHA: `c1e6dfb7347261336714e57de86e6f25c7627461`.

`git ls-remote` confirmed the tag target. A private, no-checkout clone was used for `git show <SHA>:<module-path>` source inspection. No Lean source was modified and **no local Lean build was run**. The independent Lean auditor must supply current build and dependency-closure evidence; the author does not infer a fresh compilation result from historical metadata.

| Claim / scope | Coverage | Exact module and declaration at the pinned SHA | Limitation |
|---|---|---|---|
| Concrete Nielsen image situation | Classical import; not constructed in Lean | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_lands_in_bad_leg` | Custom axiom supplying a nonempty semantic situation; no concrete spatial tensor product, crossed product or range construction |
| Containment with nonzero unit supplies a condition-(1) witness | Existing semantic Lean proof; current build audit pending | `ConnesRigidity.Ioana.OperatorAlgebra.IntertwiningConditionOne`: `intertwinesIntoConditionOne_of_le` | Supported-algebra interface; not a full proof of all equivalent Popa criteria |
| Supplied containment blocks hypothesis (2) | Existing semantic Lean proof; current build audit pending | `ConnesRigidity.NielsenThetaBlock`: `image_subseteq_M1_LH_blocks_ioana82_hyp2`, `nielsenTheta_blocks_ioana82_hyp2` | Both semantic non-intertwinings are required; no full Ioana theorem formalization |
| Paper-specific imported situation has failed hypothesis (2) | Lean-partial analytic coverage; existing conditional semantic proof | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_blocks_ioana82_hyp2` | Existential semantic situation obtained from the classical import |
| This application does not license rigid output | Lean-partial analytic coverage; existing conditional semantic proof | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_no_rigid_output_licensed_by_hyp2` | Licensing is modeled by hypothesis-(2) holding together with nonempty abstract output; not nonexistence of group morphisms |
| Theorem 8.2's corrected input/conclusions; Section 9 setup; Nielsen Section 21 response | Literature comparison, not a new theorem or claimed Lean formalization | Primary sources at the recorded page/hash anchors | No claim that every possible extension or alternative route fails |

The source-inspected bridge uses the supported algebra's nonzero local unit for both projections and the partial isometry. The manuscript's unital analytic case uses 1. The main paper-specific exports are existential statements about an imported semantic situation, not constructions of the analytic objects. The recorded historical axiom profile is the one classical import plus `propext`, `Classical.choice`, and `Quot.sound`; independent verification of that closure is pending. No new theorem or Lean code was introduced.

## Independent gate — update on closeout

| Role | Current verdict | Evidence |
|---|---|---|
| Proof-adversarial | PENDING | Parent-coordinated review of committed candidate |
| Non-claims | PENDING | Parent-coordinated review of committed candidate |
| Package/metadata | PENDING | Parent-coordinated review of committed candidate |
| Lean/build/audit | PENDING | Exact pinned SHA, build, proof-hole and axiom closure, statement match required |
| Human approval | PENDING | Historical August approval does not apply |

Aggregate: **not approved for public freeze**. No publication, push, tag, release, upload or outreach occurred in the author phase. Remaining work: independent reviews, resolution of findings, gate-approved finalization and any subsequent DOI/approval updates.
