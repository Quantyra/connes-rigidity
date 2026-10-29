# Kernel and audit provenance — v0.1.3-report

Date: 2026-10-28 Hawaii (acceptance 2026-10-29 03:30 UTC). Independent Lean/build/audit PASS applies to science `9aba11a39d6fba5886f0c1cbd73408290b15339e`. Targeted independent Lean/public-verification review records PASS at `896c1c9`; final status-only carryforward requires root exact-delta inspection and authorization before delivery. See the [verification record](verification-v0.1.3.md) for review scopes and unchanged analytic coverage.

## Exact source and toolchain

Canonical repository: https://github.com/Quantyra/connes-rigidity-lean

Tag `v0.1.1-obstruction` (annotated object `56b671831f026d21bfa50c7c6d85c9a0205bb2f4`) resolves to `c1e6dfb7347261336714e57de86e6f25c7627461`. All 46 corrected source archive members equal the pinned Git blobs byte-for-byte. The older transport archive did not meet that literal-byte condition; its failed-run receipt is preserved and is not evidence for this build.

Toolchain pin: `leanprover/lean4:v4.32.2`. Actual captured version:

```text
Lean (version 4.32.2, x86_64-unknown-linux-gnu, commit f3b06c705e6c85f5314019d5d3baab0fec5b580c, Release)
```

| Dependency | Pinned Git revision |
|---|---|
| mathlib | `905b95818eb32af7874a58b427f50c1711a5e96c` |
| plausible | `e12c1910fe855cbfc38803cd4e55543906d5fa62` |
| LeanSearchClient | `c5d5b8fe6e5158def25cd28eb94e4141ad97c843` |
| importGraph | `7e9612bf0b9ee66db3cb5b9988a35afc706f5a12` |
| proofwidgets | `6e311e2a844da9b2cc3971187df2fe0066947b93` |
| aesop | `a7dbf0c63b694e47f425f3dcddbc0e178bb432d3` |
| Qq | `38d591e778f100aec9762bb582f9c7f55f50e9dc` |
| batteries | `023ce7d62a0531e22a5331e20b587817a80d49ff` |
| Cli | `88679d088c9720c27ebdf2ba4dafe17341747f94` |

All nine captured revision outputs match these canonical manifest pins; tracked-file status outputs before and after the run are empty. Generated/cache files are excluded by those checks. Canonical cache acquisition succeeded, and the target log explicitly builds all 15 owned modules. This is a fresh target build with dependencies/cache, not a fresh full-project build.

## Accepted output and evidence identities

The build, source-hole check, register check and `lake env lean Audit.lean` each exited 0. Selected verbatim output:

```text
Build completed successfully (2980 jobs).
PASS: no sorry/admit in ConnesRigidity sources
PASS: all opaque/axiom names registered (14)
```

