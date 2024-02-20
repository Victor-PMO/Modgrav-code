> ### **Part I: The reasoning and formulae**

We want first to consider the effects of the *gravitational Faraday Tensor* $F_{\mu\nu}$ on the dynamics of $2$ semi-relativistic (as in, "no background backreaction producing") test particles. To do so we have to jointly solve the following set of equations

$
\delta F = -\gamma j,\hspace{20pt}(1.1)
$
$
dF = 0,\hspace{31pt} (1.2)
$
alongside with the *sourced geodesic equation*

\begin{equation}
\frac{d^2 x^\mu}{ds^2} + \Gamma^\mu_{\alpha\beta}\frac{d x^\alpha}{ds}\frac{d x^\beta}{ds} = \frac{\vert m\vert}{m}F^{\mu\alpha}\frac{d x^\beta}{ds}g_{\alpha\beta}.\hspace{25pt} (2)
\end{equation}

Assuming a *stationany initial condition* expressed by $\boldsymbol{j} = 0$, we have that our initial $3-$vector $j^\mu_0$ will be of the form

\begin{equation}
j_0 = (\rho, 0, 0),
\end{equation}

with $\rho$ being the mass density distribution. We will hence have tp undergo the following steps in order to perform our numerical integration.

1. Solve the field equations [Eqs.(1.1, 1.2)] with initial $3-$vector $j^\mu_0$ (**just one numerical integration step!**)
2. Plug this first step result into Eq.(2) to find the positions and velocities $\left(x^\mu, \frac{d x^\mu}{ds}\right)$.
3. Use the fact that
\begin{equation}
j^\mu = \rho \frac{d x^\mu}{ds},
\end{equation}
to thus obtain the **new** first step current density $3-$vector.
4. Solve Eqs.(1.1, 1.2) with the new $j^\mu$ from Step 3. **Again, perfoming a single step integration**
5. Iterate Steps 1 through 4 untill the final integration time is achieved.

Let's get a bit more concrete now. If we write Eq.(1.1) in coordinates (upon having used Eq.(1.2) to deduce that $F = -dA$ for some $A\in \Lambda^1(\mathbb{R}\times \mathbb{S}^2)$) we shall find that, under the *Lorentz gauge* assumption, expressed as

$$
\begin{equation}
\nabla_\nu A^\nu = 0, \hspace{25pt} (3)
\end{equation}
$$
we end up with the following:

$$
\begin{equation}
R^\mu_\nu A^\nu + \nabla_\nu\nabla^\nu A^\mu = \gamma j^\mu. \hspace{25pt} (4)
\end{equation}
$$
Furthermore, notice that the Laplace-like term on Eq.(4) can be written in the following way

$$
\begin{equation}
\nabla_\nu\nabla^\nu A^\mu = \partial^\nu\partial_\nu A^\mu + \partial^\beta \Gamma^\mu_{\sigma\beta}A^\sigma + 2 \Gamma^\mu_{\sigma\beta}\partial^\beta A^\sigma - g^{\beta\nu}\Gamma^\sigma_{\beta\nu}\partial_\sigma A^\mu + g^{\beta\nu}A^\sigma(\Gamma^\alpha_{\sigma\beta}\Gamma^\mu_{\alpha\nu} - \Gamma^\mu_{\sigma\alpha}\Gamma^\alpha_{\beta\nu}), \hspace{20pt} (5)
\end{equation}
$$
which althought seamingly makes the computations harder to be done, it is actually a necesarry step to take if we want to do numerics.

`Notation`: $\partial^\beta = g^{\beta\alpha}\partial_\alpha$



