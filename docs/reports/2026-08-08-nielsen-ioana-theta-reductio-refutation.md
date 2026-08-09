# Report: Refutation of the Nielsen Ioana+Θ Reductio

**Quantyra Inc. — Jenny research lane**  
**Date:** 2026-08-08  
**Authors:** Daniel Eric Fredriksen (Quantyra); orchestrated audit with machine-checked Lean core  
**Status:** Public bounded report  
**Lean artifact:** https://github.com/Quantyra/connes-rigidity-lean (tag `v0.1.1-obstruction`)  
**Science repo:** https://github.com/Quantyra/connes-rigidity (tag `v0.1.1-report`)  

---

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

which is the forbidden “bad tensor leg” \(M_1\bar\otimes L(\Gamma_2)\) in Ioana’s setup. Therefore Theorem 8.2 does **not** license the rigid-case output (character + group morphisms \(\delta_1,\delta_2\)) from this map, and the reductio that depends on that output does not start.

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

**CI:** `lake build`, no `sorry`/`admit`, axiom register check.

**Build pin:** git SHA of tag `v0.1.1-obstruction` (release commit on `main` at/after `939f6e4dde123d7a94677085a2ffb8acfe9089ea`).

---

## 6. Review

| Role | Verdict |
|------|---------|
| Proof-adversarial | PASS (after metadata/report alignment) |
| Non-claims boundary | PASS (after §5 refresh) |
| Package/metadata | PASS (after v0.1.1 alignment) |
| Lean/build/audit | PASS at `939f6e4` |

Planning packets:  
- `Quantyra-Jenny-Planning` — `docs/claim-boundary-packets/2026-08-07-connes-audit-s006-nogo.md`  
- `docs/claim-boundary-packets/2026-08-08-reductio-goal-complete.md`  
- `docs/claim-boundary-packets/2026-08-08-reductio-v0.1.1-freeze.md`

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

The Nielsen **Ioana+Θ reductio is refuted** as an application of Ioana’s Theorem 8.2: the map \(\Theta\) is built so that a mandatory non-intertwining hypothesis fails.  

**Remaining open (by design, out of this report’s success criterion):** whether Connes’ conjecture holds; whether any particular counterexample construction is correct.

---

## 9. Citation

Please cite the Lean software release `v0.1.1-obstruction` and this report path in [Quantyra/connes-rigidity](https://github.com/Quantyra/connes-rigidity):

`docs/reports/2026-08-08-nielsen-ioana-theta-reductio-refutation.md`

**DOIs:**

| Artifact | DOI |
|----------|-----|
| Science report (concept) | [10.5281/zenodo.21845586](https://doi.org/10.5281/zenodo.21845586) |
| Science report v0.1.0 (historical) | [10.5281/zenodo.21845587](https://doi.org/10.5281/zenodo.21845587) |
| Lean package (concept) | [10.5281/zenodo.21845588](https://doi.org/10.5281/zenodo.21845588) |
| Lean v0.1.0-obstruction (historical) | [10.5281/zenodo.21845589](https://doi.org/10.5281/zenodo.21845589) |
| Lean/science v0.1.1 | pending Zenodo version DOIs after GitHub release |

**License:** Apache-2.0 (code); report text © Quantyra Inc., released with the science repository.
