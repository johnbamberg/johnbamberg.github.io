---
layout: page
usemath: true
title: Chapter 2
---

### 2.3
We will use the fact that the collineation group of $\mathsf{PG}(2,\mathbb{R})$ acts
transitively on pairs $(P,\ell)$ where $P$ and $\ell$ are a point and line that are not incident. This allows us to suppose without loss of generality that $C=(0,0,1)$ and $\ell:z=0$. It is a routine calculation that the subgroup of $\mathsf{PGL}(3,\mathbb{R})$ fixing $C$ line-wise and $\ell$ point-wise consist of collineations induced by the matrices of
the form 
\[\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&\gamma
\end{bmatrix},\quad \gamma\in \mathbb{R}\backslash\{0\}.\] 
Clearly this group is isomorphic to $\mathbb{R}\backslash\{0\}$ under multiplication, which is
abelian. So two homologies with centre $C$ and axis $\ell$ lie in this
group and thus commute.

(We remark that this proof can also be done synthetically, but one needs
to use the fact that Pappus' Theorem holds in
$\mathsf{PG}(2,\mathbb{R})$).

### 2.4

(a) (We assume that the product of two central collineations is a
    central collineation). First, notice that $\phi\psi$ fixes the point
    $C$ as $C^{\phi\psi}=(C^\phi)^\psi=C^\psi=C$. Now let $\ell$ be a
    line incident with $C$. Then $\phi$ fixes $\ell$ and $\psi$ fixes
    $\ell$. Therefore, $\phi\psi$ fixes $\ell$. So $\phi\psi$ is an
    elation with centre $C$.

(b) Let $u$ be the line on the two points $a\cap m^\tau$ and
    $b\cap m^\sigma$. Now $m^\tau$ is the line joining $b\cap m$ and
    $a\cap u$. So $$\begin{aligned}
    m^{\tau\sigma} &=(b\cap m)^\sigma(a\cap u)^\sigma\\
    &=(b\cap m^\sigma)(a\cap u^\sigma)\\
    &=u,\end{aligned}$$ as $a\cap u^\sigma=a\cap u$. Similarly,
    $m^{\sigma\tau}=u$ and hence $m^{\sigma\tau}=m^{\tau\sigma}$.

(c) Let $\psi$ and $\phi$ be two elations sharing a common centre $C$.
    From (a), $\psi\phi$ and $\phi\psi$ are both elations with centre
    $C$. Let $\ell$ be the axis of $\psi\phi$ and let $X$ be a point
    incident with $\ell$. Let $m$ be a line. If $m$ is incident with
    $C$, then $m^{\psi\phi}=m=m^{\phi\psi}$. Otherwise, if $m$ is not
    incident with $C$, then by (b), we also have
    $m^{\psi\phi}=m=m^{\phi\psi}$. Therefore,
    $\psi\phi \psi^{-1}\phi^{-1}$ fixes every line of the projective
    plane and so is equal to the identity.

### 2.11 
Apply Pappus' Theorem to $A$, $m_1\cap n_2$, $m_1\cap n_3$, $A'$,
$n_1 \cap m_3$, $n_1 \cap m_2$. Then $A(n_1 \cap m_2)=m_2$,
$A'(m_1 \cap n_3)=n_3$, $A(n_1 \cap m_3)=n_1$, $A'(m_1\cap n_2)=n_2$. So
$(m_1\cap n_2)(m_2 \cap n_1)$, $(m_3 \cap n_1)(m_1 \cap n_3)$ and
$(m_3 \cap n_2)(m_2 \cap n_3)$ are concurrent.

### 2.12 
Apply Pappus' Theorem to $AB \cap CD$, $F$, $G$, $AD \cap BC$, $H$, $I$.
Then $(AB \cap CD)H=AB$, $(AD \cap BC)F=BC$ and these lines meet at $B$.
So $(AB \cap CD)I=CD$ and $(AD \cap BC)G=AD$, and these lines meet at
$D$. Hence $B$, $D$ and $FI \cap GH$ are collinear.

### 2.14 
The triangles $AFH$, $UCG$ have $AF \cap UC=D$, $AH \cap UG=V$,
$FH \cap CG=B$, with $D$, $V$, $B$ collinear, so, by the dual of
Desargues' Theorem, $AU$, $FC$ and $HG$ are concurrent.

### 2.15 
The triangles $XYZ$, $DCB$ are in perspective from $A$ (and $XYZ$
is a triangle by Fano's axiom), so, by Desargues' Theorem,
the intersections $L$, $M$, $N$ of corresponding sides are collinear.

### 2.16 
Apply Desargues' Theorem to the triangles $AED$ and $BFC$, which
are in perspective from $P$. This shows that the intersection points of
the diagonals of quadrilaterals $ABCD$, $ABEF$ and $CDFE$ lie on a line.
Now apply Desargues' Theorem
to the triangles $AFC$ and $BED$, which are in perspective from $P$.
This shows that the diagonals of quadrilaterals $ABCD$ and $CDFE$ and
$Q$ are collinear.

### 2.17 
We have $B'D\parallel AF \parallel A'E$ and
$BD \parallel B'F \parallel EC'$ and $AE \parallel FA' \parallel DC'$.
Now work in $\mathsf{PG}(2,\mathbb{R})$. Let $A''$ be the point at infinity on $FA'$,
$B''$ be the point at infinity on $FB'$ and $C''$ be the point at
infinity on $DB'$. Then $A"F \cap C"E=A'$, $B"F  \cap C"D=B'$,
$A"D \cap B"E=C'$. So, by Pappus' Theorem, $A'$,
$B'$, $C'$ are collinear.

### 2.18 
The six lines $a_1:=BC$, $a_2:=AG$, $a_3:=EF$ and $b_1:=AB$,
$b_2:=GF$, $b_3:=DC$ form two parallel triples, so the dual of Pappus'
Theorem applies: $\langle a_1 \cap b_2, a_2 \cap b_1\mathbb{R}angle=HA$,
$\langle a_1 \cap b_3,a_3 \cap b_1\mathbb{R}angle=CE$ and
$\langle a_2 \cap b_3,a_3 \cap b_2\mathbb{R}angle=DF$ are concurrent.

### 2.19 
Let the diagonals of quadrilaterals $ABCD$, $ABEF$ and $CDFE$
intersect respectively at $R,S$ and $T$. Triangles $ACF$ and $BDE$ are
in perspective from $P$, so, by Desargues' Theorem,
$R$, $S$ and $T$ are collinear. Triangles $ADE$ and $BCF$ are in
perspective from $P$, so, by Desargues' Theorem,
$Q$, $S$ and $T$ are collinear.
