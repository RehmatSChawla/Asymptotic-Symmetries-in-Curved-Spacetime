---
tags:
  - AGR
---

> [!def] Global Symmetry
> Consider $\mathcal L[\Phi,\partial_\mu\Phi,\dots]$ Lagrangian density with a transformation $\delta_Q\Phi=Q$, $Q$ being a local function. This transformation is a symmetry if the Lagrangian changes only by a total derivative: $\delta_Q\mathcal  L = dB_Q$, $B_q = B^\mu_Q(d^{n-1}x)_\mu$.

> [!def] Gauge Symmetry
> A symmetry depending on arbitrary spacetime functions $Q = R[F]$, $F=(f^\alpha)$. An (on-shell) equivalence class can thus be defined on the set of symmetries by collecting those differing only by gauge transformations:$$Q\sim Q+R[F]$$
> Classes $[Q]$ are called the global symmetries, with gauge symmetry being trivial ones.

Essentially, a gauge symmetry is one arising from various field configurations having the same physical observables.

> [!def] Noether Current
> Define a conserved current as an on-shell $n-1$ form, so $dj\approx 0$. For arbitrary $n-2$ forms $K$, we can again define equivalence classes$$j\sim j+dK$$The class $[j]$ is called a Noether current.

Gauge symmetries are the degeneracies of the Lagrangian, the redundancies in our description of the system. Their is a one-to-one correspondence between these symmetries and the Noether identities obeyed by the Lagrangian. Their corresponding Noether currents vanish on-shell, except for the boundary term $K$.

>[!tip] Noether's first theorem
>There exists a one-to-one correspondence between global symmetries and Noether currents. The currents associated with gauge symmetries are trivial - the Noether identities.

We can then explicitly construct the Noether currents too,$$\begin{gather}\delta_Q \mathcal L = \delta_Q \Phi \partial_\Phi\mathcal L + \delta_Q (\partial_\mu\Phi) \partial_{(\partial_\mu\Phi)} \mathcal L+\dots\\
= Q \underbrace{\left( \partial_\Phi\mathcal L -\partial_\mu \partial_{(\partial_\mu\Phi)} \mathcal L +\dots\right)}_{\frac{\delta \mathcal L}{\delta \Phi}} + \partial_\mu\left(Q \partial_{(\partial_\mu\Phi)} \mathcal L+\dots \right)\end{gather}$$Since $\delta_Q\mathcal  L = dB_Q$, we can combine the total derivative terms into $\partial_\mu j^\mu_Q = dj_{Q}$, which will then equal $Q\frac{\delta\mathcal L}{\delta\Phi}$ - which is 0 on-shell, hence the current is conserved on-shell.

>[!tip] Noether Representation Theorem
>The Noether currents form a representation of the symmetries, when you define the bracket as$$\begin{align}\{j_{Q_1},j_{Q_2}\} &= \delta_{Q_1}j_{Q_2}\\ &\approx j_{[Q_1,Q_2]}\end{align}$$where $[Q_1,Q_2]= \delta_{Q_1}Q_2 - \delta_{Q_2}Q_1$.
>>[!abstract]+ Proof
>>Operate $\delta_{Q_1}$ on the defining equation for the Noether current of $Q_2$. We'll use the fact that $[\delta_Q,\partial_\mu]=0$ to write the RHS as $d\delta_{Q_1}j_{Q_2}$.
>>For the LHS, note that commutation relation between the variational derivative and the variation due to a transformation $Q$:$$\left[\delta_Q,\frac{\delta}{\delta\Phi}\right]f = \sum_{k\ge 0} (-1)^{k+1} \partial_{\mu_1}\dots\partial_{\mu_k}\left(\frac{\partial Q}{\partial\Phi_{,\mu_1\dots\mu_k}}\frac{\delta f}{\delta\Phi}\right)$$
>>Also note that for a total derivative $f=dK$, the variational derivative is $\frac{\delta f}{\delta \Phi} =0$.
>>Using these two, write the LHS as:$$\begin{align}\delta_{Q_1}\left(Q_2\frac{\delta \mathcal L}{\delta\Phi}\right) &= \delta_{Q_1} Q_2 \frac{\delta \mathcal L}{\delta\Phi} + Q_2 \cancel{\frac{\delta }{\delta\Phi}(\underbrace{\delta_{Q_1}\mathcal L}_{dB_{Q_1}}}) - Q_2\sum\dots
>>\end{align}$$
>>The rest of the proof is too complex, so I will complete it later.

