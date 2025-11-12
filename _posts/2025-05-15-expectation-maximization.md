---
layout: post
title: The EM Algorithm
date: 2025-05-15
---
I start my writings with an algorithm that I believe is rather simple yet elegant, and is a foundation for many applications in statistics and machine learning. The expectation maximization algorithm (or EM for short) estimates the maximum likelihood (or maximum a posteriori) estimates of parameters when data is unobserved. At face value, it sounds daunting. How can you estimate parameters when things are missing? You will see later that it boils down to initialization and iterative swapping between expecting and maximizing.

## E and M
Beginning with an overview of the steps of this algorithm, we can think if it as three steps, in which we iteratively repeat two of them. We have:
1. **Initialization:** Randomly select starting parameters  $\theta^{0}$
2. **E-Step:** Given parameters, infer the posterior of the hidden data:

	$$q^{(t)} = \underset{q}{\operatorname{argmax}}\mathcal{L}(q, \theta^{(t-1)})$$
3. **M-Step:** Given that posterior, learn new parameters that fit the data:

	$$\theta^{t} = \underset{\theta}{\operatorname{argmax}}\mathcal{L}(q^{(t)}, \theta)$$
4. **Iterate:** Alternate E and M until the heat death of the universe (or convergence)

