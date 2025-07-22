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

## Details

For additional details about the method, we refer the reader to the original paper [Pseudo-Hamiltonian neural networks for learning partial differential equations](https://doi.org/10.1016/j.jcp.2023.112738).
If you are interested in getting notified when our paper is available, please fill out the form below.

<script
    type="text/javascript"
    src="https://nettskjema.no/static/js/external-embedding.js"
></script>
<details>
    <summary style="cursor: pointer; font-weight: bold;">
        Show form to get notified when our paper is available
    </summary>
<iframe
    class="nettskjema-iframe"
    src="https://nettskjema.no/a/535090?embed=1"
    title="Get notified when our paper is available"
    frameborder="0"
    width="100%"
></iframe>
</details>

If the form is not loading, refer to the link here: [Link to the form](https://nettskjema.no/a/535090).

## Additional figures

Now we only need to get math working.

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

Does inline math like $a^2 + b^2 = c^2$ work?

### Zakharov-Kuznetsov equation

![Image title](imgs/zk_surface_animation_resized.gif)
