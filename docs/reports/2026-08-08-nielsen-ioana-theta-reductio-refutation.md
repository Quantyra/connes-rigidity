# Hypothesis failure for Ioana's Theorem 8.2 under a twisted comultiplication

Long-form companion to the existing paper.

**Quantyra Inc. — Jenny research lane**
**Date:** 2026-10-28 (revises the 2026-08-08 report)
**Authors:** Daniel Eric Fredriksen (Quantyra); orchestrated audit with machine-checked Lean core
**Status:** v0.1.3-report local review candidate; four-role gate pending; no new version DOI
**Lean artifact:** https://github.com/Quantyra/connes-rigidity-lean (tag `v0.1.1-obstruction`)
**Science repo:** https://github.com/Quantyra/connes-rigidity (proposed version `v0.1.3-report`; not tagged)

---


## Revision note — 28 October 2026

The previous short manuscript overstated Ioana Theorem 8.2: its general input is a *-homomorphism, not an assumed unital one. In the torsion-free case the conclusion includes unitality, a character, a homomorphism into the product group and unitary-conjugacy data; it does not state injectivity of both coordinates. In the general case there is a finite-index subgroup and a one-to-one map into the product group, normalizing a finite subgroup K, with multiplication defect in K, and a nonzero-corner formula involving finitely many Cartan normalizers. See JAMS pp.1207–1208 for the full statement. Nielsen's desired injectivity of the second coordinate is a subsequent claim. Our particular map is unital. The bounded obstruction and published Lean anchors are unchanged.

### Response to the 49-page source

The artifact inspected on 2026-10-28 has SHA256 `BC201CC37F897EEEDA2446D1926AB7945405E5A96CF27176CA0E4157476D324E`; its title page still says August 2026. Definition 8 (p.21) retains the same formula and ambient tensor product. Remark 11 (p.23; archived Remark 21) and Lemma 14 (pp.26–27) acknowledge the right mixed containment. Nielsen names both mixed targets and claims exclusion of the right one despite that containment; it is inaccurate to characterize the problem as simply omitting that target.

For a unital inclusion P ⊆ Q, Ioana's Theorem 1.3.1(1), JAMS p.1184, permits both projections to be 1, the inclusion homomorphism, and the nonzero partial isometry v = 1. This is the existing containment-to-intertwining witness. The corner formulation therefore does not make containment irrelevant.

| Target | Distinction required |
|---|---|
| Single factors A_G ⊗ 1 and 1 ⊗ A_H | Excluding these does not exclude either mixed target. |
| Left mixed target L(G) ⊗̄ A_H | The first-factor Cartan argument addresses this target. |
| Right mixed target A_G ⊗̄ L(H) | Contains the whole image, including the Cartan image L∞(X) ⊗ 1. |

The Cartan image is asymmetric. Lemma 14's asserted symmetric exclusion of the right target does not overcome the unit witness. Both mixed-target non-intertwinings are mandatory in Theorem 8.2(2).

Section 21, pp.37–39, offers three defenses:

1. **Remark 13 (pp.37–38):** deformation fixity of the group-unitary image and the stated Cartan image, uniform in Φ. Even granting these properties, they are compatible with containment in the right mixed target.
2. **Remark 14 (p.38):** property-(T) spectral gap, described as excluding intertwining into a single tensor factor. That does not exclude a target containing the entire first crossed product and the second group algebra.
3. **Remark 15 (p.38):** genuine involvement of both factors, identified with the rigid case. A mixed-target alternative can involve both factors; this is not a verification of both conjuncts of (2).

Ioana's Theorem C, JAMS p.1179, includes both mixed targets in alternative (2), with its own same-factor and torsion-free setting. Invoking the internal proof of Theorem 8.2 also does not discard its premises: it starts under (1)–(2), uses (2) in deriving (8.b), and then applies Theorem 6.1 (pp.1208–1209). The result remains non-licensing by this application, not nonexistence of group morphisms or proof that rigid output could never hold for special inputs.

### The separate Section 9 appeal: hypothesis comparison

Current Remark 11 invokes Theorem 9.1, Lemma 9.2(4), Case (5), and the full Section 9 pipeline. This appeal was already in archived Remark 21; it is not a new October repair. Ioana does handle a mixed case there. However, Theorem 9.1 starts with a crossed-product isomorphism N = C ⋊ Λ ≅ qMq, with M the Bernoulli crossed product (JAMS p.1213), and transports comultiplication through that isomorphism before Lemma 9.2 and the cases (pp.1214–1217). An isomorphism L(G) ≅ L(H) of group factors alone does not supply that setup. The construction of injective Θ is not a construction of the required crossed-product isomorphism. The reviewed appeal supplies no hypothesis-by-hypothesis replacement. This is a source-based hypothesis comparison, not a new theorem excluding every extension or alternate route.

The [source identity manifest](../sources/nielsen-2026-10-28-identity.md) preserves both Nielsen pins and precise page anchors. No raw new third-party PDF is included in the revision package.

## 1. Executive summary

