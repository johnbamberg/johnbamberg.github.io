---
layout: page
usemath: true
title: Chapter 4
---

### 4.6 
We simply apply the *cocycle identity* of cross-ratio:
$\\require{textcomp}
\begin{aligned}
\textrecipe(A,B;E,C)&=\CrossRatio(A,B;D,C)\CrossRatio(A,B;E,D)\\
&=-\CrossRatio(A,B;E,D)\\
&=-\CrossRatio(A',C';B',D)&\text{via projection from }O'\\
&=-\CrossRatio(A,C;B,D)&\text{via projection from }O\\
&=-(1-\CrossRatio(A,C;B,D))&\text{by Lemma }\ref{permutecrossratio}\\
&=-2.\end{aligned}$

### 4.8 
First, $\ratio(A,H,C)=1/4$, so if $Q$ is the point at infinity on
$AC$, then $\CrossRatio(A,H;C,Q)=1/4$. Hence $\CrossRatio(Q,H;A,C)=4/3$.
Choose $n$ on $C$ such that $d(n \cap PH,n \cap PA)=d(n \cap PH, C)$.
(That is, take the line $g$ parallel to $PA$ through $C$, and then take
the parallel $h$ to $PC$ through $PH\cap g$. The point $n$ is the line
$CX$ where $X=h\cap PA$). Then
$$\CrossRatio(n \cap \ell',n \cap PH;n \cap PA,C)=4/3,$$ so
$d(n \cap \ell',n \cap PH)=d(n \cap PA, C)$.

### 4.9

(i) As usual, we set two reference points $O$ and $I$ on $\ell$ so that
    we can write each point in coordinate form; write $(x,1)$ for the
    point $xI+O$. We will assume $I$ is the point at infinity on $\ell$,
    so that it is not one of our points. Let
    $$A=(a,1), \quad B=(b,1), \quad C=(c,1),\quad D=(d,1).$$ In
    particular, we can now write expressions such as $d(B,A)=b-a$ (n.b.,
    we are using 'directed distance' here, but it will not matter in
    what follows). Let $P$ be the point $(p,1)$. Then for each $X$ in
    $\{C,D\}$, we have $$\begin{aligned}
    \CrossRatio(X,B;P,A)&=\frac{(p-x)(a-b)}{(p-b)(a-x)}\end{aligned}$$
    and hence $$\begin{aligned}
    \CrossRatio(C,B;P,A)+\CrossRatio(D,B;P,A)&=\frac{(p-c)(a-b)}{(p-b)(a-c)}+\frac{(p-d)(a-b)}{(p-b)(a-d)}\\
    &=\frac{a-b}{p-b}\left( \frac{p-c}{a-c}+\frac{p-d}{a-d}\right)\\
    &=\frac{d(A,B)}{d(P,B)}\left( \frac{d(P,C)}{d(A,C)}+\frac{d(P,D)}{d(A,D)}\right)\end{aligned}$$
Now $d(P,C)=d(P,A)+d(A,C)$, and $d(P,D)=d(P,A)+d(A,D)$, and so
    $$\begin{aligned}
    \CrossRatio(C,B;P,A)+\CrossRatio(D,B;P,A)
    &=\frac{d(A,B)}{d(P,B)}\left( \frac{d(P,A)}{d(A,C)}+\frac{d(P,A)}{d(A,D)}+2\right)\\
    &=\frac{d(P,A)}{d(P,B)}\left( d(A,B)\cdot \left(\frac{1}{d(A,C)}+\frac{1}{d(A,D)}\right)+d(A,B)\frac{2}{d(P,A)}\right)\end{aligned}$$
    Also, $d(P,A)+d(A,B)=d(P,B)$ and hence $$\begin{aligned}
    \CrossRatio(C,B;P,A)+\CrossRatio(D,B;P,A)
    &=\frac{d(P,A)}{d(P,B)}\left( d(A,B)\cdot \left(\frac{1}{d(A,C)}+\frac{1}{d(A,D)}\right)+2\left(\frac{d(P,B)}{d(P,A)}-1\right)\right)\\
    &=\frac{d(P,A)}{d(P,B)}\left( d(A,B)\cdot \left(\frac{1}{d(A,C)}+\frac{1}{d(A,D)}\right)-2\right)+2\\
    &=2S( d(A,B)/H-1)+2\end{aligned}$$ where $H$ is the harmonic mean of
    $d(A,C)$ and $d(A,D)$, and $S=\frac{d(P,A)}{d(P,B)}$. Therefore,
    $d(A,B)=H$ if and only if
    $\CrossRatio(C,B;P,A)+\CrossRatio(D,B;P,A)=2$.

(ii) We use the previous result: $d(A,B)$ is the harmonic mean of
     $d(A,C)$ and $d(A,D)$ if and only if
     $$\CrossRatio(D,B;C,A)=\CrossRatio(C,B;C,A)+\CrossRatio(D,B;C,A)=2.$$
     (We make use of the convention that $\CrossRatio(C,B;C,A)=0$).
     Recall, from the discussion before Theorem
     [\[cocycleidentity\]](#cocycleidentity){reference-type="ref"
     reference="cocycleidentity"}, that
     $$\CrossRatio(D,B;C,A)=1-\CrossRatio(A,B;C,D).$$ So
     $$\begin{aligned}
     \CrossRatio(C,B;C,A)+\CrossRatio(D,B;C,A)=\CrossRatio(C,B;C,A)+1-\CrossRatio(A,B;C,D)\end{aligned}$$
     and so the result follows by noting that the above quantity is
     equal to $2$ if and only if $\CrossRatio(A,B;C,D)=-1$. (This
     exercise was taken from @Eves:1972to [Theorem 2.6.4]).

### 4.12 
10 centimetres. Let the image of the first foot of the yardstick be
$AB$, the second foot be $BC$, the third foot be $CD$. Then
$$\begin{aligned}
\CrossRatio(A,B;C,D)&=\tfrac43\\
&=\ratio(D,B,A)/\ratio(C,B,A)=\\
&= \frac{35}{14}\ratio(D,B,A),\end{aligned}$$ so
$$\ratio(D,B,A)=\frac{8}{15}=\frac{d(D,C)+14}{d(D,C)+35},$$ giving
$d(D,C)=10$. (This exercise was adapted from [@Duffin:1993vt p. 42]).

### 4.13 
By the Chasles-Steiner Theorem, since $P$, $Q$, $R_1$, $R_2$, $R_3$, $R_4$ are points
on a conic,
$$\CrossRatio(PR_1,PR_2;PR_3,PR_4)=\CrossRatio(QR_1,QR_2;QR_3,QR_4),$$
but $\CrossRatio(PR_1,PR_2;PR_3,PR_4)=\CrossRatio(PS,PT;PU,PV)$ and
$$\CrossRatio(QR_1,QR_2;QR_3,QR_4)=\CrossRatio(QT,QS;QV,QU)=\CrossRatio(QS,QT;QU,QV),$$
so $\CrossRatio(PS,PT;PU,PV)=\CrossRatio(QS,QT;QU,QV)$. Therefore, by
the Chasles-Steiner Theorem, $P$, $Q$, $S$, $T$, $U$, $V$ are points on
a conic.