2980 is Lake’s total target-job count, not the number of freshly compiled sources. The fresh target is `ConnesRigidity.NielsenThetaImage`; historical full-project CI run [31303253077](https://github.com/Quantyra/connes-rigidity-lean/actions/runs/31303253077), job 93219377213, reported 3188 jobs and remains separate supporting evidence.

| Evidence | SHA256 |
|---|---|
| Canonical source archive | `66051dd6abc746b4da339d0c5989ed20ac74e68e5cc35c94eb9c70ce1f3ed0fd` |
| Canonical source manifest | `afbcd202f23dde9e28c0b82dcd178165b0cb4008d12c36568d9c0e632915c78f` |
| Audit.lean (twelve check/print/axiom triplets) | `60a204a5df8a3c9a68fcc121c957cb131cb71e30791593ab515527f153f70354` |
| Source/toolchain/dependency identity record | `13aa79a9a8042d158d6c5ac8dd10db859aa65f362ce0f7617c800b7334573e19` |
| Retained raw terminal archive | `237e6901988080844f7d2298ae607fe649a5309e06d7654a4187473e9ebadb85` |
| Raw kernel stdout (includes proof terms) | `24bb699f315f60473de738ec311580eb38743af46873f9d7621f296e8bd1d0cb` |
| Raw build stdout | `b63a5b3a0ea8387449fe36a92d5b7277eeb3a4d8307db07643096cd2d15de3f3` |
| Raw source-hole check stdout | `3fd2f746f6ec9c3e37024d11d46d24bf72b2997e453a1f7ca3ff9e551690f157` |
| Raw register check stdout | `f833c384249ec0f9e005201ef9a842dbb36c4ac203005e9a69c9d2dcb60807a6` |
| Retained public-safe excerpt file used below | `39d7fc2e8111b6a63805ad14f6af35d99d085ffd59baa648c78c3ad5910ad9d2` |
| Independent bounded-role acceptance report | `82e84d7bcdf1a394e384efdb28baa0d0cb73818bed8da47b586333eccc29bde4` |

These are identities of retained evidence, not public download links or signed third-party attestations. Raw infrastructure transcripts and the private acceptance report are not published. The toolchain archive hash `5f2069e6f5db73780f374ccb49ce8ea649aa20a0cebf0116816744c999ce72aa` (563991635 bytes) was checked by captured execution before extraction; the reviewer did not independently rehash a retained executable. The sealed runner checks the same canonical source manifest before and after compilation. No separately generated post-source manifest or retained full dependency-source/cache binary payload is claimed. Operational custody and closure were accepted separately, on retained observations.

## Declaration profiles and interpretation

The reviewer read all twelve actual types, printed bodies and axiom lists. No list contains `sorryAx`. The first nine declarations below have only `propext`, `Classical.choice` and `Quot.sound`; the last three additionally depend on the registered `nielsen_theta_by_construction_lands_in_bad_leg` axiom (which includes itself in its own list). The 14-name register inventory is not a per-theorem dependency list.

The supported-algebra bridge assumes containment and a nonzero local unit; its witness uses that unit. It is not full Popa equivalence or a formalization of analytic normality. Supplied semantic packages do not construct concrete Theta, spatial tensor products, crossed products or the concrete range. The classical axiom supplies a nonempty semantic situation. The two main exports are existential statements about that imported situation.

The older `nielsenTheta_no_rigid_licensed_by_hyp2` export explicitly requires the additional `licenses` equivalence premise shown below; its conclusion cannot be cited without that premise or as Ioana’s conclusion. `rigidOutputLicensedByHyp2` is defined as `hyp2.holds` AND `Nonempty (IoanaRigidOutput G H)`. That output record contains `Unit`/`True` placeholders, not actual group homomorphism or injectivity data. Its non-licensing is definitional. No full Ioana theorem, morphism-nonexistence, global Connes verdict or exclusion of all alternative routes follows.

The following is the reviewer’s public-safe excerpt: exact type and axiom lines, with proof bodies omitted. It is not the complete raw stdout. The last two pretty-printed existential types elide the binder type; inspected source and proof terms identify `S : NielsenThetaImageSituation G H Φ`. The elision is preserved.

```text
Exact source c1e6dfb7347261336714e57de86e6f25c7627461; Lean 4.32.2.
Extracted verbatim #check types and #print axioms lists. This excerpt omits proof terms, has its own hash, and is not the raw stdout file.

ConnesRigidity.Ioana.intertwinesIntoConditionOne_of_le.{u} {M : Type u} [CStarAlgebra.{u} M] [PartialOrder.{u} M]
  (Q B : ConnesRigidity.Ioana.SupportedWStarSubalgebra.{u} M)
  (hQ0 : Ne.{u + 1} (ConnesRigidity.Ioana.SupportedWStarSubalgebra.unit.{u} Q) 0)
  (hQB :
    LE.le.{u}
      (ConnesRigidity.Ioana.ClosedNonUnitalStarSubalgebra.toNonUnitalStarSubalgebra.{u}
        (ConnesRigidity.Ioana.SupportedWStarSubalgebra.carrier.{u} Q))
      (ConnesRigidity.Ioana.ClosedNonUnitalStarSubalgebra.toNonUnitalStarSubalgebra.{u}
        (ConnesRigidity.Ioana.SupportedWStarSubalgebra.carrier.{u} B))) :
  ConnesRigidity.Ioana.IntertwinesIntoConditionOne.{u} Q B
'ConnesRigidity.Ioana.intertwinesIntoConditionOne_of_le' depends on axioms: [propext,
 Classical.choice.{u},
 Quot.sound.{u}]

ConnesRigidity.Ioana.not_doesNotIntertwineIntoConditionOne_of_le.{u} {M : Type u} [CStarAlgebra.{u} M]
  [PartialOrder.{u} M] (Q B : ConnesRigidity.Ioana.SupportedWStarSubalgebra.{u} M)
  (hQ0 : Ne.{u + 1} (ConnesRigidity.Ioana.SupportedWStarSubalgebra.unit.{u} Q) 0)
  (hQB :
    LE.le.{u}
      (ConnesRigidity.Ioana.ClosedNonUnitalStarSubalgebra.toNonUnitalStarSubalgebra.{u}
        (ConnesRigidity.Ioana.SupportedWStarSubalgebra.carrier.{u} Q))
      (ConnesRigidity.Ioana.ClosedNonUnitalStarSubalgebra.toNonUnitalStarSubalgebra.{u}
        (ConnesRigidity.Ioana.SupportedWStarSubalgebra.carrier.{u} B))) :
  ¬ConnesRigidity.Ioana.DoesNotIntertwineIntoConditionOne.{u} Q B
'ConnesRigidity.Ioana.not_doesNotIntertwineIntoConditionOne_of_le' depends on axioms: [propext,
 Classical.choice.{u},
 Quot.sound.{u}]

image_subseteq_M1_LH_blocks_ioana82_hyp2.{u_1} {M : Type u_1} [CStarAlgebra.{u_1} M] [PartialOrder.{u_1} M]
  (h : Ioana82Hyp2.{u_1} M) (hc : Ioana82Hyp2.imageSubseteqRightLeg.{u_1} h) : ¬Ioana82Hyp2.holds.{u_1} h
'image_subseteq_M1_LH_blocks_ioana82_hyp2' depends on axioms: [propext, Classical.choice.{u}, Quot.sound.{u}]

nielsenTheta_blocks_ioana82_hyp2.{u_1} {M : Type u_1} [CStarAlgebra.{u_1} M] [PartialOrder.{u_1} M]
  {G H : DiscreteGroupLabel} (S : NielsenThetaSetup.{u_1} M G H) :
  ¬Ioana82Hyp2.holds.{u_1} (NielsenThetaSetup.hyp2.{u_1} S)
'nielsenTheta_blocks_ioana82_hyp2' depends on axioms: [propext, Classical.choice.{u}, Quot.sound.{u}]

Ioana82Hyp2.ofImageContainedInRightLeg_blocks_hyp2.{u_1} {M : Type u_1} [CStarAlgebra.{u_1} M] [PartialOrder.{u_1} M]
  (imageAlgebra rightBadLeg leftBadLeg : ConnesRigidity.Ioana.SupportedWStarSubalgebra.{u_1} M)
  (h0 : Ne.{u_1 + 1} (ConnesRigidity.Ioana.SupportedWStarSubalgebra.unit.{u_1} imageAlgebra) 0)
  (hle :
    LE.le.{u_1}
      (ConnesRigidity.Ioana.ClosedNonUnitalStarSubalgebra.toNonUnitalStarSubalgebra.{u_1}
        (ConnesRigidity.Ioana.SupportedWStarSubalgebra.carrier.{u_1} imageAlgebra))
      (ConnesRigidity.Ioana.ClosedNonUnitalStarSubalgebra.toNonUnitalStarSubalgebra.{u_1}
        (ConnesRigidity.Ioana.SupportedWStarSubalgebra.carrier.{u_1} rightBadLeg))) :
  ¬Ioana82Hyp2.holds.{u_1} (Ioana82Hyp2.ofImageContainedInRightLeg.{u_1} imageAlgebra rightBadLeg leftBadLeg h0 hle)
'Ioana82Hyp2.ofImageContainedInRightLeg_blocks_hyp2' depends on axioms: [propext, Classical.choice.{u}, Quot.sound.{u}]

NielsenThetaImagePackage.image_subseteq_holds.{u_1} {M : Type u_1} [CStarAlgebra.{u_1} M] [PartialOrder.{u_1} M]
  {G H : DiscreteGroupLabel} (P : NielsenThetaImagePackage.{u_1} M G H) :
  Ioana82Hyp2.imageSubseteqRightLeg.{u_1} (NielsenThetaSetup.hyp2.{u_1} (NielsenThetaImagePackage.toSetup.{u_1} P))
'NielsenThetaImagePackage.image_subseteq_holds' depends on axioms: [propext, Classical.choice.{u}, Quot.sound.{u}]

NielsenThetaImagePackage.blocks_ioana82_hyp2.{u_1} {M : Type u_1} [CStarAlgebra.{u_1} M] [PartialOrder.{u_1} M]
  {G H : DiscreteGroupLabel} (P : NielsenThetaImagePackage.{u_1} M G H) :
  ¬Ioana82Hyp2.holds.{u_1} (NielsenThetaSetup.hyp2.{u_1} (NielsenThetaImagePackage.toSetup.{u_1} P))
'NielsenThetaImagePackage.blocks_ioana82_hyp2' depends on axioms: [propext, Classical.choice.{u}, Quot.sound.{u}]

nielsenTheta_no_rigid_licensed_by_hyp2.{u_1} {M : Type u_1} [CStarAlgebra.{u_1} M] [PartialOrder.{u_1} M]
  {G H : DiscreteGroupLabel} (S : NielsenThetaSetup.{u_1} M G H)
  (licenses : Ioana82Hyp2.holds.{u_1} (NielsenThetaSetup.hyp2.{u_1} S) ↔ Nonempty.{1} (IoanaRigidOutput G H)) :
  ¬Nonempty.{1} (IoanaRigidOutput G H)
'nielsenTheta_no_rigid_licensed_by_hyp2' depends on axioms: [propext, Classical.choice.{u}, Quot.sound.{u}]

NielsenThetaImageSituation.rigidOutputLicensedByHyp2 {G H : DiscreteGroupLabel} {Φ : FactorIsoAssumption G H}
  (S : NielsenThetaImageSituation G H Φ) : Prop
'NielsenThetaImageSituation.rigidOutputLicensedByHyp2' depends on axioms: [propext,
 Classical.choice.{u},
 Quot.sound.{u}]

nielsen_theta_by_construction_lands_in_bad_leg (G H : DiscreteGroupLabel) (Φ : FactorIsoAssumption G H) :
  Nonempty.{2} (NielsenThetaImageSituation G H Φ)
'nielsen_theta_by_construction_lands_in_bad_leg' depends on axioms: [nielsen_theta_by_construction_lands_in_bad_leg,
 propext,
 Classical.choice.{u},
 Quot.sound.{u}]

nielsen_theta_by_construction_blocks_ioana82_hyp2 (G H : DiscreteGroupLabel) (Φ : FactorIsoAssumption G H) :
  ∃ S, S.hyp2Fails
'nielsen_theta_by_construction_blocks_ioana82_hyp2' depends on axioms: [nielsen_theta_by_construction_lands_in_bad_leg,
 propext,
 Classical.choice.{u},
 Quot.sound.{u}]

nielsen_theta_by_construction_no_rigid_output_licensed_by_hyp2 (G H : DiscreteGroupLabel)
  (Φ : FactorIsoAssumption G H) : ∃ S, ¬S.rigidOutputLicensedByHyp2
'nielsen_theta_by_construction_no_rigid_output_licensed_by_hyp2' depends on axioms: [nielsen_theta_by_construction_lands_in_bad_leg,
 propext,
 Classical.choice.{u},
 Quot.sound.{u}]
```
