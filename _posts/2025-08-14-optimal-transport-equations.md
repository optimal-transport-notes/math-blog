---

layout: post
title: "Optimal transport equations example"
date: 2025-08-14
categories: [optimal-transport, mathjax]
---

In this post we demonstrate how to write LaTeX equations in a Jekyll blog using the Lagrange theme with MathJax. The core optimal transport problem seeks a map \(T\) pushing a source distribution \(\mu\) onto a target \(\nu\) and minimizing the cost \(c(x, y)\):

\[
\min_{T_\ast \mu = \nu} \int c(x,T(x)) \, d\mu(x).
\]

This is known as the **Monge formulation**. The **Kantorovich relaxation** replaces the transport map with a joint distribution \(\gamma\) on \(X \times Y\) with marginals \(\mu\) and \(\nu\):

\[
\min_{\gamma \in \Gamma(\mu,\nu)} \int_{X \times Y} c(x,y)\, d\gamma(x,y),
\]

where \(\Gamma(\mu,\nu)\) is the set of couplings with marginals \(\mu\) and \(\nu\).

An important computational approach is **entropic regularization**, which adds an entropy term to the objective:

\[
\min_{\gamma \in \Gamma(\mu,\nu)} \int c(x,y)\, d\gamma(x,y)
+ \varepsilon \mathrm{KL}(\gamma \Vert \mu \otimes \nu).
\]

Here \(\mathrm{KL}(\gamma \Vert \mu \otimes \nu) = \int \log\!\bigg(\frac{d\gamma}{d\mu \otimes d\nu}\bigg) \, d\gamma\) is the Kullback\u2013Leibler divergence, and \(\varepsilon > 0\) controls the strength of the regularization. The resulting problem can be solved efficiently using the **Sinkhorn algorithm**.

This example shows that MathJax renders display equations between `$$` or `\[\]` and inline equations between single dollar signs. Use it to write your own derivations and proofs.
