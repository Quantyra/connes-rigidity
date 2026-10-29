# Verification record — prepared v0.1.3-report

Date: 2026-10-28. **Prepared, unreleased version; publication gate pending.** The three final manuscript roles and the independent Lean/build/audit role record PASS at science `9aba11a39d6fba5886f0c1cbd73408290b15339e`. The documentation-only successor still requires targeted independent Lean review of its new evidence prose and the parent metadata/hash/diff check before release. This record does not assert aggregate approval or a performed release.

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

Prepared-artifact check (28 October 2026, successor to `bdbb133`): both the manuscript build and a fresh four-member ZIP extraction used `tectonic --keep-logs --only-cached nielsen-ioana-theta-reductio-arxiv.tex` in separate private directories and exited 0. All six pages matched in extracted text and 1.5x RGB pixels; all six were visually inspected. No unresolved references/citations, box warnings or missing-character diagnostics were found. The Fontconfig diagnostic above recurred in both builds. The independent package reviewer subsequently passed these exact artifacts at `9aba11a39d6fba5886f0c1cbd73408290b15339e`, after a fresh ZIP build, six-page text/pixel comparison and visual inspection. Its timestamp-dependent rebuilt PDF differed in binary hash; the reviewed release PDF remains unchanged.

## Lean source inspection and coverage

Repository: https://github.com/Quantyra/connes-rigidity-lean
Tag: `v0.1.1-obstruction`
Exact peeled SHA: `c1e6dfb7347261336714e57de86e6f25c7627461`.

