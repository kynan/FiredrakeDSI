---
layout: layout
title: Firedrake
---

## Mathematics is the language of simulation

### The Cahn-Hilliard equation: a model of phase separation

$$
\begin{aligned}
F[\phi(x, t)] &= \int \overbrace{\alpha \phi^2 + \beta \phi^4 + \epsilon}^{\text{Landau potential}} + \underbrace{\frac{\gamma}{2} |\nabla\phi|^2}_{\text{interface penalty}}\,\mathrm{d}x & \text{Free energy}\\
\mu = \frac{\delta F}{\delta \phi} &= 2\alpha\phi + 4\beta\phi^3 - \gamma\nabla^2\phi & \text{Chemical potential}\\
\frac{\partial \phi}{\partial t} &= \nabla \cdot D(\phi) \nabla \mu & \text{Continuity}
\end{aligned}
$$

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$'], ['\\(','\\)']]
    }
  });
  MathJax.Hub.Configured();
</script>
<script type="text/javascript"
  src="//cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
