---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# layout: default
layout: post
# title: "Pseudo-Hamiltonian Neural Networks 2: Electric Boogaloo"
title: ""
date: 2025-07-21 10:01:37 +0200
categories: jekyll update
---

# Pseudo-Hamiltonian Neural Networks for Learning (2+1)-Dimensional Partial Differential Equations

## Abstract

Pseudo-Hamiltonian neural networks (PHNN) were recently introduced for learning Partial Differential Equations (PDEs), and fall under a broader category of hybrid machine learning models that combine data driven machine learning with mathematical descriptions of the systems.
Here, we extend the method to PDEs with 2 dimensions in space and one in time.
The resulting model is comprised of up to three neural networks, modelling conservative, dissipative and external forces, which can be inspected separately to gain insight into the system.

## Additional figures

<!-- Now we only need to get math working.

$$
\begin{align*}
    E &= mc^2 \\
    e^{i \pi} + 1 &= 0
\end{align*}
$$

It works, locally atleast.

By pseudo-Hamiltonian PDEs, we refer to the class of partial differential equations that can be written on the form

$$
    u_t = S \frac{\delta\mathcal{H}}{\delta u}[u] - R \frac{\delta\mathcal{V}}{\delta u}[u] + f.
$$

Does inline math like $a^2 + b^2 = c^2$ work? -->

### Zakharov--Kuznetsov equation

The Zakharov--Kuznetsov equation is a generalization of the Korteweg-de Vries equation to two spatial dimensions, and is given by

$$
    u_t + \eta \, u_x u + \gamma^2 ( u_{xxx} + u_{xyy} ) = 0.
$$

We consider here the case where $\eta = 6$ and $\gamma = 1$.
As the equation is Hamiltonian, we here inform the network that there are no dissipative or external forces, and the network learns the Hamiltonian and the skew-symmetric operator.

![Gif of the Zakharov-Kuznetsov equation](imgs/zk_surface_animation_transparent.gif)

### Cahn--Hilliard equation

The Cahn--Hilliard equation models the phase separation of a binary fluid, and is given by

$$
    u_t = \Delta \! \left( \nu u + \alpha u^3 + \mu \Delta u \right),
$$

where $\Delta$ is the Laplacian operator.
Here, we consider the case where $\nu = -1.0$, $\alpha = 1.0$ and $\mu = -0.001$.
The model is informed that there are no conservative or external forces, and the network learns the dissipative integral and the positive semi-definite operator.

![Gif of the Cahn-Hilliard equation](imgs/cahn_hilliard_resized.gif)

### Heat equation

The heat equation is simply given by

$$
    u_t = \alpha \Delta u,
$$

with $\alpha = 0.01$.
The model is informed that there are no conservative or external force, and that the $R$ operator is identity.
The network therefore only learns the dissipative integral.

![Gif of the Heat equation](imgs/heat_equation_resized.gif)

Note that while the solution goes to zero, the order of magnitude of the difference decreases.

For the heat equation, we trained six different models, each with their distinct training data.
The models were then evaluated on an unseen initial condition, giving varying results.
As the numerical solution approaches zero, we see that the relative error increases rapidly for some of the models.
In order to make sense of this, note that the $L^2$ errors for models 2 and 3 start increasing linearly after approximately $t = 4$, while the $L^2$ norm of the solution is decreasing exponentially.

We see that this corresponds to the mean values of the models diverging from zero.

<div style="text-align: center; margin: 20px 0">
  <img
    src="imgs/heat/relative_errors.png"
    alt="Relative errors"
    style="width: 45%; max-width: 550px"
  />
  <img
    src="imgs/heat/l2_errors.png"
    alt="L2 errors"
    style="width: 45%; max-width: 550px"
  />
</div>

<div style="text-align: center; margin: auto">
  <img
    src="imgs/heat/l2_norms.png"
    alt="L2 norms"
    style="width: 45%; max-width: 550px"
  />
  <img
    src="imgs/heat/mean_values.png"
    alt="Mean values"
    style="width: 45%; max-width: 550px"
  />
</div>

## Details

For additional details about the method, we refer the reader to the original paper [Pseudo-Hamiltonian neural networks for learning partial differential equations](https://doi.org/10.1016/j.jcp.2023.112738).
When completed, this work will be added to the [`phlearn` GitHub repository](https://github.com/SINTEF/pseudo-hamiltonian-neural-networks).
If you are interested in getting notified when our paper is available, please fill out the form below.

<details>
  <summary>
    Get notified when the paper is available
</summary>
  <iframe
    class="nettskjema-iframe"
    src="https://nettskjema.no/a/535090?embed=1"
    title="Get notified when our paper is available"
    frameborder="0"
    width="100%"
  ></iframe>
</details>

<!-- If the form is not loading, refer to the link here: [Link to the form](https://nettskjema.no/a/535090). -->
