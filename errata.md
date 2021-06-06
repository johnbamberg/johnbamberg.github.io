---
layout: default
title: Errata
---

# Errata and Addenda

> Experience is the name everyone gives to their mistakes.  
> - <cite>Oscar Wilde</cite>

> Anyone who has never made a mistake has never tried anything new.  
> - <cite>Albert Einstein</cite>

Please let me know if you find a mistake in one of my papers. Here is a list of the ones I know of so far:

### The crystallographic restriction, permutations, and Goldbach’s Conjecture,  
*American Mathematical Monthly 110 (2003), 202–209,  
    with Grant Cairns and Devin Kilminster.*
   
   In Table 1 on page 204, we are missing some entries:
	- for n=20, we are missing 2520
	- for n=22, we miss 2310
	- for n=24, we miss 2184, 2340, 2640, 2730, 2772, 3080, 3960, 4620, 5040
	
	For more information, see N.J.A. Sloane's On-Line Encyclopaedia of Integer 	Sequence,entries A080736-A080742.
	
### Transitive eggs,
*Innovations in Incidence Geometry 4 (2006), 1–12.  
    with Tim Penttila.*
    
   On page 4, under "Reducible examples", we write 
   > In fact, it follows that $u = \tfrac{2}{3}d$ by noting that a primitive divisor of $q^{(2/3)d} − 1$ also divides $|\hat{G}|$.
   
It is true that $u=\tfrac{2}{3}d$ but not for the reasons we gave. Here is the fleshed out proof of this fact. We go to the trouble of generalising the argument because we think it provides more insight and might be applicable to other situations.
   
 ----  
   **Lemma:** Let $q$ be a prime power, $d$ and $e$ positive integers with $d/2 \le e \le d$, and $G\le GL(d,q)$. Suppose that $G$ permutes a set $\mathcal{O}$ of mutually disjoint subspaces of $\mathsf{V}(d,q)$ such that there exists a primitive prime divisor of $q^e-1$ that divides $|\mathcal{O}|$ and $G$. 
Suppose also that $G$ fixes a subspace $U$ of dimension $u\le d-e$. Then either
	1. $u=e=d/2$, or
	2. $U$ intersects each element of $\mathcal{O}$ trivially.
	
*Proof.* We suppose that (1) does not hold and prove that in this case (2) must hold. Observe that $e\ge d/2$ and $u\le d-e$ imply $u\le d/2 \le e$. 
So $u<e$. Fix a primitive prime divisor $r$ of $q^e-1$ that divides $|\mathcal{O}|$ and $|G|$. Let $r^\ell$ denote the highest power of $r$ dividing $|G|$ (note that $\ell>0$), and consider a Sylow $r$-subgroup $R \leq G$ of order $r^\ell$. Observe that for every $\pi \in \mathcal{O}$, there exists $g\in R$ such that $\pi^g \neq \pi$. Indeed, if $\pi^g=\pi$ for all $g\in R$ then $R$ is contained in the stabiliser $Stab_G(\pi)$ of $\pi$ in $G$, and hence $r^\ell$ divides $|Stab_G(\pi)|$, which contradicts the fact that the orbit $\mathcal{O}$ of $\pi$ has size divisible by $r$. 
Moreover, since $u<e$, it follows that $g$ acts trivially on $U$, because if $g$ acted nontrivially then $r$ would divide $|GL(U)|$ and hence $q^i-1$ for some $i\leq u$, a contradiction because $r$ is a ppd of $q^e-1$ and $u<e$. 
Since $\pi^g\ne\pi$, we have $\pi^g\cap \pi=\{0\}$. Since $g$ fixes $U$ pointwise, $(U\cap \pi)^g=U\cap\pi$. However, $U\cap \pi=(U\cap \pi)^g\cap (U\cap \pi)\le \pi^g\cap \pi=\{0\}$, which is (2).  QED

----Now for the transitive eggs argument: Write $d=3n$. A pseudo-oval consists of $q^{e/2}+1$ subspaces of dimension $n$ where $e=2n=2d/3$. Since $q$ is odd, the tangent spaces to $\mathcal{O}$ form a pseudo-oval $\mathcal{O}^\star$ of the dual space, and it also admits $G$ acting transitively. The dual $U^\star$ of $U$ has dimension $u^\star\le n=d-e$. Because $G$ acts transitively on $|\mathcal{O}^\star|$, and because as $q\neq 2$ and $e>2$, there exists a ppd of $q^e-1$ dividing $|\mathcal{O}^\star|$ and $|G|$. Hence, by the lemma above, $U^\star$ intersects each element of $\mathcal{O}^\star$ trivially. Therefore, $\dim (U^\star)\leq 3n - n =2n$ and the result follows.


### Tight sets and m-ovoids of finite polar spaces, 
*Journal of Combinatorial Theory Series A 114 (2007), no. 7, 1293–1314.  
    with Shane Kelly, Maska Law, and Tim Penttila.*
    
This was pointed out to me by Klaus Metsch. The proof of Theorem 8 has a mistake, that can be fixed by patching the counting argument there. In the first case, we claim there is a bijective correspondence between the lines $\bar l_R$ with $\bar l_R\subseteq 
l_R^\perp$ and the lines $l$ on $P$ with $\bar l\cap l^\perp\not=\varnothing$. It's incorrect.

Ferdinand Ihringer gives a complete proof in Section 3.3 of his Masters Thesis. There is also a beautiful algebraic combinatorial argument by Frédéric Vanhove that I can communicate privately.

### Overgroups of cyclic Sylow subgroups of linear groups,  
*Communications in Algebra 36 (2008), no. 7, 2503–2543,  
    with Tim Penttila.*

1. This was pointed out by Bob Guralnick. The entire field extension case should be there for the Hermitian varieties in odd dimension (Theorem 4.1). The only change needed is to add the extension
field groups of odd prime degree. 
2. This was pointed out be Tao Feng. Under the sporadic simple group case, the line $G’=2\cdot M_{22}$ can be deleted, because $q=2$ is not valid.
	
### Elation generalised quadrangles for which the number of lines on a point is the successor of a prime,  
*Journal of the Australian Mathematical Society 85 (2008), no. 3, 289–303,  
    with Tim Penttila and Csaba Schneider.*

The following mistake in Lemma 4.6 of our paper was pointed out by Koen Thas in his paper "Isomorphisms of groups related to flocks". We say:

>... one can see that $H=(H\cap A)(H\cap B)Z(E)$. So $$C^\star\cap H=(C\cap (H\cap A)(H\cap B))Z(E)$$

This statement is only true if $p$ is odd (which we assume anyway), and can be proved easily by applying 2.6.1 of "Finite generalized quadrangles", Payne and Thas. 

### A hemisystem of a nonclassical generalised quadrangle,  
*Designs, Codes and Cryptography 51 (2009), no. 2, 157–165,  
    with Frank De Clerck and Nicola Durante.*
    
In the introduction we say
> Generalised quadrangles are partial quadrangles with $\mu=s(t+1)$

It should read $\mu = t+1$.


### Weighted intriguing sets of generalised quadrangles

The inequality on the last page should have $\le$ rather than $<$.