We consider J. L. Nielsen’s argument that applies **Ioana’s Theorem 8.2** (J. Amer. Math. Soc. 24 (2011)) to a **twisted comultiplication**

\[
\Theta(f u_g) = f u_g \otimes \Phi(u_g)
\]

built from an assumed group-factor isomorphism \(\Phi\colon L(G)\to L(H)\), in order to obtain injective group morphisms and run a reductio against claimed counterexamples to Connes’ rigidity conjecture (and, in Nielsen Part II, to prove the conjecture itself).

**Result (bounded):** That application of Ioana’s Theorem 8.2 **does not go through**. Hypothesis (2) of Theorem 8.2 fails for this \(\Theta\), because by construction

\[
\Theta(A_G)\subseteq A_G\,\bar\otimes\, L(H),
\]

which is the forbidden “bad tensor leg” \(M_1\bar\otimes L(\Gamma_2)\) in Ioana’s setup. Therefore Theorem 8.2 does **not** license the rigid-case output under the theorem’s stated qualifications from this map, and the reductio that depends on that output does not start.

This report **does not** claim that Connes’ rigidity conjecture is true or false, and **does not** validate or refute the OpenAI or Zhou counterexample constructions on independent grounds.

---

## 2. Scope and non-claims

### In scope
- Nielsen’s use of \(\Theta\) + Ioana Theorem 8.2 to obtain \(\delta_2\) (the load-bearing step of the reductio).
- Classical pin of Ioana JAMS 2011 and Nielsen NIEWTC.
- Machine-checked packaging of the obstruction logic in Lean 4.

### Out of scope (explicit non-claims)
- Connes rigidity true or false.
- Validity or invalidity of OpenAI `ten-proofs` / Zhou arXiv:2608.02327 as counterexamples.
- Full formalization of Ioana (2011) or of group von Neumann algebras \(L(\Gamma)\) in mathlib.
- Nielsen’s separate Lean code-internal ICC / property-(T) objections (not required for this gate).

---

## 3. Background

**Connes’ rigidity conjecture (ICC + property (T) form).**
If \(G,H\) are countable discrete ICC groups with Kazhdan’s property (T) and \(L(G)\cong L(H)\), then \(G\cong H\).

**Nielsen’s reductio hinge.**
Assume \(L(G)\cong L(H)\). Equip \(G\) with a Bernoulli action; form \(A_G=L^\infty(X)\rtimes G\); build \(\Theta\) from \(\Phi\); apply Ioana’s classification to obtain group morphisms; derive a contradiction with extension-class or structural data (Part I), or force \(G\cong H\) in general (Part II).

**Ioana Theorem 8.2 (structure).**
For a *-homomorphism into a tensor product of two Bernoulli crossed products \(M=M_1\bar\otimes M_2\), the rigid/standard conclusion requires non-intertwining hypotheses, including (2):

- \(\theta(N)\nprec_M L(\Gamma_1)\bar\otimes M_2\), and
- \(\theta(N)\nprec_M M_1\bar\otimes L(\Gamma_2)\).

