# Reconstruction card — J. L. Nielsen NIEWTC

**Date:** 2026-08-07  
**Local PDF:** `docs/sources/nielsen-NIEWTC.pdf`  
**SHA256:** `9529E43EBFF1E38A808397DA0C0FC56CABCB71C41B622FABA54B6B57573D3884`  
**Text:** `docs/sources/nielsen-NIEWTC.txt`  
**NON-CLAIMS:** Card describes Nielsen’s claims; does not endorse Connes true/false or OpenAI/Zhou invalidity without independent check.

## Bibliographic

| Field | Value |
|-------|--------|
| Author | J. L. Nielsen |
| Affiliation | Center for Topological Physics / University of Kansas |
| Title (PDF) | Connes’ Rigidity Conjecture: Disproof of the Counterexamples and Proof of the Theorem |
| Date | August 2026 |
| PhilPapers | NIEWTC |

## Part I — claimed invalidation of counterexamples

1. **OpenAI / Anthropic-style pairs** \(\Gamma_0,\Gamma_\tau\): split vs non-split extensions of \(\mathrm{Sp}_4(\mathbb{Z})\) by \(\mathbb{Z}^4\).  
   - Reductio: assume \(L(\Gamma_0)\cong L(\Gamma_\tau)\); Bernoulli + twisted comultiplication + **Ioana Thm 8.2** ⇒ injective \(\delta_2\); Borel density; Margulis; Schur; Bockstein \([\tau]\neq 0\) contradiction.  
   - Also claims **code-internal** OpenAI failures: ICC/spec gap (cocycle vs semidirect), nontrivial centre (not ICC), surjection to infinite abelian (not (T)).

2. **Zhou** \(\Gamma_i=D\rtimes_{\theta_i} H\): same reductio methodology; \(D\) unique maximal abelian normal; \(\delta_2\) must intertwine \(\theta_1,\theta_2\); contradicts Zhou §6 non-isomorphism.

## Part II — claimed proof of Connes

Same \(\Theta(f u_g)=f u_g\otimes\Phi(u_g)\) for **arbitrary** ICC+(T) \(G,H\); claims NI conditions hold **uniformly** via:
- Bernoulli deformation fixes group unitaries (spectral gap / Case I kill)
- \(\Theta(L^\infty(X))=L^\infty(X)\otimes 1\) (Cartan / Case II kill via Cor 2.3)
- Only Case III survives ⇒ \(\delta_1,\delta_2\); then finite-depth / index forces isomorphism.

## Nielsen’s reading of Ioana 8.2 (as stated)

Prop. 20: claims Thm 8.2 classifies \(\theta:L^\infty(X)\rtimes\Gamma\to L^\infty(X)\rtimes\Gamma\bar\otimes N\) for arbitrary finite \(N\), under (H1)(H2) and (NI1)(NI2).  
Acknowledges NI are **hypotheses**, verified in Props 22–24.

## Cross-link

Full audit vs Ioana fulltext: `docs/notes/ioana-theta-audit-2026-08-07.md` (updated NO-GO).
