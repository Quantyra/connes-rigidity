# Verification record — prepared v0.1.3-report

Date: 2026-10-28. **Prepared, unreleased version; publication gate pending.** This public-safe record distinguishes completed independent reviews at their exact commits from pending checks of the prepared artifacts. It is not an aggregate PASS or a fresh Lean build certificate.

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

Final packaging normalizes the three source-package inputs to LF using scoped `.gitattributes` rules. Their archive bytes match the committed Git blobs. A rebuild after normalization has identical text and pixels on all six pages to the visually inspected PDF; the manifest records the final rebuilt PDF bytes.

**Nonfatal environment diagnostic:** both Tectonic invocations printed `Fontconfig error: Cannot load default config file: No such file: (null)`. The bundled TeX fonts loaded, both builds completed, and visual inspection found no missing glyphs. This diagnostic is recorded rather than hidden. Build logs and page renders remain outside the public repository.

Prepared-artifact check (28 October 2026, successor to `bdbb133`): both the manuscript build and a fresh four-member ZIP extraction used `tectonic --keep-logs --only-cached nielsen-ioana-theta-reductio-arxiv.tex` in separate private directories and exited 0. All six pages matched in extracted text and 1.5x RGB pixels; all six were visually inspected. No unresolved references/citations, box warnings or missing-character diagnostics were found. The Fontconfig diagnostic above recurred in both builds. These are author artifact checks; independent final artifact delta reviews remain pending.

## Lean source inspection and coverage

Repository: https://github.com/Quantyra/connes-rigidity-lean
Tag: `v0.1.1-obstruction`
Exact peeled SHA: `c1e6dfb7347261336714e57de86e6f25c7627461`.

