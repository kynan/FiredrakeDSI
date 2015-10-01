---
layout: layout
title: Firedrake
---

## The mathematics is the code

{% highlight python %}
from firedrake import *

mesh = UnitSquareMesh(100, 100)
V = FunctionSpace(mesh, "CG", 1)
W = V*V
gamma = Constant(0.005)
D = Constant(10)
q, v = TestFunctions(W)
u = Function(W)
u0 = Function(W)

phi, mu = split(u)
phi0, mu0 = split(u0)
phi = variable(phi)
f = 10*(phi**2 - 1)**2
dfdphi = diff(f, phi)
theta = 0.5
mu_theta = (1-theta)*mu0 + theta*mu
dt = 5e-6

F = ((phi - phi0)*q + dt*D*dot(grad(mu_theta), grad(q)) + 
     (mu - dfdphi)*v - gamma*dot(grad(phi), grad(v)))*dx

for _ in range(200):
    u0.assign(u)
    solve(F == 0, u)
{% endhighlight %}