In the above proof, we required the:
>[!tip] Algebraic Poincare Lemma
>Let $[\alpha^n]$ denote the equivalence class of n-forms relating $\alpha^n \sim \alpha^n + d\beta^{n-1}$, then the cohomology class for an operator $d$ is $$
>H^p(d) = \begin{cases}[\alpha^n]& p=n\\ 0 &0\le p\le n\\ \mathbb R &p=0 \end{cases}$$

For further details, refer to [[Fibre Bundles and Jet Bundles]].

>[!def] Noether Charge
>For an $n-1$ dim spacelike $\Sigma$ with boundary $\delta\Sigma$,
>$$\begin{gather} H_Q[\Phi] := \int_\Sigma j\\H'_Q[\Phi] = \int _\Sigma (j+dK) = H_Q[\Phi] + \cancelto{0}{\int_{\delta\Sigma} K}\end{gather}$$Where the Stokes theorem was used.
>Thus the Noether charge is some idea of a space-distributed quantity which is well-defined for a Noether current as an equivalence class.
>Furthermore, it is conserved in time. Consider spacelike surfaces $\Sigma_i:=(t_i=0)$, then (denoting by $\Sigma_2-\Sigma_1$ the volume enclosed by them) $$H_Q[\Phi](t_2)-H_Q[\Phi](t_1) = \int_{\Sigma_2}j-\int_{\Sigma_1}j = \int_{\Sigma_2-\Sigma_1} dj \approx 0$$Note, this proof does require currents to vanish at infinity.

Like the currents, the charges too form a representation of the global symmetry algebra, and the proof too follows from the statement for the currents:
$$\begin{gather}\{H_{Q_1},H_{Q_2}\} := \delta_{Q_1}H_{Q_2} = \int_{\Sigma} \delta_{Q_1}j_{Q_2}\\\implies \{H_{Q_1},H_{Q_2}\}\approx H_{[Q_1,Q_2]}\end{gather}$$
> [!Def] Noether Identities
> Consider $R[F]\tfrac{\delta \mathcal L}{\delta\Phi} = \partial_\mu j^\mu_F$. For a gauge symmetry, expand $R[F]$ in the derivatives of $f^\alpha$:$$R[F]=R_\alpha f^\alpha + R_\alpha^\mu\partial_\mu f^\alpha + R^{(\mu\nu)}_\alpha \partial_\mu\partial_\nu f^\alpha +\dots $$
> And then write the LHS as $f^\alpha R^\dagger_\alpha$, $R^\dagger_\alpha=\sum\limits_{n=0}(-1)^n \partial_{\mu_1}\dots\partial_{\mu_n} \left(R_\alpha^{(\mu_1\dots\mu_n)}\tfrac{\delta\mathcal L}{\delta\Phi}\right)$ plus a total derivative $:= \partial_\mu S^\mu_F$.
> $$f^\alpha R^\dagger_\alpha = \partial_\mu(j^\mu_F - S^\mu_F)$$Now we can take the variational derivative wrt $f^\alpha$, cause $F$ is arbitrary, hence $$R^\dagger_\alpha= 0$$Thus each independent generator $f^\alpha$ creates such an identity. Also note that the identities satisfy off-shell as well.

> [!tip] Noether's Second Theorem
> $$R[F] \frac{\delta \mathcal L}{\delta \Phi} = dS_F$$Where $S_F = S^\mu_F(d^{n-1}x)_\mu$ is the (weakly) vanishing Noether current, $S_F\approx 0$.

