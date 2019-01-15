---
title: Introduction to Homology
author: Colton Grainger (MATH 6220 Topology 2)
date: 2019-01-14
bibliography: /home/colton/coltongrainger.bib
url: https://github.com/coltongrainger/fy19top2
---

## Problems due 2019-01-30

###

Let $X = \bigcup_{i\in I} X_i$ where the $X_i$ are the (disjoint) path components of $X$. Prove that $$H_*(X) \cong \bigoplus_{i\in I} H_*(X_i).$$

### 

Let $X$ and $Y$ be path connected spaces.

(a) Prove that any map $f \colon X \to Y$ induces an isomorphism $f_* \colon H_0(X) \xrightarrow{\cong} H_0(Y)$.

(b) Prove that any map $f \colon X \to X$ induces the identity on $H_0(X)$.

###

Use the Hurewicz theorem to solve the following problems:

(a) Compute $H_1(K)$ for the Klein bottle $K$.

(b) Compute $H_1$ of $X=\prod_{j \in J} X_j$ for topological spaces $X_j$ in terms of $H_1(X_j)$.

(c) Let $X_i$ with base points $x_i \in X_i$. Suppose that there are open sets $x_i\in U_i \subseteq X_i$ such that $x_i$ is a deformation retract of $U_i$. Show that $${H}_1 \left( \bigvee_{i\in I}  X_i \right)  \cong \bigoplus_{i\in I} {H}_1(X_i).$$

###

Let $f \colon X \to Y$ be a covering space of path connected spaces with $f(x_0) = y_0$. By the fundamental theorem of covering spaces, $f_{\#} \colon \pi_1(X,x_0) \to \pi_1(Y, y_0)$ is a monomorphism. Is $f_* \colon H_*(X) \to H_*(Y)$ also a monomorphism. Prove that it is, or give a counterexample.