`git ls-remote` confirmed the tag target. A private, no-checkout clone was used for `git show <SHA>:<module-path>` source inspection. No Lean source was modified and **no local Lean build was run**. The independent Lean auditor verified historical full CI run [31303253077](https://github.com/Quantyra/connes-rigidity-lean/actions/runs/31303253077), job 93219377213, at the exact anchor: 3188 jobs including the root and cited targets, with source-hole and register checks. This remains historical full-project support, separate from the fresh targeted verification below.

| Claim / scope | Coverage | Exact module and declaration at the pinned SHA | Limitation |
|---|---|---|---|
| Concrete Nielsen image situation | Classical import; not constructed in Lean | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_lands_in_bad_leg` | Custom axiom supplying a nonempty semantic situation; no concrete spatial tensor product, crossed product or range construction |
| Containment with nonzero unit supplies a condition-(1) witness | Existing semantic Lean proof; fresh target audit accepted | `ConnesRigidity.Ioana.OperatorAlgebra.IntertwiningConditionOne`: `intertwinesIntoConditionOne_of_le` | Supported-algebra interface; not a full proof of all equivalent Popa criteria |
| Supplied containment blocks hypothesis (2) | Existing semantic Lean proof; fresh target audit accepted | `ConnesRigidity.NielsenThetaBlock`: `image_subseteq_M1_LH_blocks_ioana82_hyp2`, `nielsenTheta_blocks_ioana82_hyp2` | Both semantic non-intertwinings are required; no full Ioana theorem formalization |
| Paper-specific imported situation has failed hypothesis (2) | Lean-partial analytic coverage; existing conditional semantic proof | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_blocks_ioana82_hyp2` | Existential semantic situation obtained from the classical import |
| This application does not license rigid output | Lean-partial analytic coverage; existing conditional semantic proof | `ConnesRigidity.NielsenThetaImage`: `nielsen_theta_by_construction_no_rigid_output_licensed_by_hyp2` | Licensing is defined as `hyp2.holds` AND `Nonempty (IoanaRigidOutput G H)`. The record contains a `Unit` carrier and a `True` injectivity field: placeholder data, not constructed group homomorphisms or actual injectivity. Non-licensing is a direct definitional consequence of semantic hypothesis-(2) failure, not a formalization of Ioana's conclusion or nonexistence of group morphisms |
| Theorem 8.2's corrected input/conclusions; Section 9 setup; Nielsen Section 21 response | Literature comparison, not a new theorem or claimed Lean formalization | Primary sources at the recorded page/hash anchors | No claim that every possible extension or alternative route fails |

The source-inspected bridge uses the supported algebra's nonzero local unit for both projections and the partial isometry. The manuscript's unital analytic case uses 1. The main paper-specific exports are existential statements about an imported semantic situation, not constructions of the analytic objects. The fresh kernel audit directly verified the two main existential exports: each depends on the registered classical import `nielsen_theta_by_construction_lands_in_bad_leg` plus `propext`, `Classical.choice`, and `Quot.sound`. The audited generic semantic declarations have only those three standard dependencies. The [kernel appendix](kernel-audit-v0.1.3.md) gives all twelve actual profiles and the older export’s additional licensing-equivalence premise. No new theorem or Lean code was introduced.

## Fresh targeted Lean verification — 28 October 2026 Hawaii

Independent fourth-role acceptance completed on 2026-10-29 at 03:30 UTC (28 October Hawaii) at the unchanged science artifact commit `9aba11a39d6fba5886f0c1cbd73408290b15339e`. The corrected canonical source archive matches all 46 Git blobs literally at Lean `c1e6dfb7347261336714e57de86e6f25c7627461` / `v0.1.1-obstruction`. Lean is `leanprover/lean4:v4.32.2`; mathlib is `905b95818eb32af7874a58b427f50c1711a5e96c`. All nine dependency pins, exact evidence identities and accepted output excerpts appear in the [kernel/audit provenance appendix](kernel-audit-v0.1.3.md).

The accepted commands each have recorded numeric exit 0:

```text
lake build ConnesRigidity.NielsenThetaImage
bash scripts/check_no_sorry.sh
bash scripts/check_axiom_register.sh
lake env lean Audit.lean
```

The fresh build covers the documented target and its 15 owned modules, using pinned dependencies and canonical cache. Lake reports 2980 target jobs; this is not a count of freshly compiled source files or a fresh full-project build. The source lexical check found no `sorry`/`admit`; the register check accounted for all 14 opaque/axiom names. Independently reviewed raw `#check`, `#print` and `#print axioms` output covers twelve declarations, with no `sorryAx`. The broader registered inventory is distinct from each declaration’s actual dependencies. No analytic coverage is expanded by this audit.

The independent reviewer separately accepted terminal custody and operational closure. Captured execution verifies the toolchain archive hash and checks the same canonical source manifest before and after compilation; no independent retained executable rehash, retained full dependency/cache payload, or separately generated post-source manifest is claimed. Historical setup/cache failures remain failures and do not support this success. Raw infrastructure records remain private.

## Author repair provenance — 28 October 2026

This repair follows independent reviews of preserved commit `7ee23d1dc88f435725cfc20e576d49a5d30a58a2`: proof-adversarial REVISE (M1), non-claims PASS with two minors, and package/metadata PASS. Those verdicts apply to the old candidate only. Subsequent independent rechecks and the final artifact reviews resolved the findings as recorded below; fresh kernel acceptance is now recorded separately above. No release approval is claimed.

M1: abstract, Section 6, declaration table and coverage row now explicitly distinguish the `Unit`/`True` placeholder and definitional licensing from the classical obstruction and Ioana's conclusion. L1: scope separates obtaining a morphism from Nielsen's subsequent injectivity argument. L2: the long-report conclusion now says “does not go through” for this application; historical filenames are retained. N1: the local analytic witness target is consistently B. N2: both-target citation adds Nielsen p.24 Case (II) and p.27. N4: the existing unit witness explicitly explains why right-target non-intertwining is false here. Non-claims minor 2: the obsolete bridge entry has a dated superseded notice and current-coverage link, with historical text preserved.

N3: the parent checked the [official Annals page](https://annals.math.princeton.edu/2006/163-3/p03) and [official PDF](https://annals.math.princeton.edu/wp-content/uploads/annals-v163-n3-p03.pdf), confirming 163 (2006), 809–899, DOI 10.4007/annals.2006.163.809. The correct bibliography is retained; Ioana Theorem 1.3.1 remains the direct criterion citation and Popa remains “see also”.

Private author receipts and prior candidate evidence are preserved outside the public repository. The new PDF and ZIP replace only the working candidate paths, with old bytes preserved in Git. The rebuilt source bundle is checked against LF-normalized Git source bytes, then built in a fresh directory and compared page-by-page for text and pixels. No Lean or cloud commands were run by the author.

## Independent gate — exact reviewed artifacts and conditional successor

The four role verdicts below refer to science `9aba11a39d6fba5886f0c1cbd73408290b15339e`, with the fixed PDF/TeX/ZIP hashes in the [manifest](artifact-manifest-v0.1.3.json). They do not assert review of an unseen successor commit.

| Role / check | Recorded verdict | Scope |
|---|---|---|
| Proof-adversarial | PASS at `9aba11a` | Final manuscript delta; mathematics, citations and coverage unchanged |
| Non-claims | PASS at `9aba11a` | Final text/artifact delta; classical import, placeholder/definitional limits and bounded conclusions preserved |
| Package/metadata | PASS at `9aba11a` | Exact Git/artifact/member bytes; independent ZIP rebuild, six-page text/pixel and visual checks |
| Lean/build/audit | PASS at `9aba11a` | Corrected canonical inputs, fresh target build, twelve raw kernel profiles, statement match and separately verified operational closure |
| Historical exact-anchor build | Independently verified | Full 3188-job CI at `c1e6dfb`; distinct historical support |
| Successor evidence prose and exact diff | PENDING targeted independent review | New verification/axiom assertions require Lean-role acceptance; parent metadata/hash/link/scope checks and aggregate decision remain required |

The original three manuscript PASSes permit conditional documentation-only carryforward after fresh independent Lean acceptance. This successor records that acceptance and preserves the reviewed PDF, TeX, ZIP and every bundle member. Its permitted delta is factual evidence, gate/status and publication metadata only; mathematical text, source pins, imports, declarations, non-claims and substantive coverage remain unchanged. Exact successor identity and diff checks belong in the parent packet. The Lean PASS likewise requires targeted review of this new public prose before release; carryforward is not approval of unseen bytes.

Aggregate: **publication gate pending**. Version production is authorized; root will authorize release only after the targeted checks. No push, tag, release, upload, new version DOI or outreach is asserted here. ArXiv submission and outreach require separate human approval. The earlier failed-run REVISE remains preserved and is superseded only for the fresh-evidence gap by the independently accepted corrected run.
