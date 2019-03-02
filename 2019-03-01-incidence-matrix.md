---
title: Incidence numbers in Cellular Homology
author: 
- Colton Grainger (scribe)
- Shen Lu (presenter)
date: 2019-03-01
bibliography: /home/colton/coltongrainger.bib
xy: true
---

\providecommand{\ccw}{C^{\text{CW}}}
\providecommand{\k}[1]{K^{( #1 )}}

This problem is set from Bredon [@Bre93, number IV.11.12]; it produces a combinatorial description of the differential operator between free groups on a CW-complex.

*Given*. Let $K$ be a CW-complex, with $n$-skeleton $\k n$ for $n \ge 0$. Assume $\k{n}$ contains an open neighborhood around the closed subset $\k {n-1}$ that deform retracts to onto $\k {n-1}$. With this assumption, one may show that

- the relative homology $H_*(\k n, \k {n-1})$ is isomorphic to the reduced homology $\tilde{H}_*(\k n / \k {n-1})$,
- the quotient space $\k n / \k {n-1}$ is a wedge of spheres $\vee S^n$, and thus
\begin{equation}
\xymatrix{
H_*(\k n, \k{n-1}) \ar[r]^-{\cong} 
    & \tilde{H}_*(\k n / \k{n-1}) \ar[r]^-{\cong}_-{\text{h.a.}}
    & \tilde{H}_*(\vee S^n) \ar[r]^-\cong
    & \displaystyle{\bigvee_\text{$n$-cubes of $\k n$} \tilde H_*(S^n)}
}
\label{eq:ncubes}
\end{equation}

To define the chain complex $\ccw_*(K)$, for each $n \ge 0$:

- Let the chain group $\ccw_n(K)$ be  $H_n(\k n, \k {n-1})$.

    - This is the free abelian group in \eqref{eq:ncubes} on the set of $n$-cubes attached to $\k {n-1}$ to form $\k n$.

- Let the differential $\beta_n \colon \ccw_n(K) \to \ccw_n(K)$ be the composite 
\begin{equation*}
\xymatrix{
H_n(\k n, \k {n-1}) \ar[r]^-{\delta_n} \ar@/^2.0pc/_-{\beta_n}[rr] 
    & H_{n-1}( \k {n-1} ) \ar[r]^-{j_{n-1}} 
    & H_{n-1}( \k {n-1},\k {n-2}),
}
\end{equation*}

    - where the inclusion $j \colon \k {n-1} \hookrightarrow (\k{n-1}, \k{n-2})$ induces the map of relative homology groups $$H_{n-1} (\k{n-1}) \xrightarrow{j_{n-1}} H_{n-1} (\k{n-1}, \k{n-2}),$$
    - and $\delta$  arises from the long exact sequence for the pair $(\k n, \k{n-1})$. (See \ref
    
Note that $\delta$ respects the attaching maps $\delta [I^n_\alpha] = [f_{\partial \alpha} \partial I^n_\alpha]$.

## References
