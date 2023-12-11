---
tags:
  - AGR
---
---
A course project for **PH 807 : Advanced General Relativity**

at the **Indian Institute of Technology Bombay**

in partial fulfilment of the requirements of the degree of
**Bachelors in Technology
Engineering Physics**

by **Rehmat Singh Chawla**
**200260039**

Supervisor:
**Prof. Vikram Rentala**

---
## Table of Contents
- [[#Introduction|Introduction]]
- [[#Defining the asymptotic group|Defining the asymptotic group]]
		- [[#Introduction#Geometric Approach|Geometric Approach]]
		- [[#Introduction#Gauge Fixing Approach|Gauge Fixing Approach]]
		- [[#Introduction#Hamiltonian Approach|Hamiltonian Approach]]
- [[#Gauge Fixing|Gauge Fixing]]
				- [[#Examples|Examples]]
- [[#Boundary Conditions|Boundary Conditions]]
	- [[#Boundary Conditions#Asymptotic Flatness in Bondi|Asymptotic Flatness in Bondi]]
			- [[#Hamiltonian Approach#Variation 1 (AF1)|Variation 1 (AF1)]]
			- [[#Hamiltonian Approach#AF2|AF2]]
			- [[#Hamiltonian Approach#AF3|AF3]]
	- [[#Boundary Conditions#Asymptotic (A)dS in FG & Bondi|Asymptotic (A)dS in FG & Bondi]]
		- [[#Asymptotic (A)dS in FG & Bondi#Asymptotically Locally (A)dS|Asymptotically Locally (A)dS]]
			- [[#Asymptotically Locally (A)dS#In the Fefferman-Graham Metric|In the Fefferman-Graham Metric]]
			- [[#Asymptotically Locally (A)dS#In the Bondi Gauge|In the Bondi Gauge]]
		- [[#Asymptotic (A)dS in FG & Bondi#Asymptotically AdS 1 (AAdS1)|Asymptotically AdS 1 (AAdS1)]]
				- [[#In the Bondi Gauge#Fefferman-Graham|Fefferman-Graham]]
		- [[#Asymptotic (A)dS in FG & Bondi#AAdS2|AAdS2]]
				- [[#In the Bondi Gauge#Fefferman-Graham|Fefferman-Graham]]
				- [[#In the Bondi Gauge#Bondi|Bondi]]
- [[#Solution Space|Solution Space]]
		- [[#Asymptotic (A)dS in FG & Bondi#Asymptotically locally $(A)dS_4$ with Fefferman-Graham|Asymptotically locally $(A)dS_4$ with Fefferman-Graham]]
		- [[#Asymptotic (A)dS in FG & Bondi#Asymptotically locally $(A)dS_4$ with Bondi|Asymptotically locally $(A)dS_4$ with Bondi]]
		- [[#Asymptotic (A)dS in FG & Bondi#Asymptotically Flat with Bondi|Asymptotically Flat with Bondi]]
- [[#Asymptotic Symmetry Algebras|Asymptotic Symmetry Algebras]]
		- [[#Asymptotic (A)dS in FG & Bondi#AAdS1 boundary conditions, FH gauge|AAdS1 boundary conditions, FH gauge]]
		- [[#Asymptotic (A)dS in FG & Bondi#AAdS1 boundary conditions, Bondi gauge|AAdS1 boundary conditions, Bondi gauge]]
- [[#Differential Forms|Differential Forms]]
- [[#Symmetries and Noether's Theorem|Symmetries and Noether's Theorem]]
- [[#Surface Charges|Surface Charges]]
	- [[#Surface Charges#Properties of Surface Charges|Properties of Surface Charges]]
		- [[#Properties of Surface Charges#Violations of these properties|Violations of these properties]]
- [[#Example: The BMS Group in 4D Spacetime|Example: The BMS Group in 4D Spacetime]]
	- [[#Example: The BMS Group in 4D Spacetime#Intuiting Supertranslations|Intuiting Supertranslations]]
	- [[#Example: The BMS Group in 4D Spacetime#The Bondi Metric in 4D|The Bondi Metric in 4D]]
	- [[#Example: The BMS Group in 4D Spacetime#Deriving Supertranslations|Deriving Supertranslations]]
- [[#Applications|Applications]]
	- [[#Applications#Holography|Holography]]
	- [[#Applications#Infrared Triangle|Infrared Triangle]]
	- [[#Applications#Black Hole Information Paradox|Black Hole Information Paradox]]
- [[#Modern Research on Asymptotic Symmetries|Modern Research on Asymptotic Symmetries]]
- [[#Bibliography|Bibliography]]
## Introduction
In a gauge theory - specifically those incorporating GR - the symmetry groups arising asymptotically at the boundary is what this topic is all about. In 4D GR, in addition to the Poincare group we get supertranslations, which combined are called the Bondi-Metzner-Sachs-van der Burg (BMS) group.
## Defining the asymptotic group

^3c4b63

The asymptotic group is intricately connected to the boundary conditions of the gauge theories.
#### Geometric Approach
Introduced by Penrose, the boundary conditions require certain data to be preserved at the boundary.
The weak definition of the asymptotic is a group isomorphic to the gauge transformations *induced on the boundary* which preserve this data. The strong definition is the quotient group of the data-preserving transformations by the trivial gauge transformations - the trivial are defined as those with vanishing (Noether) charges. The connection between these being that the trivial transformations are not those induced at the boundary, I suppose. ^aa489e
Since we do not refer to coordinates in these boundary conditions, it is a manifestly gauge invariant approach, but it has the flaw that the boundary conditions are rigid, and often defined *a posteriori* - you can't start from BCs and obtain the asymptotes.
#### Gauge Fixing Approach
Related to [[Gauge Invariance and Theories]].
Gauge fixing "quotients the field space" to eliminate redundancies in a gauge theory - mostly unphysical or "pure gauge" redundancies. ^fae226
However, the appropriate gauge fixing for a theory does not always remove all redundancy - see electromagnetism, where the Lorenz gauge $\partial_\mu A^\mu=0$ still allows $A_\mu\rightarrow A_\mu + \partial_\mu\beta$, as long as $\partial_\mu\partial^\mu \beta=0$.
After gauge fixing, the boundary conditions may be expressed in the chosen gauge.
Intuitively, gauge fixing is removing the pure gauge degrees of freedom - essentially the trivial ones with vanishing charges discussed above.
Similarly to above, the weak (strong) asymptotic group can be defined as the diffeomorphisms preserving the boundary conditions (with non-vanishing charges). But explicit coordinate expressions allow for flexibility in the boundary conditions, and gauge fixing is also local so global topological considerations are moot.
Consider the example of superrotations, an extension to BMS - they have poles at the celestial sphere, so the geometric approach would require a modified topology, a punctured celestial sphere - it just makes things difficult, as opposed to gauge fixing. But for any results of this approach, it is often needed to reproduce them with the geometric approach to show manifest gauge invariance.
#### Hamiltonian Approach
Perform calculations in a coordinate system - no gauge fixing needed - and study the symmetries at spatial infinity explicitly, with the trivial symmetries having charges vanishing identically over the phase space, and the asymptotic group being defined hence, the same way as in the other approaches (corresponding to the strong definitions).
## Gauge Fixing

> [!def]+ Gauge Symmetry
> $$
> S[\Phi] = \int_M \mathbf L[\Phi,\partial_\mu\Phi,\partial_\mu\partial_\nu\Phi,\dots] d^nx$$
> A gauge transformation with parameter functions $F=(f^\alpha)$:$$\begin{align}
> \delta _F \Phi &= R[F]\\
> &= \sum\limits_{k\ge0} R_\alpha^{\; (\mu_1\dots \mu_k)} \partial_{\mu_1} \dots\partial_{\mu_k} f^\alpha
> \end{align}$$
> The $R$s are local functions of the coordinates, the fields and their derivatives. This transformation is a symmetry if the lagrangian transforms as $\delta _F \mathbf L = d\mathbf B_F$, $B_F = B^\mu_F(d^{n-1}x)_\mu$ - a total derivative.

>[!info]+ Examples
>**Vacuum electrodynamics**
>$$\begin{gather}S[A] = \int_M \mathbf F\wedge *\mathbf F\\
>\mathbf F = d\mathbf A\\
>\delta_\alpha \mathbf A = d\alpha\end{gather}$$
>For arbitrary $\alpha$, this transformation is a symmetry.
>
>---
>**General Relativity**
>Use the Einstein-Hilbert action (optionally include cosmological constant $\Lambda$):
>$$\begin{gather}
>S[g] = \frac 1 {16\pi G} \int_M (R-2\Lambda) \sqrt{-g} d^n x\\
>\delta_\xi g_{\mu\nu} = \mathcal L_\epsilon g_{\mu\nu} \\=\xi^\rho \partial_\rho g_{\mu\nu} + g_{\mu\rho} \partial_\nu \xi^\rho+g_{\rho\nu} \partial_\mu \xi^\rho\end{gather}$$
>For every vector field $\xi^\mu$ which generates diffeomorphisms, this transformation (where $\mathcal L_\xi$ is the Lie derivative) is a symmetry.
>>*Sidenote*, the conditions for a vector field to generate diffeomorphisms are that it be complete, smooth, and proper (map compact to compact).

Worth noting is that these transformations have the common structure $\delta _F \Phi = R_\alpha f^\alpha + R^\mu_\alpha \partial_\mu f^\alpha$, involving at most first derivatives of the parameters.

>[!def] Gauge Fixing
>A constraint (generally algebraic or differential) on the fields to eliminate some part of the theory's redundancy, $G[\Phi]=0$ (a set of $n$ independent conditions).
>This constraint must be satisfiable by a field configuration reachable by a gauge transformation $(n\le \# f^\alpha)$, and to completely fix the gauge it must also use up all the available freedom $(n\ge \# f^\alpha)$ - hence it must have as many independent conditions $n$ as the number of independent parameters $f^\alpha$.

Note the common gauges used in
- **Electrodynamics**: Lorenz $(\partial^\mu A_\mu=0)$, Coulomb $(\partial^i A_i= 0)$, temporal $(A_0=0)$, axial $(A_3=0)$.
 Used when $\Lambda\neq 0$,$x^\mu = (\rho,x^\alpha)$ where $\rho$ is the expansion parameter, 0 at the spacetime boundary and positive in the bulk. The constraints:$$\begin{align}
		g_{\rho\rho} &= -\frac{(n-1)(n-2)}{2\Lambda\rho^2}\\ g_{\rho a}&=0\end{align}$$Where $\rho$ is a spacelike (timelike) for $\Lambda \lt 0 (\;\gt 0)$.
- **Gravity**: ^0ab336
	- **de Donder (Harmonic) gauge** : $\square x^\mu= \tfrac 1 {\sqrt{-g}}\partial_\nu (\sqrt{-g} \partial^\nu x^\mu) = 0$. This is equivalent to $\Gamma^\alpha_{\;\beta\gamma}g^{\beta\gamma}=0$, which is useful for working with gravitational waves, since it is also equivalent to $\partial_\gamma g^{\alpha\gamma} = \tfrac 12 \partial^\alpha g$, which in the linear gravity approximation and perturbed metric $g\mapsto g+h$ becomes $\partial_\gamma h^{\alpha\gamma} = \tfrac 12 \partial^\alpha h$.
	- **Fefferman-Graham gauge** : Used when $\Lambda\neq 0$,$x^\mu = (\rho,x^a)$ where $\rho$ is the expansion parameter, 0 at the spacetime boundary and positive in the bulk. $\rho$ is a spacelike (timelike) for$\Lambda \lt 0 (\;\gt 0)$. The constraints:$$\begin{align}
		g_{\rho\rho} &= -\frac{(n-1)(n-2)}{2\Lambda\rho^2}\\ g_{\rho a}&=0\end{align}$$
	- **Bondi gauge** : As the name suggests, this has special relevance to the symmetries we wish to study. Use coordinates $(u,r,x^A)$, where $x^A$ are the angular coordinates on the spatial unit $(n-2)$-sphere. Then the gauge:$$\begin{align}g_{rr}&=0\\g_{rA}&=0\\\partial_r\left(\frac{\det g_{AB}}{r^{2(n-2)}}\right)&=0\end{align}$$Which implies that $u$ labels the null hypersurfaces, $x^A$ the null geodesics in any single hypersurface, and $r$ the luminosity distance along a geodesic. The general metric becomes $$ds^2 = e^{2\beta} \frac Vr du^2 -2e^{2\beta} du dr + g_{AB} (dx^A - U^A du)(dx^B - U^B du)$$
	- **Newman-Unti gauge** : Similar to Bondi, $$\begin{align}g_{rr}&=0\\g_{rA}&=0\\g_{ru}&=-1\end{align}$$
>[!def] Residual Gauge Transformations
>Gauge transformations left over even after fixing the gauge - transformations with generators $F$ s.t. $\delta_F G[\Phi]=0$, $F$ being local functions parametrised by $(n-1)$ coordinates.
###### Examples
- For the Lorenz gauge, we know $\square \alpha=0$ permits $\delta_\alpha A_\mu=\partial_\mu \alpha$ transformations.
- Fefferman-Graham : The transformations generated by $\xi^\mu$ must have $\mathcal L_\xi g_{\rho\mu}=0,\mu=\rho,a$. The solutions of these are parametrised by $n$ arbitrary functions $(\sigma,\xi^a_0)$ of the $n-1$ coordinates $x^a$:$$
  \begin{align}
  \xi^\rho&=\sigma(x^a)\rho\\
  \xi^a &= \xi^a_0(x^b) + \frac{(n-1)(n-2)}{2\Lambda}\partial_b\sigma\int_0^\rho\frac{d\rho'}{\rho'}g^{ab}(\rho',x^c)\end{align}$$
- **Bondi gauge** : The residual transformations need to satisfy ($\omega$ an arbitrary function):$$\begin{gather}\mathcal L _\xi g_{rr} = 0\\\mathcal L_\xi g_{rA} =0\\
  g^{AB}\mathcal L_\xi g_{AB} = 4\omega(u,x^A)\end{gather}$$The solutions to these use the $n$ functions of $(u,x^A)$, $\omega,f,Y^A$, with $\partial_r f=\partial_r Y^A = 0$. Also note $g=\det g_{AB}$ and $\mathcal D_A$ is the covariant derivative using $g_{AB}$. $$\begin{gather}\xi^\mu=f\\
  \xi^A = Y^A + I^A \\
  I^A = -\partial_B f \int_r ^\infty dr' (e^{2\beta } g^{AB})\\
  \xi^r = -\frac{r}{n-2} (\mathcal D_A Y^A - 2\omega +\mathcal D_A I^A  - \partial_B f U^B +\tfrac 12 fg^{-1} \partial_u g)\end{gather}$$
## Boundary Conditions
In essence, requiring some constraints on the fields, in a neighbourhood of any given spacetime region. These are generally on the far-off *asymptotic region*, which again is often infinity (spacelike, timelike or null) but can be something else, like black hole horizons, as well.
Boundary conditions that are too strong - and hence bestow only a trivial asymptotic symmetry group - or too weak - giving divergent associated surface charges - are uninteresting. We want conditions endowing non-trivial symmetries with interesting charges (example properties are finite, integrable, conserved, generically non-vanishing.)
### Asymptotic Flatness in Bondi
One boundary condition - with multiple definitions and variations - is ***asymptotic flatness** at null infinity* $(r\rightarrow \infty)$. All variations have as preliminary the following at $(r\rightarrow \infty)$:
$$\begin{gather}
\beta = \mathcal o(1)\\
\frac{V}{r}= \mathcal o(r^2)\\
U^A = \mathcal o(1)\\
g_{AB} = r^2 q_{AB} + r C_{AB} +D_{AB} + \mathcal O(r^{-1})
\end{gather}$$
With $(n-2)$-dim symmetric tensors $q_{AB},C_{AB},D_{AB}$, functions of $(u,x^A)$. $q_{AB}$ in particular becomes the transverse boundary metric.
##### Variation 1 (AF1)
Fix the determinant of $q$ to some fixed (possibly time-dependent) volume element $\bar q$:
$$\sqrt q = \sqrt{\bar q}$$
##### AF2
Define $\mathring q_{AB}$ as the inherited $n-2$ unit sphere metric, and require $q_{AB}$ to be conformally related:$$q_{AB} = e^{2\phi} \mathring q_{AB}$$For $n=4$, this only needs a coordinate transformation to be satisfied (every metric on 2D is conformally flat).
##### AF3
The historical definition, and a sub-case of AF2, $$q_{AB} = \mathring q_{AB}$$Note the unique property of this definition to be asymptotically Minkowskian - leading orders of the metric tend to the Minkowski line element $ds^2 = -du^2 - 2dudr + r^2 \mathring q_{AB} dx^Adx^B$with $r\rightarrow\infty$.
### Asymptotic (A)dS in FG & Bondi
Recap [[(Anti) de Sitter Spaces|(Anti) de-Sitter Spaces]]. Briefly, they are maximally symmetric Lorentzian manifolds with a (negative) positive cosmological constant $\Lambda$ measuring the curvature of spacetime everywhere.
Now we consider some boundary conditions which constrain the spacetime to tend to, instead of flat, a curved (A)dS behaviour in the asymptotic region.
#### Asymptotically Locally (A)dS
The preliminary condition, which can be augmented in various ways.
##### In the Fefferman-Graham Metric
$$\begin{gather}g_{ab} = \mathcal O(\rho^{-2})\\
\Leftrightarrow g_{ab} = \tfrac 1 {\rho^2} g^{(0)}_{ab} + \mathcal o(\rho^{-2})  \end{gather}$$
This keeps the boundary metric $g^{(0)}_{ab}$ free, which differentiates asymptotically *locally* AdS from asymptotically AdS, the latter requiring the metric to tend to AdS on the whole boundary in the same coordinate system, which introduces the restriction that the induced boundary metric must be conformal to $\mathbb R\times S^{d-1}$.[^2]
Note the difference in big-O and little-o notation - big-O is asymptotically tight, it requires equality in asymptotic growth rate, whereas little-o does not.
##### In the Bondi Gauge
The above conditions expressed in the Bondi gauge become
$$g_{AB} = \mathcal O(r^2) = r^2 q_{AB} + \mathcal  o(r^2)$$
#### Asymptotically AdS 1 (AAdS1)
A subcase of AlAdS.
###### Fefferman-Graham
$$\begin{gather}
g^{(0)}_{tt} = \frac{2\Lambda}{(n-1)(n-2)}\\ 
g^{(0)}_{ta} = 0\\
\det g_{ab}^{(0)} = \bar q\frac{2\Lambda}{(n-1)(n-2)}\\
\end{gather}$$
Where $\bar q$ is any fixed (possibly time-dependent) volume form for the transverse $(n-2)$-dim space (not spacetime) in the boundary.
###### Bondi
$$\begin{gather}\beta = \mathcal o (1)\\
\frac V r = \frac{2r^2\Lambda}{(n-1)(n-2)} + \mathcal o(r^2)\\
U^A = \mathcal o(1)\\
\sqrt q = \sqrt{\bar q}\end{gather}$$
#### AAdS2
A subcase of AlAdS, dirichlet boundary conditions require $g_{ab}^{(0)}$ be fixed.
This is not very relevant for (A)dS spacetimes, however, since it restricts the bulk spacetime dynamics a little too strongly.
###### Fefferman-Graham
This is usually chosen to be the cylinder metric:
$$\begin{gather}g^{(0)}_{ab} dx^a dx^b =  \frac{2\Lambda}{(n-1)(n-2)} dt^2 + \mathring q _{AB} dx^A dx^B\end{gather} $$
$\mathring q _{AB}$ is the metric on the unit $(n-2)$-sphere, and as in Bondi, the capital indices are defined with $x^a = (t,x^A)$, taking values $\in[3,n]$.
###### Bondi
$$\begin{gather}\beta = \mathcal o(1)\\
\frac V r = \frac{2r^2\Lambda}{(n-1)(n-2)} + \mathcal o(r^2)\\
U^A = \mathcal o(1)\\
q_{AB} = \mathring q_{AB}
\end{gather}$$
Note how AAdS1 and AAdS2 were similar to AF1 and AF3 respectively.
Also note how the Bondi gauge is well-suited in both flat and (A)dS asymptotes, whereas the Fefferman-Graham isn't defined for asymptotically flat.
## Solution Space
Given a gauge fixing and boundary conditions, a field configuration $\tilde\Phi$ satisfying the boundary conditions and the Euler-Lagrange equations is a solution, and the set of all such is the solution space, parametrised by $\tilde\Phi\equiv \tilde\Phi(b)$, $b$ being arbitrary functions of $(n-1)$ coordinates, since the solution space should lose a degree of freedom after the constraints. $$
\begin{gather}\left. \frac{\delta\mathcal L}{\delta\Phi }\right|_{\tilde \Phi}=0\\G[\tilde\Phi]=0\end{gather}$$
#### Asymptotically locally $(A)dS_4$ with Fefferman-Graham
The Einstein equations give the following limiting behaviour:$$\begin{gather}
G_{\mu\nu} + \Lambda g_{\mu\nu} = 0\\
g_{ab} = \rho^{-2} g^{(0)}_{ab}  + \rho^{-1} g^{(1)}_{ab}  + g^{(2)}_{ab}+\rho g^{(3)}_{ab} + \mathcal O(\rho^2)
\end{gather}
$$ Note $g^{(i)}_{ab}\equiv g^{(i)}_{ab}(x^a)$, no $\rho$ dependence. $g^{(0)}_{ab}$ is named the boundary metric, and along with $g^{(3)}_{ab}$ are the only free parameters. Define the stress-energy tensor:$$ T_{ab} \equiv \frac{\sqrt{3|\Lambda|}}{16\pi G}g^{(3)}_{ab}$$
And use the Einstein equations to obtain (Using $D^{(i)}_{a}$ as the covariant derivative defined using $g^{(i)}_{ab}$):$$\begin{gather} g^{(0)}_{ab} T^{ab} = 0\\
D_a^{(0)} T^{ab} =0\end{gather}$$
Thus for $\Lambda\neq 0$, solution space is parametrised by:
- **AlAdS** boundary conditions: the 11 functions $g^{(0)}_{ab},T_{ab}$.
- **AAdS1** boundary conditions: the 7 functions $g^{(0)}_{AB},T_{ab}$.
- **AAdS2** boundary conditions: the 5 functions $T_{ab}$.
Always implicit that $T_{ab}$ satisfies the above constraints.
#### Asymptotically locally $(A)dS_4$ with Bondi
A diffeomorphism between the Bondi and Fefferman-Graham gauges has been worked out for asymptotically $(A)dS_4$ spacetimes in [^4],[^5]. This, combined with the validity of the Fefferman-Graham expansion, allows us to expand the functions in the metric in powers of $r$ even in the Bondi gauge:$$g_{AB} = r^2 q_{AB} + rC_{AB} + D_{AB} +\tfrac 1 r E_{AB} + \tfrac 1{r^2} F_{AB} +\mathcal O(r^{-3})$$. The defining condition of the Bondi gauge then implies the following:$$\begin{gather}g^{AB}\partial_r g_{AB} =4/r\\\implies 
\det g_{AB} = r^4 \det q_{AB}
\\ \implies q^{AB}C_{AB} = 0
\end{gather}$$And further conditions relating the other components of the expansion.
Using these results, we can solve the Einstein equations with this power-series ansatz. We obtain various constraints from the $rr,rA$ components on the arbitrary functions which make up the solution. These involve logarithmic terms, however those vanish for $\Lambda\neq 0$, highlighted by the $AB$ components of the Einstein equations.
The solution is parametrised by the 11 functions $\{\beta_0,U_0^A,q_{AB},\mathcal E_{AB},M,N^A\}_{\Lambda\neq 0}$, with the evolution of $M,N^A$ with respect to $u$ being constrained - hence the IVP is well-defined when given $\beta_0(u,x^C),U_0^A(u,x^C),\mathcal E_{AB}(u,x^C),q_{AB}(u,x^C),M(u_0,x^C),N^A(u_0,x^C)$. As with Fefferman-Graham, these reduce to 7 and 5 functions each in the AAdS1/2 boundary conditions : $\{q_{AB},\mathcal E_{AB},M, N^A\}$ with fixed $\det q_{AB}$, and  $\{\mathcal E_{AB},M, N^A\}$, respectively.
#### Asymptotically Flat with Bondi
Taking the limit $\Lambda\rightarrow 0$, the solutions are obtained:$$\begin{gather} G_{\mu\nu}=0\end{gather}$$The radial constraints are satisfied by $\beta_0 = 0, U_0^A = 0$ and the evolution constraint simplifies to $(\partial_u - l)q_{AB}=0$. The evolution constraints on $M,N^A$ remain unchanged. Various components like $C_{AB},\mathcal D_{AB},\mathcal E_{AB}$ become unconstrained or only time-evolution constrained, and hence are more free parameters. In particular, we need to impose $D^A\mathcal D_{AB}=0$ to remove logarithmic terms from the expansion for $U^A(r)$.
Note that the assumption of $g_{AB}$ being analytic in $r$ and the power series expansion being valid, while unrestrictingly true for the (A)dS limit, is slightly restrictive for the flat limit.
As with (A)dS, different boundary conditions restrict the solution space in different ways.
For now, I have elected to avoid the details of this section on solution spaces and focus on the following sections. I may revisit it later.
## Asymptotic Symmetry Algebras
Recall that asymptotic symmetries are the residual gauge transformations which preserve given boundary conditions. They are called *on-shell* when they do so, since they are closed transformations on the solution space. Considering the solution space as a subset of the larger parameter space traversed by all the possible gauge transformations, the on-shell transformations will be tangent to the solution space at every point (any normal component will exit the solution space).
The generators of these symmetries are called *asymptotic Killing vectors* in gravity contexts.

> [!def] Asymptotic Symmetry Algebra
> The gauge symmetry generators being $F$, the gauge transformations (on the solution space) being $R[F]$, their infinitesimal actions on the fields being $\delta_{F}$, and $\approx$ denoting on-shell equality,$$\begin{align}[R[F_1],R[F_2]] &= \delta_{F_1} R[F_2] - \delta_{F_2}R[F_1]\\
> &\approx  R[[F_1,F_2]_A]\end{align}$$
> The bracket of gauge symmetry generators involves an arbitrary skew-symmetric bi-differential operator $C$. The two other terms account for the possible field-dependence of these generators. This bracket satisfies the Jacobi identity and so the symmetry generators do form a (solution-space-dependent) Lie algebra.$$\begin{align}[F_1,F_2]_A &= C(F_1,F_2) - \delta_{F_1}F_2 + \delta_{F_2}F_1\\
> C(F_1,F_2) &= \sum\limits_{k,l\ge 0} C_{[\alpha,\beta]}^{(\mu_1\dots\mu_k)(\nu_1\dots\nu_l)} \partial_{\mu_1}\dots\partial_{\mu_k}F_1^\alpha \cdot \partial_{\nu_1}\dots\partial_{\nu_l}F_2^\beta
> \end{align}$$
> The algebra of the gauge transformations implies that $[\delta_{F_1},\delta_{F_2}]\Phi = \delta_{[F_1,F_2]_A}\Phi$ - the infinitesimal actions of the symmetries on the fields creates a representation of the generator Lie algebra.

Consider the preliminary (A)dS boundary conditions in either gauge - neither of them add any further constraints to the residual gauge diffeomorphisms derived earlier.
#### AAdS1 boundary conditions, FH gauge
We discussed that the FH gauge symmetries are generated by a vector field $\xi^\mu$. For these to preserve the AAdS1 boundary conditions, they must satisfy:$$\begin{gather}\mathcal L_\xi g_{t\mu}^0=0,\mu=t,a\\g^{ab}_{(0)}\mathcal L_\xi g^{(0)}_{ab}=0 \end{gather}$$ ^ed8925
These can be rewritten in the parameters of the metric:$$\begin{gather} \left(\partial_u - \frac 12 l \right)\xi_0^t = \frac 12 D_A^{(0)} \xi^A_0\\
\partial_u \xi^A_0 = -\frac\Lambda 3g_{(0)}^{AB} \partial_B \xi^t_0\\
\sigma = \frac 12 (D_A^{(0)} \xi_0^A + \xi^t_0 l)\end{gather}$$where $l=\partial_u \ln \sqrt q$. 
The lie bracket for $\xi$ as generators is (known in this context as the *modified lie bracket*):$$[\xi_1,\xi_2]_A = \mathcal L _{\xi_1} \xi_2 - \delta_{\xi_1}\xi_2 + \delta_{\xi_2}\xi_1$$Using this and the the constraints on the components $\xi^\mu$, we can derive the explicit asymptotic symmetry algebra.
#### AAdS1 boundary conditions, Bondi gauge
The constraints are$$\begin{gather}\left(\partial_u-\tfrac 12 l\right) f = \tfrac 12 D_A Y^A\\
\partial_u Y^A = -\frac\Lambda 3 q^{AB} \partial_B f\\\omega=0\end{gather}$$This gives rise to the asymptotic algebra$$\begin{gather}[\xi(f_1,Y_a^A),\xi(f_2,Y_2^A)]_A = \xi(f,Y^A):\\
f = \sum\limits_{i=1}^2\ Y_i^A \partial_A f_{i+1} +\tfrac 12 f_i D_A Y_{i+1}^A -\delta _{\xi_i} f_{i+1}  \\Y^A = \sum\limits_{i=1}^2\  Y_i^B\partial_B Y^A_{i+1} -\frac\Lambda 3 f_i q^{AB}\partial_B f_{i+1} - \delta_{\xi_i}Y_{i+1}^A
\end{gather}$$This, known as the $\Lambda-\textrm{BMS}_4$ algebra, is field-dependent, and contains area-preserving diffeomorphisms so is infinite itself. $f$ generate the **supertranslations**, and $Y^A$ generate the **superrotations**.
## Differential Forms
![[Differential Forms]].
## Symmetries and Noether's Theorem
![[Symmetries and Noether's Theorem]].
## Surface Charges
Associated with the generators of the asymptotic symmetries will be $n-2$ forms $\mathbf k_F[\Phi,\delta\Phi]$, and their construction mimics the Barnich-Brandt procedure. However, some of the assumptions, like the Noether current being conserved, the $n-2$ form being conserved on-shell, do not hold anymore. But the procedure can be recovered sufficiently for our purposes. Let us see how.
>[!def] Barnich-Brandt $n-2$ form for asymptotic symmetries
>$$\mathbf k_{F}[\Phi,\delta\Phi] = -I^{n-1}_{\delta\Phi} \mathbf S_F$$

For a first-order gauge theory ($δ_{F=(f^\alpha)} Φ = R_αf^α + R_α^μ∂_μf^\alpha$ and first-order EoMs for $\Phi$), this becomes$$\begin{gather}\mathbf k_F = [\Phi,\delta\Phi] = -\frac 12 \delta\Phi \frac{\partial}{\partial(\partial_\mu\Phi)}\left(\frac{\partial}{\partial dx^\mu}\mathbf S_F\right)\\
\mathbf S_F = R^\mu_\alpha f^\alpha \frac{\delta L}{\delta\Phi} (d^{n-1} x)_\mu\end{gather}$$
>[!example] General Relativity, who could've guessed
>Recall [[Symmetries and Noether's Theorem#^05981e|the weakly vanishing Noether current for GR]] $\mathbf S_\xi = \frac{-\sqrt{-g}}{8\pi G} \xi_\nu(G^{\mu\nu}+g^{\mu\nu}\Lambda)d^{n-1}x$, which gives$$\mathbf k_\xi[g,h] = \frac{\sqrt{-g}}{8\pi G}(d^{n-2}x)_{\mu\nu}[\xi^\nu\nabla^\mu h+\xi^\mu\nabla_\sigma h^{\sigma\nu}+\xi_\sigma\nabla^\nu h^{\sigma\mu} + \frac 12 (h\nabla^\nu\xi^\mu+h^{\mu\sigma}\nabla_\sigma\xi^\nu + h^{\nu\sigma}\nabla^\mu\xi_\sigma)]$$
>(Referring to $\delta g_{\mu\nu}$ as $h_{\mu\nu}$)

>[!tip]- Theorem - Conservation Law
>Define the *invariant presymplectic current*$$\mathbf W[\Phi,\delta\Phi] = \frac 12 I^n_{\delta\Phi} \left(\delta\Phi\frac{\delta \mathbf L}{\delta \Phi}\right)$$Then we have the conservation law$$d\mathbf k_F[\Phi,\delta\Phi]\approx \mathbf W [\Phi,R[F]]$$

>[!def] Surface Charges
>The infinitesimal surface charge is defined by integrating the conserved $n-2$ form of a symmetry over the $n-2$ boundary $\partial\Sigma$ of an $n-1$ surface $\Sigma$:$$\cancel\delta H_F[\Phi] =\int_{\partial\Sigma} \mathbf k_F[\Phi,\delta\phi]$$
>This infinitesimal charge is integrable if it is $\delta$-exact, $\cancel\delta H_F[\Phi] = \delta H_F[\Phi]$, in which case we can integrate it over a path $\gamma$ in the solution space from $\bar\Phi$ to $\Phi$:$$H_F[\Phi] = \int_\gamma \delta H_{F}[\Phi]+N[\bar\Phi]$$Where $N[\bar\Phi]$ is the reference value at $\bar\Phi$, and the integral is independent of the chosen path, as long as the endpoints are the same.

>[!tip] Theorem - Charge representation
>For integrable charges, the following algebra is satisfied:$$\begin{gather}\{H_{F_1},H_{F_2}\} \approx H_{[F_1,F_2]_A}+ K_{F_1,F_2}[\bar\Phi]\\\text{Where }\{H_{F_1},H_{F_2}\}  := \delta_{F_2}H_{F_1} = \int_{\partial\Sigma} \mathbf k_{F_1}[\Phi,\delta_{F_2}\Phi]
>\end{gather}$$
>$K_{F_1,F_2}[\bar\Phi]$ is called the *central extension*, which only depends on the reference solution field configuration $\bar\Phi$, is antisymmetric in the symmetries $F_1,F_2$, and satisfies the 2-cocycle condition, reminiscent of the Bianchi identities:$$\begin{gather}K_{[F_{(1},F_2]_A,F_{3)}} = 0\\\implies K_{[F_{1},F_2]_A,F_{3}}+K_{[F_{3},F_1]_A,F_{2}}+K_{[F_{2},F_3]_A,F_{1}}=0\end{gather}$$
>Thus, up to a central extension, the charges form a representation of the asymptotic symmetry algebra.
### Properties of Surface Charges
Now we've obtained surface charges for a general set of boundary conditions, we'd like to impose some physical constraints on these charges and hence restrict ourselves to the interesting boundary conditions. But note that these conditions are violable, and we'll discuss these conditions in the context of BMS charges in 4D spacetime.
The charges should be
- **Finite** - Charges may diverge due to factors of the expansion parameter (which defines the asymptotic region), or from a divergence of the integral over the $n-2$ surface $\partial\Sigma$.
- **Integrable** - The infinitesimal charges, if integrable, allow us to define the *integrated* surface charges, which then form a representation of the asymptotic symmetry algebra. It is also the integrated charges that generate the symmetries on the solution space.
- **Generically non-vanishing** - Since they generate the symmetries, identically vanishing charges would give rise to trivial actions on the solution space, symmetries which would be considered trivial under the strong definition of the [[Asymptotic and BMS Symmetries#^3c4b63|asymptotic symmetry group]].
- **Conserved** - The integrated charge should be conserved in time. While we discussed a conservation law regarding the charges, this law can fail in certain conditions - the in-depth discussion of how the proof fails is outside the scope of this report, but I shall go through an example.
#### Violations of these properties
- For 4D spacetime on the manifold $\mathbb R^4$, since the surface to integrate over becomes infinite due to the divergence in radial coordinate $r$, the charges diverge. It's more sensible to consider a cut-off $r$ and talk about the coefficients of the overleading orders of $r$.
- Non-integrable charges are dealt with by isolating an integrable part and integrating that. However, the representation theorem may not hold in this case. An alternate approach can be to work with the non-integrable expression and try to define a Lie bracket and representation for the same.
- In asymptotically flat spacetimes, at null infinity, the charges associated with time translation symmetry are not conserved with time. This is known as the *Bondi mass loss*, referring to the decrease of the mass at future null infinity due to radiation flux through the boundary. Similarly, non-conservation often encodes important information about the system's dynamics.
## Example: The BMS Group in 4D Spacetime
### Intuiting Supertranslations
Take a Minkowski spacetime, and identify points at $\mathcal I^+$ with the coordinates $u,\theta,\phi$, such that a beam of light shot from the origin in $\hat n(\theta,\phi)$ at time $u$ reaches that point on $\mathcal I^+$ - essentially, $u$ is the retarded time.
Then we have a few symmetries on the boundary. One is time translation, $u\rightarrow u + C$. The other is translation of the origin, $u\rightarrow u + \delta \vec r\cdot\hat n(\theta,\phi)$. Both of these could be written in terms of spherical harmonics as:
$$
\begin{gather}u\mapsto u+\alpha Y_{00}\\
u\mapsto u + \sum\limits_{m=-1}^{m=1} \alpha_m Y_{1m}\end{gather}
$$
With the condition that the sum over spherical harmonics is real.
One may wonder whether the natural extension of these to higher spherical harmonics is also a symmetry (while maintaining that the additional term must become real):
$$\begin{gather}
u\mapsto u+\sum\limits_{l=0}^\infty \sum\limits_{m=-l}^l \alpha_{lm} Y_{lm}(\theta,\phi)\\
= u+f(\theta,\phi)
\end{gather}
$$
Well, for the general Minkowski spacetime, clearly not, but at the boundary? It turns out, yes, they are - to be precise, they're symmetries of the asymptotic metric - and these are exactly the supertranslations of the BMS group. 
One more way to intuit these is to realise that all the points at two different $\hat n(\theta,\phi)$ at the boundary are causally disconnected, so they cannot synchronise their times, and adding arbitrary time offsets at any $\theta,\phi$ is a symmetry.
### The Bondi Metric in 4D
The BMS group arises as the asymptotic symmetry in an asymptotically flat spacetime. 
Let us work in the Bondi metric. Earlier, we described it as
$$\begin{gather}ds^2 = e^{2\beta} \frac Vr du^2 -2e^{2\beta} du dr + g_{AB} (dx^A - U^A du)(dx^B - U^B du)\\\partial_r\det\left(\frac{g_{AB}}{r^2}\right)=0\end{gather}$$
Where $u$ labelled the null hypersurfaces - the lightcones. For 4D, we work in the bondi coordinates $(u,r,z,\bar z)$ - $z$ is complex and replaces our angular coordinates on the 2-sphere.

Minkowski space can be described in this metric by $\beta=0,V=-r,U^A=0$. Further, we abstract out the $r$ dependence of metric on the 2-sphere by writing $g_{AB}=2r^2\gamma_{z\bar z}$:
$$ds^2 = -du^2 -2dudr+2r^2 \gamma_{z\bar z}dzd\bar z$$

The spacetime we are concerned with is asymptotically flat - so we want functions $\beta,V'=e^{2\beta}\frac Vr,U^A$ such that in the asymptotic limit they give us the Minkowski metric. We discussed these requirements in [[#Asymptotic Flatness in Bondi]]:
$$
\begin{gather}
\beta = \mathcal o(1)\\
\frac{V}{r}= \mathcal o(r^2)\\
U^A = \mathcal o(1)\\
g_{AB} = r^2 \gamma_{AB} + r C_{AB} +D_{AB} + \mathcal O(r^{-1})
\end{gather}
$$
The subleading order term in the metric, $C_{AB}$, describes gravitational waves - the term is order $1/r$ relative to leading order, and is transverse to $\mathcal I^+$.
Also introduce the Bondi mass aspect $m_B$ occurring in the leading order expansion of the coefficients of $du^2$:
$$e^{2\beta}\frac V r +g_{AB}U^AU^B= -1 + \frac{2 m_B}{r}+\mathcal O(r^{-2})$$
And introduce the angular momentum aspect, $N_z$, whose integrals over the sphere, contracted with a particular rotational vector field (equivalently, specifying an axis of rotation) give the total angular momentum.

The bondi mass aspect, the angular momentum aspect, and $C_{AB}$ all are independent of $r$. Also introduce the covariant derivative with respect to $\gamma_{z\bar z}$, $D_z$. With all these, we can write the metric to leading orders in $r$ in the same convention followed by Bondi, van der Berg, Metzner, and Sachs: (note that c.c. implies replacing all $z$ with $\bar z$, in the indices too, and not merely a complex conjugate)
$$\begin{gather}ds^2 = -du^2 -2dudr +2r^2\gamma_{z\bar z} dzd\bar z\\
+\frac{2 m_B}{r}du^2 + \left(rC_{zz}dz^{2} + D^z C_{zz} dudz\right) + \text{c.c.}\\
+\frac 1r \left( \frac 4 3 (N_z+u\partial_um_B) -\frac 1 4 \partial_z(C_{zz}C^{zz})\right) dudz+ \text{c.c.}+\dots\end{gather}$$
The eagle-eyed may notice that in Schwarzschild or Kerr spacetimes, the Bondi mass aspect $= GM$ and hence is proportional to the total mass of the system. More generally, the integral of $m_B\equiv m_B{(u,z,\bar z)}$  over the 2-sphere gives the *total Bondi mass*. It contrasts with the ADM mass in that it excludes the energy carried by gravitational waves to infinity, and so it was key in proving that gravitational radiation decreases the mass of a system.

We also define the Bondi news tensor:
$$N_{zz} =\partial_u C_{zz}$$
This is the gravitational analogue of the field strength $F_{uz}=\partial_uA_z$, and its square is proportional to the energy flux across $\mathcal I^+$.
### Deriving Supertranslations
Restricting to the diffeomorphisms with the asymptotic behaviours:$$\xi^u,\xi^r\sim\mathcal O(1),\quad\xi^z,\xi^{\bar z}\sim\mathcal O\left(\frac 1 r\right)$$This eliminates 6 lorentz generators - the boosts and rotations which grow as $r\rightarrow\infty$.
Then, for a diffeomorphism generated by vector field $\zeta$, the lie derivatives of the metric:$$\begin{gather}\mathcal L_\zeta g_{ur} = -\partial_u\zeta^u +\mathcal O\left(\frac 1 r\right)\\\mathcal L_\zeta g_{zr} = r^2 \gamma_{z\bar z} \partial_r \zeta^{\bar z} - \partial_z \zeta^u +\mathcal O\left(\frac 1 r\right)\\
\mathcal L_\zeta g_{z\bar z} = r\gamma_{z\bar z}(2\zeta^r+rD_z\zeta^r+rD_{\bar z}\zeta^{\bar z}) + \mathcal O(1)\\\mathcal L_\zeta g_{uu} = -2\partial_u\zeta^u -2\partial_u\zeta^r +\mathcal O\left(\frac 1 r\right)\end{gather}$$
We want this diffeomorphism to be an isometry in the large $r$ limit to find the killing vector field $\zeta$ corresponding to the asymptotic symmetries. This gives the general form:$$\zeta = f\partial_u -\frac 1 r (D^zf\partial_z+D^{\bar z} f\partial_{\bar z})+D^zD_z f\partial_r + \dots$$Leaving out the subleading order terms.
There is a caveat for the third term - it depends on the gauge choice for $g_{ur}$, and notably differs in the Newman-Unti gauge where $g_{ur}=-1$. But the first two terms are universal - these are the ones measured in gravitational memory. The first term, notably, is the symmetry $u\mapsto u+f(z,\bar z)$ - the same supertranslations we intuited by extending time and space translations with spherical harmonics!

Thus, in the IR limit, GR does not reduce to STR - instead, to quote[^8], "A large space of degenerate vacua remains."
### Supertranslations in Action
## Applications
### Holography
The *holographic principle* states that quantum gravity can be described in terms of lower-dimensional quantum field theories on the boundary.
An important extension of this duality is the AdS/CFT correspondence, which states that the gravitational theory in the $d+1$ dimensional asymptotically AdS spacetime (AAdS2) is dual to a CFT on the $d$ dimensional boundary.
Among the relations between a bulk theory and its dual boundary theory, relevant to us is the correspondence between the gauge symmetries in the bulk theory and the global symmetries of the boundary theory. Now consider that the bulk theory has asymptotic symmetries like the ones we've discussed - this correspondence implies that there exist field theories on the boundary with the same symmetries as global. 
The holographic principle is believed to hold in all types of asymptotics. In particular, in asymptotically flat spacetimes, the dual theory would have BMS as the global symmetry.
### Infrared Triangle
The Infrared triangle of gauge theories refers to the connections between three seemingly unrelated topics - asymptotic symmetries, soft theorems, and memory effects.

**Soft theorems** are about scattering amplitudes involving massless particles with small momenta $q\rightarrow0$ - then the scattering amplitude relates to that of the rest of the particles (to first order):$$\mathcal M_{n+1}(q,p_i) = S^{(0)}\mathcal M_n(p_i) + \mathcal O(q^0),\;S^{(0)}\sim q^{-1}$$ $S^{(0)}$ is called the soft factor, particular to the soft particle involved and to some extent independent of the other particles - for example, it does not involve the spins of the rest of the particles. *Subleading soft theorems* have also been proposed, discussing the $S^{(1)}\sim q^0$ factor (also scaling $\mathcal M_n(p_i)$).
These theorems also imply that an infinite number of soft

**Memory effects** in general refer to permanent shifts in systems from cyclic processes. In gauge theories, we refer to when a field is turned on as a result of a burst of energy passing through the region of interest, leading to an observable phenomenon. In the context of gravity, gravitational waves can cause the *displacement memory effect*, wherein a permanent shift happens in the relative position of two (inertial) detectors. The spin and refraction memory effects also exist under gravity.
Consider the Bondi gauge in the AF3 boundary conditions - then the angular displacement of the two inertial observers, if they are in the asymptotic region, is proportional to the extent to which the field $C_{AB}$ is turned on, $\Delta s^A\propto \Delta C_{AB}$. This could happen due to gravitational waves (Christodoulou effect) or a variation of the Bondi mass $M$ (ordinary memory effect).

So how are these three related?
1. Every symmetry transformation has a corresponding Ward-Takahashi identity equating scattering amplitudes related by that transformation. Supertranslations are symmetries of gravitational scattering processes[^10], and the Ward identity for supertranslations is equivalent to the soft graviton theorem.
2. The displacement memory effect is equivalent to performing a supertranslation - it has the same effects on $C_{AB}$ as a burst of gravitational waves. The supertranslation connects the two vacua related by the memory effect.
3. The soft theorem relates to the memory effect via a fourier transform. While the soft theorem concerns poles in momentum space $(S^{(0)}\sim q^{-1})$, the memory effect is a position-space permanent shift (sometimes called a DC shift). These are the same thing - the fourier transform of a pole is a step function.
Furthermore, subleading triangles are also a topic of research - superrotations' ward identities are equivalent to the subleading soft graviton theorem, and the spin and refraction memory effects can be understood as superrotations too.

This infrared triangle is itself relevant to the black hole information paradox. In infrared - low energy - regimes, black holes produce a number of soft gravitons - through this correspondence, they relate to asymptotic symmetries and their surface charges, which then need to be accounted for as information storage - these charges are called *soft hairs*.
### Black Hole Information Paradox
Following is an excerpt from an interview[^6] with Strominger, where he explains in lay terms the relationship between asymptotic symmetries and the information paradox - the linchpin of the connection is that a black hole event horizon is, in some sense, expanding at the speed of light:

> The horizon of a black hole has the weird feature that it’s a sphere and it’s expanding outward at the speed of light...  ... That’s why nothing that is inside a black hole can get out—because the boundary of the black hole itself is already moving at the speed of light.
> 
> There’s this symmetry of a black hole that we all knew about in which you move uniformly forward and backward in time along all of the light rays. But there’s another symmetry... ...in which the individual light rays are moved up and down. See, individual light rays can’t talk to each other—if you’re riding on a light ray, causality prevents you from talking to somebody riding on an adjacent light ray. So these light rays are not tethered together. You can slide them up and down relative to one another. That sliding is called a super-translation.
> 
> ...It turns out that adding a soft graviton has an alternate description as a super-translation in which you move some of these light rays back and forth relative to one another.
> 
> ...Super-translations were introduced in the 1960s, and they were talking not about the light rays that comprise the boundary of spacetime at the horizon of a black hole but the light rays that comprise the boundary of spacetime out at infinity.

## Modern Research on Asymptotic Symmetries
1. Asymptotic symmetries at timelike and spacelike infinities.[^7]

## Bibliography
References not mentioned in the text: [^1],[^3],[^8],[^9].

[^1]: Ruzziconi, Romain. ‘Asymptotic Symmetries in the Gauge Fixing Approach and the BMS Group’. arXiv, 3 May 2020. [https://doi.org/10.48550/arXiv.1910.08367](https://doi.org/10.48550/arXiv.1910.08367).
[^2]: [1211.6347] Conserved Charges in Asymptotically (Locally) AdS Spacetimes’. Accessed 31 August 2023. [https://arxiv.org/abs/1211.6347](https://arxiv.org/abs/1211.6347).
[^3]: Ashtekar, A., & Petkov, V. (2014). _Springer Handbook of spacetime_. Springer.
[^4]: G. Compère, A. Fiorucci, and R. Ruzziconi, “The Λ-BMS4 group of dS4 and new boundary conditions for AdS4,” 1905.00971.
[^5]: A. Poole, K. Skenderis, and M. Taylor, “(A)dS4 in Bondi gauge,” Class. Quant. Grav. 36 (2019), no. 9, 095005, 1812.05369.
[^6]: http://blogs.scientificamerican.com/dark-star-diaries/stephen-hawking-s-new-black-hole-paper-translated-an-interview-with-co-author-andrew-strominger/
[^7]: Chakraborty, Sumanta, Debodirna Ghosh, Sk Jahanur Hoque, Aniket Khairnar, and Amitabh Virmani. ‘Supertranslations at Timelike Infinity’. _Journal of High Energy Physics_ 2022, no. 2 (February 2022): 22. [https://doi.org/10.1007/JHEP02(2022)022](https://doi.org/10.1007/JHEP02(2022)022).
[^8]: Strominger, Andrew. ‘Lectures on the Infrared Structure of Gravity and Gauge Theory’. arXiv, 15 February 2018. [http://arxiv.org/abs/1703.05448](http://arxiv.org/abs/1703.05448).
[^9]: Bondi, Hermann, M. G. J. Van der Burg, and A. W. K. Metzner. ‘Gravitational Waves in General Relativity, VII. Waves from Axi-Symmetric Isolated System’. _Proceedings of the Royal Society of London. Series A. Mathematical and Physical Sciences_ 269, no. 1336 (January 1997): 21–52. [https://doi.org/10.1098/rspa.1962.0161](https://doi.org/10.1098/rspa.1962.0161).
[^10]: 39. A. Strominger, “On BMS Invariance of Gravitational Scattering,” JHEP 07 (2014) 152, arXiv:1312.2229 [hep-th].