(See Ioana, *J. Amer. Math. Soc.* 24 (2011), Thm. 8.2; DOI [10.1090/S0894-0347-2011-00706-6](https://doi.org/10.1090/S0894-0347-2011-00706-6).)

---

## 4. Argument

1. **Identify setups.** Take Nielsen’s \(\Theta\colon A_G\to A_G\bar\otimes A_H\) as an instance of Ioana’s \(\theta\colon N\to M_1\bar\otimes M_2\) with \(N=A_G\), \(M_1=A_G\), \(M_2=A_H\), \(\Gamma_2=H\).

2. **Containment by definition.**
   \(\Theta(f u_g)=f u_g\otimes\Phi(u_g)\) with \(\Phi(u_g)\in L(H)\) yields
   \(\Theta(A_G)\subseteq A_G\bar\otimes L(H)=M_1\bar\otimes L(\Gamma_2)\).
   Nielsen’s own text records this containment (image in the group-algebra leg).

3. **Hypothesis (2) fails.**
   Containment in \(M_1\bar\otimes L(\Gamma_2)\) implies it is not the case that \(\theta(N)\nprec M_1\bar\otimes L(\Gamma_2)\) (Popa intertwining / \(\prec\) from inclusion of the image). Thus Ioana’s required pair of non-intertwinings in (2) does not hold.

4. **No licensed \(\delta_2\).**
   Without hypothesis (2), Theorem 8.2 does not supply the rigid-case group-morphism conclusion for this \(\Theta\).

5. **Reductio blocked.**
   Steps that need \(\delta_2\) from this Ioana application (Borel–Margulis–Schur–Bockstein chain in Part I; universal Connes argument in Part II that reuses the same \(\Theta\)) do not obtain their input from Theorem 8.2.

---

## 5. Lean artifact

Repository: [Quantyra/connes-rigidity-lean](https://github.com/Quantyra/connes-rigidity-lean)
Release tag: `v0.1.1-obstruction`
Modules: `ConnesRigidity.NielsenThetaImage`, `ConnesRigidity.NielsenThetaBlock`

| Declaration | Content |
|-------------|---------|
| `nielsen_theta_by_construction_lands_in_bad_leg` | **Classical import only:** Nielsen NIEWTC definitional Θ package and by-construction image containment as a semantic situation (not a Lean construction of \(A_G\bar\otimes L(H)\)) |
| `nielsen_theta_by_construction_blocks_ioana82_hyp2` | **Proved:** from that import, Ioana 8.2 hyp (2) fails |
| `nielsen_theta_by_construction_no_rigid_output_licensed_by_hyp2` | **Proved:** rigid output is not licensed by that failed application |
| `intertwinesIntoConditionOne_of_le` | **Proved:** containment + nonzero unit ⇒ condition-(1) intertwiner (Popa bridge not axiomatized) |
| `image_subseteq_M1_LH_blocks_ioana82_hyp2` | **Proved:** semantic containment blocks hyp (2) |

**Axiom profile of main exports:** only
`nielsen_theta_by_construction_lands_in_bad_leg` + standard Lean foundations (`propext`, `Classical.choice`, `Quot.sound`).
The former custom Popa bridge axiom `image_subseteq_M1_LH_negates_niRight` is **removed**.

**Historical verification recipe:** `lake build`, no `sorry`/`admit`, axiom register check. Current independent build/audit is pending; no local Lean build was run for this revision.

**Build pin:** git SHA `c1e6dfb7347261336714e57de86e6f25c7627461` (tag `v0.1.1-obstruction`).

---

## 6. Review

The four independent reviews of **v0.1.3-report are pending**. Historical August PASS records do not approve this revision. The current checklist and public-safe coverage matrix are in [submission-checklist-v0.1.3.md](../publication/submission-checklist-v0.1.3.md) and [verification-v0.1.3.md](../publication/verification-v0.1.3.md). No new Lean build is claimed by this author; the parent coordinator owns the independent Lean audit and final review packet.

Historical planning packets remain the August 7 audit and August 8 closeout/v0.1.1 freeze records. Their approvals, including Dan's historical arXiv approval, are not inherited.

---

## 7. Primary sources

| Source | Pin |
|--------|-----|
| Nielsen, *Connes’ Rigidity Conjecture…* (NIEWTC), Aug 2026 | PDF SHA256 `9529E43EBFF1E38A808397DA0C0FC56CABCB71C41B622FABA54B6B57573D3884` |
| Ioana, JAMS 24 (2011) | DOI 10.1090/S0894-0347-2011-00706-6; PDF SHA256 `0EF129649596FC6BDF36A7ADA3C1972CF1B20FB838D5E560D1FCACCEF21501E3` |
| Zhou, arXiv:2608.02327 (background only) | PDF SHA256 `F66016BB8D65815DB56A50F31A81B9046698CF4045167909D7741FBEF7B22E65` |
| OpenAI ten-proofs (background only) | git `94bc0feb6a9ff12c7d31d6de640a725c9d43d2b6` |

---

## 8. Conclusion

The Nielsen **Ioana+Θ reductio does not go through** as an application of Ioana’s Theorem 8.2: the map \(\Theta\) is built so that a mandatory non-intertwining hypothesis fails.

**Remaining open (by design, out of this report’s success criterion):** whether Connes’ conjecture holds; whether any particular counterexample construction is correct.

---

## 9. Citation

Please cite the Lean software release `v0.1.1-obstruction` and this report path in [Quantyra/connes-rigidity](https://github.com/Quantyra/connes-rigidity):

`docs/reports/2026-08-08-nielsen-ioana-theta-reductio-refutation.md`

**DOIs:**

| Artifact | DOI |
|----------|-----|
| Science report (concept — cite for all versions) | [10.5281/zenodo.21845586](https://doi.org/10.5281/zenodo.21845586) |
| Science report **v0.1.2** (historical PDF deposit) | [10.5281/zenodo.21859653](https://doi.org/10.5281/zenodo.21859653) |
| Science report v0.1.1 (historical zip) | [10.5281/zenodo.21859308](https://doi.org/10.5281/zenodo.21859308) |
| Science report v0.1.0 (historical) | [10.5281/zenodo.21845587](https://doi.org/10.5281/zenodo.21845587) |
| **Candidate PDF v0.1.3** | [local revised PDF](../notes/nielsen-ioana-theta-reductio-arxiv.pdf); no version DOI |
| Lean package (concept — cite for all versions) | [10.5281/zenodo.21845588](https://doi.org/10.5281/zenodo.21845588) |
| Lean **v0.1.1-obstruction** (this version) | [10.5281/zenodo.21859309](https://doi.org/10.5281/zenodo.21859309) |
| Lean v0.1.0-obstruction (historical) | [10.5281/zenodo.21845589](https://doi.org/10.5281/zenodo.21845589) |

**Preferred citation DOIs:** concept DOIs above for “the work”; version DOIs only for their corresponding historical bytes. The candidate has no version DOI.

**License:** Report text CC-BY-4.0 (Quantyra-authored); Lean code Apache-2.0; third-party source PDFs under original rights (pins only).