>[!example] Example - General Relativity, $\textbf L = \frac 1 {16\pi G} (R-2\Lambda) \sqrt{-g}\ d^n x$ (n-form lagrangian)
>For a diffeomorphism generated by $\xi^\mu$, the Noether identity is the Bianchi identity $\nabla_\mu G^{\mu\nu}=0$ and the Noether current is $\mathbf S_\xi = \frac{-\sqrt{-g}}{8\pi G} \xi_\nu(G^{\mu\nu}+g^{\mu\nu}\Lambda)d^{n-1}x$.

^05981e

The Noether current associated with a gauge symmetry is trivial up to an exact $n-1$-form $dK$. We would like to define a conserved charge for gauge symmetries, but $H_F = \int_\Sigma j_F = \int_{\partial \Sigma} \mathbf  K_F$, and $K_F$ is arbitrary. 

>[!def] Definition - Reduciblity Parameter
> Parameters $\bar F$ of gauge transformations satisfying $R[\bar F]\approx 1$ (the transformation is identity on-shell).
> Two parameters are equivalent $(\bar F\sim\bar F')$ if they are the same on-shell $(\bar F\approx \bar F')$.
> For a lot of gauge theories (EM, Yang-Mills, GR in $\ge 3$dim), these equivalence classes can be mapped to the exact reducibility parameters $\bar F$ which give identity off-shell $R[\bar F]=1$.

>[!tip] Generalised Noether's Theorem
>$\exists$ a one-to-one mapping between the equivalence classes of reducibility parameters and the equivalence classes of conserved-on-shell $n-2$ forms: $$[\bar F]\xleftrightarrow{1-1}[\mathbf K]$$
>Where the equivalence class $[\mathbf K]$ is defined by $\mathbf K\sim\mathbf K'$ iff $\mathbf K \approx \mathbf K' + d\mathbf l$ for an $n-3$ form $\mathbf l$.
>So every identity transformation corresponds to a conserved $n-2$ form (both on-shell, and up to total derivatives). In other words, every symmetry gives a conserved $n-2$ form - this is not a conserved current, though, since currents are $n-1$ forms.
>A non-trivial conserved current is $j\not\approx dK$, and reference 86 of Ruzziconi's lectures restates this theorem as mapping to the equivalence classes of non-trivial conserved currents. 

^a9fe2a
With the Barnich-Brandt procedure, we can construct the n-2 forms explicitly. Given exact reducibility parameters $\bar F$, we know (Noether's second theorem) that $d\mathbf S_{\bar F}=0$ (the corresponding conserved current). While the details will have to wait until I cover appendix B of Ruzziconi's lectures, in essence there is a homotopy operator which allows the definition $\mathbf k_{\bar F} [\Phi,\delta\Phi]=-I^{n-1}_{\delta\Phi}\mathbf S_{\bar F}$, which then gives the conserved n-2 form $\mathbf K_{\bar F}[\Phi] = \int_\gamma \mathbf k_{\bar F}[\Phi,\delta\Phi]$.


>[!example] Linearised General Relativity
>$\bar\xi$, the diffeomorphism generators, are the exact reducibility parameters. They are the killing vectors of $g_{\mu\nu}$, so $\delta_{\bar\xi}g_{\mu\nu} = \mathcal L_{\bar\xi} g_{\mu\nu}=0$. There are no solutions to this for the general metric.
>
>Consider linearised gravity, $g_{\mu\nu} = \bar g_{\mu\nu}+h_{\mu\nu}$, then$$\delta_{\bar\xi}h_{\mu\nu}=\mathcal L_{\bar\xi}g_{\mu\nu}=0$$The exact reducibility parameters are the diffeomorphism generators (Killing vectors) of the background metric. For a minkowski background, these are the Poincare generators, so we can explicitly construct the n-2 form via the Barnich-Brandt procedure and integrate it over an n-2 sphere at infinity. The constants obtained thus are the ADM charges of linearised gravity.

