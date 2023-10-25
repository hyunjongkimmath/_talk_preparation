---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Topic

---

- Written by: [Hyun Jong Kim](https://sites.google.com/wisc.edu/hyunjongkim?pli=1)
- Created: 10/8/2023
- Last updated: 10/25/2023

These are notes for my talk at the Algebra Seminar at Western University on Friday, 10/20/2023.

I would greatly appreciate comments and corrections to these notes; please send such suggestions to me at `hyunjong<dot>kim<at>math<dot>wisc<dot>edu` or to my latest email address.

---

> [!Disclaimer]
> You might find it useful to use [Obsidian.md](https://obsidian.md/) if you are reading this as a Markdown file so that you can use the internal links in these notes. However, I may or may not make other notes that this note links to publicly available, so such links may be useless to you. Nevertheless, reading this as a Markdown file on Obsidian.md (alongside as a pdf file) could supplement your reading experience.


> [!Title]
>An integral big monodromy theorem

> [!Abstract]
> Associated to a family of curves C -> S are ell-adic monodromy representations, which generalize Galois representations. I will discuss part my ongoing thesis work demonstrating a big monodromy result for the moduli space of superelliptic curves. This result uses an arithmeticity result of reduced Burau representations of Venkataramana and clutching methods of Achter and Pries. Time permitting, I will also describe applications of this big monodromy result in other parts of my thesis --- it can be used to prove a Cohen-Lenstra result for function fields and to prove a result on the vanishing of zeta functions for Kummer curves over the projective line over finite fields.

---

References:
- ![[_reference_achter_pries_imht]]
- Hyun Jong Kim, *Cohen-Lenstra heuristics and vanishing of zeta functions for superelliptic curves over finite fields*, thesis, in progress
- ![[_reference_venkataramana_ibrd]]

---


# Monodromy representations

Given a field $K$, an abelian variety $A$ of dimension $g$, and prime number $\ell$, and $k \geq 0$, one has mod-$\ell^k$ Galois representations
	$$\rho_{A,\ell^k}: \operatorname{Gal}(\overline{K}/K) \to \operatorname{Aut}(A[\ell^k]) \cong \operatorname{GL}_{2g}(\mathbb{Z}/\ell^k \mathbb{Z})$$
Taking inverse limits, we get the $\ell$-adic Galois representation
	$$\rho_{A, \mathbb{Z}_\ell}: \operatorname{Gal}(\overline{K}/K) \to \operatorname{Aut}(T_\ell A) \cong \operatorname{GL}_{2g}(\mathbb{Z}_\ell).$$

More generally, given an irreducible scheme $S$, an abelian scheme $X/S$ and a prime number $\ell$ invertible on $S$, $X[\ell]$ is a finite etale cover of $S$ and there there mod-$\ell^k$ monodromy representations
	$$\rho_{X, \ell^k}: \pi_1^{\text{\'et}}(S,s) \to \operatorname{Aut}(X[\ell]_s) \cong \operatorname{GL}_{2g}(\mathbb{Z}/\ell^k \mathbb{Z}).$$
where $s \in S$ is a geometric point. Taking inverse limits, we get the $\ell$-adic monodromy representation.
	$$\rho_{X, \mathbb{Z}_\ell}: \pi_1^{\text{\'et}}(S,s) \to \operatorname{Aut}(X[\ell]_s) \cong \operatorname{GL}_{2g}(\mathbb{Z}/\ell^k \mathbb{Z}).$$
Note that the isomorphism class of the image $M_{\mathbb{Z}_\ell}(S)$[^2] of $\rho_{X, \mathbb{Z}_\ell}$ does not depend on $s$.

[^2]: Note that $X$ is suppressed in this image. In this talk, $X$ will often be clear in context. 
 
> [!Question]
> How big is the image of $M_{\mathbb{Z}_\ell}(S)$?

Sometimes, there are "trivial" restrictions to $M_{\mathbb{Z}_\ell}(S)$. For instance, if $X/S$ is principally polarized, i.e. we have an isomorphism $X \to X^\vee$,  then the Weil pairing $X[\ell] \times X^\vee[\ell] \to \mu_{\ell, S}$ is a skew-symmetric pairing $X[\ell] \times X[\ell] \to \mu_{\ell, S}$. In this case, $M_{\mathbb{Z}_\ell}(S)$ is contained in the group of symplectic similitudes of $(X[\ell]_s, \langle \cdot, \cdot \rangle)$, which is isomorphic to $\operatorname{GSp}_{2g}(\mathbb{Z}_\ell)$[^3]. If $S$ has a primitive $\ell$th root of unity, then $\pi_1(S,s)$ acts trivially on $\mu_{\ell,S}$, so $M_{\mathbb{Z}_\ell}(S)$ is contained in $\operatorname{Sp}_{2g}(\mathbb{Z}_\ell)$. 

[^3]:  $$\operatorname{GSp}(V,\langle\cdot, \cdot\rangle)=\left\{M \in \operatorname{GL}(V) \mid \exists \lambda(M) \in R^{\times}:\langle M v, M w\rangle=\lambda(M)\langle v, w\rangle \forall v, w \in V\right\}$$

For the situation that I will eventually describe, the monodromy representation also has to preserve a "complex multiplication" on $X$, which turns out to mean that the monodromy representation has to preserve a unitary group.

We are interested in the case that $X$ is the relative degree $0$ Picard group $\operatorname{Pic}^0(C) = \operatorname{Pic}^0_{C/S}$ where  $\psi: C \to S$ is a relative proper [[achter_pries_imht_3#Semi-stable curve|semi-stable curve]]. 

> [!Definition]
> $\psi$ is semi-stable if it is [[foag_flat_morphism_of_schemes|flat]] and [[foag_ 10.3.1|proper]] and the [[foag_ 9.5.1#Geometric fiber|geometric fibers]] of $C$ are [[bredon_Definition 4.1|connected]], [[foag_ 5.2.1|reduced]] curves whose only singularities are ordinary double points.  

It turns out that $\operatorname{Pic}^0(C)$ is a [[bosch_lutkebohmert_raynaud_nm_page_178|semiabelian scheme]] over $S$, i.e. it is smooth and all (geometric) fibres have identity components which are extensions of an abelian variety by an affine torus.

Assuming that there is at least one geometric point $s$ such that the fiber $\operatorname{Pic}^0(C_s)$ is an abelian scheme, then there is a nonempty  open subscheme $S^*$ of $S$ such that $\operatorname{Pic}^0(C|_S^*)$ is an abelian scheme, so we can talk about the monodromy representations of this:

$$\rho_{C|S^*, \mathbb{Z}_\ell}: \pi_1^{\text{\'et}}(S^*,s) \to \operatorname{Aut}(X[\ell]_s)$$

The image of this representation does not depend on the choice of $S^*$; if $U \subseteq Y$ is an open embedding, then the induced map $\pi_1^{\text{\'et}}(U,s) \to \pi_1^{\text{\'et}}(Y,s)$ is a surjection. 

Write $M_{\mathbb{Z}_\ell}(S)$ for (the isomorphism class of) this image, which does not depend on the choice of $s$.

This formalism can be generalized to when $S$ is an algebraic stack $\mathcal{S}$; there is a theory of etale fundamental groups for algebraic stacks, say by Noohi (2004).



# Moduli of covers of genus $0$ curves

Aside: Romagny and Wewers (2006) constructed a Hurwitz scheme $\mathcal{H}_{G,n}$, where $G$ is a finite group and $n \geq 1$, of tamely ramified $G$-covers $f: Y \to \mathbb{P}^1$, i.e. the cover is Galois, ramification is tame, and there are $n$ branch points (in $\mathbb{P}^1$). It is only a coarse moduli space, but it is a fine moduli space whenever $G$ is center-free

Let $G = \mathbb{Z}/d\mathbb{Z}$. There is a Deligne-Mumford stack  $\widetilde{\mathcal{M}}_G$ of labeled admissible stable $G$-curves $(C/S, \iota_0,\eta)$

> [!Abridged definition]
> A labeled admissible stable $G$-curve $(C/S, \iota_0, \eta)$
> - is a semi-stable curve
> - $\iota_0: G \to C/S$ is a $G$-action with $C/\iota_0(G)$ an arithmetic genus $0$ curve, 
> - $\eta$ is a labeling of branch points (and the ordering of the labels matter) under smooth ramified points.
> - the irreducible components has stable labeling, 
> - singularities are "admissible" 

> [!Remark]
> Achter and Pries only deal with the prime $d$ case; also they have $\eta$ be a labeling of the ramified points.

> [!Remark]
> Over an algebraically closed field, a genus $0$ curve is a bunch of $\mathbb{P}^1$'s glued together at simple intersections and such that no cycles are formed.  In other words, such a curve is a tree of $\mathbb{P}^1$'s

Associated to such a curve are "class vectors" describing branching and inertia/monodromy around each branch point.

For example, take the smooth completion $C$ of the curve given by 

$$y^3 = (x-1)(x-5)^2$$

over a field with all third roots of unity, such that the characteristic is not $3$ (and with $1 \neq 5$.).

The curve is a $\mathbb{Z}/3\mathbb{Z}$-cover of $\mathbb{P}^1$ totally ramified over $x = 1, 5$. But there is way (see Section 5 of Wood's "An Algebraic Lifting Invariant of Ellenberg, Venkatesh, and Westerland" for example) to express that the branching has monodromy/inertia type $1$ at $x = 1$ and $2$ at $x = 5$. By specifying a labeling to have $x = 1$ and $x = 5$, we have a class vector $(1,2)$ consisting of elements of $\mathbb{Z}/d\mathbb{Z} - \{0\}$ listing out these monodromy types.

> [!Remark]
> The monodromy types depend on choices of roots of unity, but different choices only scale the class vector by elements of $\mathbb{Z}/d\mathbb{Z}^\times$.


> [!Remark]
> For the $\mathbb{Z}/d\mathbb{Z}$-cover $C$ of $\mathbb{P}^1$ to be smooth, the entries of the class vector need to add to $0 \in \mathbb{Z}/d\mathbb{Z}$.

For instance, in the example above, $1 + 2 \equiv 0 \pmod{3}$, so we know that there is no branching above $x  = \infty$. 

For another example,

$y^6 = x(x-1)^4(x-2)^3$

has class vector $(1,4,3,5)$; there is branching at $\infty$ with monodromy type $5$ to ensure that $1 + 4 + 3 +5 \equiv 0 \pmod{6}$.


> [!Facts]
> 1. $\widetilde{\mathcal{M}}_G$ is a smooth proper Deligne-Mumford stack over $\mathbb{Z}[1/d,\zeta_d]$ with an open and dense substack $\widetilde{\mathcal{M}}_G^\circ$ parameterizing the smooth curves $C$
> 2. Given a class vector $\gamma: \{1,\ldots,r\} \to (\mathbb{Z}/d\mathbb{Z}) - \{0\}$ the substack $\widetilde{\mathcal{M}}_G^\gamma$ of $\widetilde{\mathcal{M}}_G$ parameterizing the curves with class  vector $\gamma$ is an irreducible component (and hence a connected component)

# The big monodromy result 
Now I can talk about big monodromy for the tautological curve $\mathcal{C}^\gamma$ over $\widetilde{\mathcal{M}}_G^\gamma$. By definition, there is a $G$-action on this curve. Let $\zeta_d$ stand for a generator of $G$. Given a geometric point $s \in \widetilde{\mathcal{M}}_G^\gamma$ such that $\operatorname{Pic}^0(\mathcal{C}|_s)$ is an abelian variety. Due to the $G$-action, it turns out that the Weil pairing on $T_\ell \operatorname{Pic}^0(\mathcal{C}|_s)$ yields a Hermitian space over $\mathbb{Z}_\ell[\zeta_d] = \mathbb{Z}_\ell[X]/(1 + X + \cdots + X^{d-1})$

> [!Theorem] (K., ongoing thesis)
> Let $d \geq 2$. Let $\bar{k}$ be an algebraically closed field of characteristic not $d$. For all but finitely many primes $\ell$ and for all $n \geq 2d+1$, $M_{\mathbb{Z}_\ell}( \widetilde{\mathcal{M}}_G^\gamma \otimes \overline{k})$ contains the special unitary group of $\operatorname{Pic}^0(\mathcal{C}|_s)$ for $\gamma = (\underbrace{1,\ldots,1}_{n \text{ times}}, -n \pmod{d} )$.

Stronger results where proved for $d = 2,3$ by Jiu-Kang Yu (unpublished) and Achter-Pries (2007) respectively.

> [!Strategy]
> 1. Over $k = \mathbb{C}$
> 	1. Use Venkataramana's arithmeticity result to get base cases 
> 	2. Use clutching methods of Achter and Pries to induct
> 2. Convert to characteristic $p$ using tamely ramified fundamental groups

# Clutching maps

Suppose that $(C_i/S, \iota_{0,i},  \eta_{0,i})$ are two labeled, stable, admissible curves with class vectors $\gamma_i$ such that $\gamma_1(r_1) = -\gamma_2(1)$ and $\gamma_1(r_1), \gamma_2(1)$ are coprime to $d$. We can glue $C_1$ and $C_2$ to get a new $C$ with class vector

$$\gamma  = (\gamma_1(1), \ldots, \gamma_1(r_1-1), \gamma_2(2) \ldots, \gamma_2(r_2)).$$

We say that $\gamma$ degenerates to $(\gamma_1,\gamma_2)$ or that $(\gamma_1,\gamma_2)$ deforms to $\gamma$.

Also $C/S$ is "equivariantly smoothable"; note that the sum of entries of $\gamma$ is $0$ mod $d$. We thus have a map

$$\kappa: \widetilde{\mathcal{M}}_G^{\gamma_1} \times \widetilde{\mathcal{M}}_G^{\gamma_2} \to \widetilde{\mathcal{M}}_G^{\gamma}$$

mapping into a boundary of $\widetilde{\mathcal{M}}_G^\gamma$.



> [!Lemma]
> Let $k$ be an algebraically closed field in which $d\ell$ is invertible. 
> 1. There is a canonical isomorphism
> $$(\kappa \otimes k)^* \operatorname{Pic}^0(\mathcal{C}^\gamma)[\ell] \cong \operatorname{Pic}^0(\mathcal{C}^{\gamma_1})[\ell] \times \operatorname{Pic}^0(\mathcal{C}^{\gamma_2})[\ell]$$
> 2. Suppose that $s_i \in \widetilde{\mathcal{M}}_G^{\gamma_i}(k)$ for $i = 1,2$ and let $s = \kappa(s_1,s_2)$. After base change to $k$, there is a commutative diagram
![[Pasted image 20231017132242.png]]


Given $\gamma_1, \gamma_2, \gamma_3$ such that $\gamma_1(r_1) = -\gamma_2(1)$ and $\gamma_2(r_2) = -\gamma_3(1)$, write $\gamma_L$ and $\gamma_R$ for the class vectors degenerating to $(\gamma_1, \gamma_2)$ and $(\gamma_2, \gamma_3)$. Also write $\gamma$ for the class vector degenerating to $(\gamma_1, \gamma_R)$ or $(\gamma_L, \gamma_3)$. So we have injections
$M_\ell(\widetilde{\mathcal{M}}_G^{\gamma_1}) \times M_\ell(\widetilde{\mathcal{M}}_G^{\gamma_R}) \to M_\ell(\widetilde{\mathcal{M}}_G^{\gamma})$ and  $M_\ell(\widetilde{\mathcal{M}}_G^{\gamma_L}) \times M_\ell(\widetilde{\mathcal{M}}_G^{\gamma_3}) \to  M_\ell(\widetilde{\mathcal{M}}_G^{\gamma})$

The inductive argument is as follows: if $M_\ell(\widetilde{\mathcal{M}}_G^{\gamma_R})$ and $M_\ell(\widetilde{\mathcal{M}}_G^{\gamma_L})$ both contain their respective special unitary groups, then so does $M_\ell(\widetilde{\mathcal{M}}_G^{\gamma})$.

# Venkataramana's arithmeticity result


There is the **reduced Burau representation**

$$B_n \cong \pi_1(\operatorname{Conf}_n^{\text{disc}}) \to \operatorname{GL}_{n-1}(\mathbb{Z}[t,t^{-1}])$$

essentially coming from the monodromy action of a family of topological covers of the complex unit disk with $n$ punctures. We get more representations by evaluating these at $t = d\text{-th roots of unity}$. Also, if you take this representation mod $\ell$, then you get the 

> [!Theorem] (Venkatarmana, 2011)
> The reduced Burau representation evaluated at any primitive $d$th-root of unity is an arithmetic group. More precisely, its image is a subgroup of finite index in an appropriate unitary group over $\mathbb{Q}(\operatorname{cos}(2\pi/d))$, the totally real sub-field of the $d$th cyclotomic extension of $\mathbb{Q}$.


One consequence is that the appropriate arithmeticity still holds when you fill in the punctures (and get a ramified cover). In turn, here is a consequence more relevant to the big  statements of interest:

> [!Theorem]
> (K., thesis, in progress)
> For all $d \geq 2$, for all $n \geq 2d+1$, for all but finitely many primes $\ell \nmid d$, $M_{\mathbb{Z}_\ell}( \widetilde{\mathcal{M}}_G^{\gamma} \otimes \mathbb{C})$  contains the special unitary group of $\operatorname{Pic}^0(\mathcal{C}^\gamma |_s)$, where $\gamma = (1,\ldots,1,-n)$.
> 

One can prove this by using weak approximation of the special unitary group as a linear algebraic group.

This looks quite similar to the main theorem, but is different in the order of the quantifiers. Here, the statement is:

- For all $d \geq 2$, for all $n \geq 2d+1$, for all but finitely many primes $\ell \nmid d$

Whereas the statement for the theorem is:

- For all $d \geq 2$, for all but finitely many primes $\ell \nmid d$, for all $n \geq 2d+1$.

Nevertheless, by carefully using the clutching methods, one can use induction to get the main theorem from the above statement.

# Applications
















# See Also

# Meta
## References

## Citations and Footnotes