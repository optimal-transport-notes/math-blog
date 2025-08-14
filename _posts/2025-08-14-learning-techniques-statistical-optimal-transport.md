---
layout: post
title: "Learning techniques from statistical optimal transport"
date: 2025-08-14
categories: [optimal-transport, learning]
---

Statistical optimal transport (OT) provides a powerful framework for comparing probability distributions and has become an important tool in modern statistics and machine learning.  Classical optimal transport originated in the work of Monge and Kantorovich, which formulate the problem of moving mass efficiently between distributions【741586441947269†L63-L74】.  Modern OT introduces the **Bures metric** for Gaussian distributions and explores **dual** and **dynamic** formulations that lead to gradient flows on the space of probability measures【741586441947269†L63-L74】.  A recent MIT news article describes how the field has matured; the new book *Statistical Optimal Transport* collects material central to applications in statistics and machine learning and is designed to be accessible to applied mathematicians and computer scientists【204403613854785†L41-L59】.  The notes in this blog draw from that perspective.

## Key learning techniques

### Entropic regularization

A central algorithmic idea in modern OT is **entropic regularization**, which adds an entropy term to the transport cost.  This leads to the **Sinkhorn algorithm**, which is computationally efficient and differentiable.  Entropic regularization not only accelerates numerical solvers but also enables gradient-based learning in deep neural networks.  When training generative models, entropic-regularized Wasserstein distances can be used to compare generated and target distributions.

### Semi‑discrete and linear‑programming solvers

Optimal transport can be solved as a linear program, but in high dimensions this becomes expensive.  **Semi‑discrete solvers** exploit structure where one measure is continuous and the other is discrete, while **entropic regularization** yields iterative scaling methods like Sinkhorn.  These solvers are used to estimate transport plans from sample data.

### Gradient flows and Bures metric

The **Bures metric** is an OT‑based distance between Gaussian distributions; it allows closed‑form formulas for transport maps.  More generally, OT defines gradient flows on the space of probability measures.  These flows can be used to design optimization algorithms for machine learning—e.g., training neural networks via Wasserstein gradient flows and understanding token dynamics in Transformers【741586441947269†L63-L74】.

### Applications to generative models

Optimal transport is closely connected to modern generative models.  Wasserstein distances are used to train **Generative Adversarial Networks (GANs)** and **diffusion models** by comparing model outputs with data distributions.  OT provides a geometric interpretation of these models and suggests new training objectives.

## Looking ahead

These notes will continue exploring mathematical foundations (Monge, Kantorovich, Brenier’s theorem), efficient numerical algorithms (Sinkhorn iterations, semi‑discrete solvers), and applications to generative modelling and transformers.  For a comprehensive introduction, the book *Statistical Optimal Transport* offers exercises and detailed explanations【204403613854785†L41-L59】.  I hope these posts help demystify the tools and inspire further exploration into this fascinating intersection of probability, geometry, and learning.
