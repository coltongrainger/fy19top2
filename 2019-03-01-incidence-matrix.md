---
title: Incidence numbers in Cellular Homology
author: 
- Colton Grainger (scribe)
- Shen Lu (presenter)
date: 2019-03-01
bibliography: /home/colton/coltongrainger.bib
xy: true
nonumbering: true
---

\providecommand{\ccw}{C^{\text{CW}}}
\providecommand{\k}[1]{K^{( #1 )}}
\renewcommand{\deg}[1]{\operatorname{deg}\left( #1 \right)}
\newcommand{\defeq}{\stackrel{\text{def}}{=}}

This problem is set from Bredon [@Bre93, number IV.11.12]. It demonstrates

- for a CW-complex $K$, the differential $\beta$ of the chain complex $\ccw_*(K)$ satisfies $\beta^2 =0$, and thus
- for an $n+1$ cell $\sigma$ and an $n-1$ cell $\omega$, we've $\sum_\tau [\omega : \tau][\tau : \sigma] = 0$ with $\tau$ ranging over all $n$-cells. 

### Given

Let $K$ be a CW-complex, with $n$-skeleton $\k n$ for $n \ge 0$. Because $\k{n}$ contains an open neighborhood around the closed subset $\k {n-1}$ that deform retracts onto $\k {n-1}$, we know:

- The relative homology $H_*(\k n, \k {n-1})$ is isomorphic to the reduced homology $\tilde{H}_*(\k n / \k {n-1})$.
- The quotient space $\k n / \k {n-1}$ is homeomorphic to the wedge $\vee ( I^n/\partial I^{n-1} ) \approx \vee S^n$, and thus

\begin{equation}
\xymatrix{
H_*(\k n , \k{n-1}) \ar[r]^-{\cong}_-{e_*}
    & \tilde{H}_*(\k n / \k{n-1}) \ar[r]^-{\cong}_-{\text{h.a.}}
    & \tilde{H}_*(\vee ( I^n/\partial I^{n-1} )) \ar[r]^-\cong
    & \displaystyle{ \bigoplus_\text{$n$-cells of $\k n$} } \tilde H_*(S^n).
}
\label{eq:ncells}
\end{equation}

We may define a chain complex $\ccw_*(K)$ associated to $K$ as follows:

- Let the chain group $\ccw_n(K)$ be $H_n(\k n, \k {n-1})$. This is the free abelian group (in the $n$th degree of the graded group) at the end of \eqref{eq:ncells} whose basis is the set of $n$-cells attached to $\k {n-1}$.

- Let the differential $\beta_n \colon \ccw_n(K) \to \ccw_{n-1}(K)$ be the composite 

    \begin{equation}
    \xymatrix{
    \ccw_n(K) = 
    H_n(\k n, \k {n-1}) \ar[r]^-{\delta_n} \ar@/_2.0pc/^-{\beta_n}[rr] 
        & H_{n-1}( \k {n-1} ) \ar[r]^-{j_{n-1}} 
        & H_{n-1}( \k {n-1},\k {n-2}) = \ccw_{n-1}(K).
    }
    \label{eq:beta}
    \end{equation}

In \eqref{eq:beta}, the boundary map $\delta_n$ arises from the long exact sequence for the pair $(\k n, \k{n-1})$, and the map of relative homology groups $j_{n-1} \colon H_{n-1} (\k{n-1}) \to H_{n-1} (\k{n-1}, \k{n-2})$ is induced by the inclusion of skeleta $j \colon (\k {n-1}, \emptyset) \hookrightarrow (\k{n-1}, \k{n-2}).$
    
From lecture [@Bea19, number 1.11.3], we know $\delta_n$ respects the attaching maps; for an $n$-cell $\sigma$ with attaching map $f_{\partial\sigma}$, $$\delta_n [I^n_\sigma] = [f_{\partial \sigma} ( \partial I^n_\sigma )].$$ 

And so, the differential $\beta_n$ can be described with "incidence numbers" [@Til13, number 8.5]. For an $n$-cell $\sigma$ and an $n-1$ cell $\tau$, define

\begin{equation}
[\tau : \sigma] := \text{deg}\bigg( \xymatrix @R-1.8pc{
    S^{n-1} \ar[r]^{f_{\partial\sigma}} \ar@2{~}[d]
    & \k {n-1} \ar[r] \ar@/_1.5pc/^-{p_\tau}[rrr]
    & \k{n-1} / \k{n-2} \ar[r]^-{\approx}
    & \vee S^{n-1} \ar[r]^{\text{find $\tau$}}
    & S^{n-1} \ar@2{~}[d]\\
    \partial I^n_\sigma & & & & I^{n-1}_\tau / \partial I^{n-1}_\tau
}\bigg).
\label{eq:incidencedef}
\end{equation}

To make three comments. First, we take for granted the rule $\sigma \mapsto \sum_\tau [\tau : \sigma] \tau$ on generators $\sigma$ in $\ccw_n(K)$ extends linearly and *is* the differential $\beta_n$ in \eqref{eq:beta}. See [@Bre93, page 203]. So write $\beta_n(\sigma) := \sum_\tau [\tau : \sigma] \tau$. Second, all but finitely many terms in the sum $\sum_\tau [\tau : \sigma]\tau$ must be zero. This is because the compact set $\partial I^n_\sigma$ is attached by $f_{\partial \sigma}$ to a *compact* subset of $\k {n-1}$. Third, the projection $p_\tau$ that "finds" $\tau$ in \eqref{eq:incidencedef} is the unique map $p_\tau \colon \k {n-1} \to S^{n-1}$ satisfying:

i. $p_\tau \circ f_\tau = \gamma_{n-1} = \text{smash product $\gamma \wedge \cdots \wedge \gamma$ of $n-1$ copies of the quotient map $\gamma\colon I^1 \to S^1$}$
ii. $p_\tau \circ f_{\tau'} = \text{constant map to base point, for $\tau' \neq \tau$}$.

Now, we almost done setting up results and rehashing definitions needed to make $\ccw_*(K)$ a chain complex. It remains to argue that the differential $\beta$ is of order $2$, i.e., that $\beta^2 = 0$. So consider the following three long exact sequences in relative homology. (This is Ulrike Tillmann's argument [@Til13, number 8.6].)

\begin{equation}
\xymatrix{
\cdots \ar[r]
    & H_{n+1}(\k {n+1}, \k n) \ar[r]^-{\delta_{n+1}}
    & H_n( \k n ) \ar[r] \ar@{=}[dl]
    & H_n( \k {n+1}) \ar[r]
    & \cdots\\
\cdots \ar[r] 
    & H_n(\k n) \ar[r]_-{j_n}
    & H_n(\k n, \k {n-1}) \ar[r]^-{\delta_n}
    & H_{n-1} (\k {n-1}) \ar[r] \ar@{=}[dl]
    & \cdots\\
& \cdots \ar[r]
    & H_{n-1}(\k {n -1}) \ar[r]_-{j_{n-1}}
    & H_{n-1} (\k {n-1}, \k {n-2}) \ar[r]
    & \cdots
}
\label{eq:order2}
\end{equation}

Notice $\beta_{n}  \beta_{n+1} = (j_{n-1}\delta_n)  (j_n \delta_{n+1}) = j_{n-1}  (\delta_n j_n)  \delta_{n+1} = 0,$ as $\delta_n j_n = 0$ by exactness of the middle row. 

### To prove

Let $K$ be a CW-complex. For all $n+1$ cells $\sigma$ and $n-1$ cells $\omega$, 
\begin{equation}\label{eq:boundaries}\sum_\tau [\omega : \tau][\tau : \sigma] = 0,\end{equation}
where $\tau$ ranges over all $n$-cells. 

### Proof

We require $\beta^2 = 0$, as in \eqref{eq:order2}. We also require $\beta(\sigma) = \sum_\tau [\tau: \sigma]\tau$, as discussed after \eqref{eq:incidencedef}. Whence 
\begin{align*}
\beta^2(\sigma) & = \sum_\tau [\tau : \sigma] \beta(\tau) & \text{($\beta$ is linear)}\\
    & = \sum_\tau [\tau : \sigma] \sum_\omega [\omega: \tau]\omega & \text{(evaluate)}\\
    & = \displaystyle{\sum_{\forall \tau, \omega}[\omega : \tau][\tau : \sigma] \omega}. & \text{($\ZZ$ is a commutative ring)}
\end{align*}
$\ccw_{n-1}(K)$ is the free abelian group whose basis is the set of $n-1$ cells in $K$. So if $\beta^2(\sigma) = 0$, then the coefficient $[\omega:\tau][\tau:\sigma]$ of each $n-1$ cell $\omega$ had better be zero. Thus, fixing $\omega$, we conclude $\sum_{\tau}[\omega : \tau][\tau : \sigma] \omega = 0$. \qedsymbol

### Remarks

i. Here's another way to remember \eqref{eq:boundaries} in the case that $K$ is finite. Take the matrices $[\beta_{n+1}]$ and $[\beta_n]$ representing $\beta_{n+1}$ and $\beta_n$ with respect to the *finite* bases for $\ccw_{n+1}(K)$ and $\ccw_n(K)$. Because $\beta$ is order two, $[\beta_{n}][\beta_{n+1}] = 0$ and \eqref{eq:boundaries} follows from matrix multiplication.

ii. If the coefficient $[\tau : \sigma]$ is the "incidence" of $\sigma$ to $\tau$, then the matrix $[\beta_n]$ suggests itself as the "incidence matrix" of the differential $\beta_n$. 

iii. However, the term "incidence matrix" is typically reserved for the following situation: Take the differential $\beta_1 \colon \ccw_1(K) \to \ccw_0(K)$. How does the matrix $[\beta_1]$ describe the *directed graph* whose vertices are $0$-cells in $\k 0$ and whose directed edges are $1$-cells in $\k 1$?

## References