`git ls-remote` confirmed the tag target. A private, no-checkout clone was used for `git show <SHA>:<module-path>` source inspection. No Lean source was modified and **no local Lean build was run**. The independent Lean auditor verified historical full CI run [31303253077](https://github.com/Quantyra/connes-rigidity-lean/actions/runs/31303253077), job 93219377213, at the exact anchor: 3188 jobs including the root and cited targets, with source-hole and register checks. This historical verification does not supply the pending fresh declaration-level kernel evidence.

| Claim / scope | Coverage | Exact module and declaration at the pinned SHA | Limitation |
|---|---|---|---|
| Concrete Nielsen image situation | Classical import; not constructed in Lean | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_lands_in_bad_leg` | Custom axiom supplying a nonempty semantic situation; no concrete spatial tensor product, crossed product or range construction |
| Containment with nonzero unit supplies a condition-(1) witness | Existing semantic Lean proof; current build audit pending | `ConnesRigidity.Ioana.OperatorAlgebra.IntertwiningConditionOne`: `intertwinesIntoConditionOne_of_le` | Supported-algebra interface; not a full proof of all equivalent Popa criteria |
| Supplied containment blocks hypothesis (2) | Existing semantic Lean proof; current build audit pending | `ConnesRigidity.NielsenThetaBlock`: `image_subseteq_M1_LH_blocks_ioana82_hyp2`, `nielsenTheta_blocks_ioana82_hyp2` | Both semantic non-intertwinings are required; no full Ioana theorem formalization |
| Paper-specific imported situation has failed hypothesis (2) | Lean-partial analytic coverage; existing conditional semantic proof | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_blocks_ioana82_hyp2` | Existential semantic situation obtained from the classical import |
| This application does not license rigid output | Lean-partial analytic coverage; existing conditional semantic proof | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_no_rigid_output_licensed_by_hyp2` | Licensing is defined as `hyp2.holds` AND `Nonempty (IoanaRigidOutput G H)`. The record contains a `Unit` carrier and a `True` injectivity field: placeholder data, not constructed group homomorphisms or actual injectivity. Non-licensing is a direct definitional consequence of semantic hypothesis-(2) failure, not a formalization of Ioana's conclusion or nonexistence of group morphisms |
| Theorem 8.2's corrected input/conclusions; Section 9 setup; Nielsen Section 21 response | Literature comparison, not a new theorem or claimed Lean formalization | Primary sources at the recorded page/hash anchors | No claim that every possible extension or alternative route fails |

The source-inspected bridge uses the supported algebra's nonzero local unit for both projections and the partial isometry. The manuscript's unital analytic case uses 1. The main paper-specific exports are existential statements about an imported semantic situation, not constructions of the analytic objects. The recorded historical axiom profile is the one classical import plus `propext`, `Classical.choice`, and `Quot.sound`; independent verification of that closure is pending. No new theorem or Lean code was introduced.

## Author repair provenance — 28 October 2026

This repair follows independent reviews of preserved commit `7ee23d1dc88f435725cfc20e576d49a5d30a58a2`: proof-adversarial REVISE (M1), non-claims PASS with two minors, and package/metadata PASS. Those verdicts apply to the old candidate only. Subsequent independent rechecks resolved the findings as recorded below; final artifact delta reviews and fresh kernel verification remain pending. No release approval is claimed.

M1: abstract, Section 6, declaration table and coverage row now explicitly distinguish the `Unit`/`True` placeholder and definitional licensing from the classical obstruction and Ioana's conclusion. L1: scope separates obtaining a morphism from Nielsen's subsequent injectivity argument. L2: the long-report conclusion now says “does not go through” for this application; historical filenames are retained. N1: the local analytic witness target is consistently B. N2: both-target citation adds Nielsen p.24 Case (II) and p.27. N4: the existing unit witness explicitly explains why right-target non-intertwining is false here. Non-claims minor 2: the obsolete bridge entry has a dated superseded notice and current-coverage link, with historical text preserved.

N3: the parent checked the [official Annals page](https://annals.math.princeton.edu/2006/163-3/p03) and [official PDF](https://annals.math.princeton.edu/wp-content/uploads/annals-v163-n3-p03.pdf), confirming 163 (2006), 809–899, DOI 10.4007/annals.2006.163.809. The correct bibliography is retained; Ioana Theorem 1.3.1 remains the direct criterion citation and Popa remains “see also”.

Private author receipts and prior candidate evidence are preserved outside the public repository. The new PDF and ZIP replace only the working candidate paths, with old bytes preserved in Git. The rebuilt source bundle is checked against LF-normalized Git source bytes, then built in a fresh directory and compared page-by-page for text and pixels. No Lean or cloud commands were run by the author.

## Independent gate — prepared artifacts

These are recorded independent verdicts, not author signoff of successor bytes.

| Role / check | Recorded verdict | Scope and remaining work |
|---|---|---|
| Proof-adversarial | PASS at `bdbb133e0accf4754da419aa8341ee1b1f3be844` | Earlier placeholder finding and companion licensing qualification resolved; final artifact delta review pending |
| Non-claims | PASS at `8eb09837d2c29d932d91b2b712f1008da4f7cb6b` | Both earlier minors resolved; subsequent companion qualification and final artifact delta review pending |
| Package/metadata | PASS at `bdbb133e0accf4754da419aa8341ee1b1f3be844` | Independent four-member ZIP rebuild matched all six pages in text and pixels; final artifact delta review pending |
| Lean source-to-paper comparison | PASS at `bdbb133e0accf4754da419aa8341ee1b1f3be844` | Semantic interface, classical import, placeholder and definitional licensing limits confirmed; final delta review pending |
| Historical exact-anchor build | Independently verified at `c1e6dfb7347261336714e57de86e6f25c7627461` | Historical full build and source/register checks; not a fresh kernel audit |
| Lean/build/audit final gate | REVISE; fresh GCP kernel evidence pending | Earlier attempt stopped during setup before any Lean job; fresh declaration-level type/proof/axiom evidence and independent acceptance remain required |
| Final artifact delta reviews | PENDING | Exact diff, regenerated PDF/TeX/ZIP identities, metadata and build-provenance assertions require independent checks |

The prepared artifact delta removes transient review wording from the manuscript and attributes historical verification without claiming a fresh build. Mathematical claims, citations, Lean anchor and qualifications are unchanged. Author typesetting and bundle checks do not confer reviewer PASS on these new bytes.

Aggregate: **not approved for public freeze**. Version production is already authorized; ordinary GitHub release remains subject to the required publication gates, without an additional human-approval prerequisite. ArXiv submission and outreach require separate human approval. No push, tag, release, upload or outreach occurred in this preparation. Later accepted gate evidence and status can be recorded without changing the manuscript artifacts.
