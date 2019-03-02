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

This problem is set from Bredon [@Bre93, number IV.11.12]; it produces a combinatorial description of the differential between the chain groups of a CW-complex.

## What is given

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

We may define a chain complex $\ccw_*(K)$ on the CW structure as follows:

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

In \eqref{eq:beta}, the boundary map $\delta_n$ arises from the long exact sequence for the pair $(\k n, \k{n-1})$, and the map of relative homology groups $j_{n-1} \colon H_{n-1} (\k{n-1}) \to H_{n-1} (\k{n-1}, \k{n-2})$, is induced by the inclusion of skeleta $j \colon (\k {n-1}, \emptyset) \hookrightarrow (\k{n-1}, \k{n-2}).$
    
From lecture [@Bea19, number 1.11.3], we know $\delta_n$ respects the attaching maps, e.g., for an $n$-cell $\sigma$ with attaching map $f_{\partial\sigma}$, $$\delta_n [I^n_\sigma] = [f_{\partial \sigma} ( \partial I^n_\sigma )].$$ 
And so it turns out the differential $\beta_n$ can also be described with incidence^[I am fond of calling $[\sigma : \tau]$ the *incidence of $\sigma$ to $\tau$*.] numbers [@Til13, number 8.5]. For an $n$-cell $\sigma$ and an $n-1$ cell $\tau$, define
\begin{equation}
[\sigma : \tau] := \text{deg}\bigg( \xymatrix @R-1.8pc{
    S^{n-1} \ar[r]^{f_{\partial\sigma}} \ar@2{~}[d]
    & \k {n-1} \ar[r] \ar@/_2.0pc/^-{p_\tau}[rrr]
    & \k{n-1} / \k{n-2} \ar[r]^-{\approx}
    & \vee S^{n-1} \ar[r]^{\text{find $\tau$}}
    & S^{n-1} \ar@2{~}[d]\\
    \partial I^n_\sigma & & & & I^{n-1}_\tau / \partial I^{n-1}_\tau
}\bigg).
\label{eq:incidencedef}
\end{equation}
Three comments. First, we will take for granted that the rule $\sigma \mapsto \sum_\tau [\sigma : \tau] \tau$ for generators $\sigma$ in $\ccw_n(K)$ extends linearly to match the differential $\beta_n$ as defined in \eqref{eq:beta}. So write $\beta(\sigma) := \sum_\tau [\sigma : \tau] \tau$. Second, all but finitely many terms in the sum $\sum_\tau [\sigma : \tau]\tau$ must be zero because the compact set $\partial I^n_\sigma$ is attached by $f_{\partial \sigma}$ to a *compact* subset of $\k {n-1}$. Third, the projection $p_\tau$ in \eqref{eq:incidencedef} is the unique map $p_\tau \colon \k {n-1} \to S^{n-1}$ satisfying:

i. $p_\tau \circ f_\tau = \gamma_{n-1} = \text{smash product $\gamma \wedge \cdots \wedge \gamma$ of $n-1$ copies of the quotient map $\gamma\colon I^1 \to S^1$}$
ii. $p_\tau \circ f_{\tau'} = \text{constant map to base point, for $\tau' \neq \tau$}$.

Now, we almost done setting up results and rehashing definitions needed to consider $\ccw_*(K)$ as a chain complex. It remains to argue that the differential $\beta$ is order $2$, i.e., that $\beta \circ \beta = 0$. So consider the following three long exact sequences in relative homology.



## What needs to be shown

## References
