---
tags:
  - BTP
---
Let a manifold $M$ and the tangent space $T_p(M)$ at any point $p$ on it. 
## One-forms

> [!def] One-form
> A 1-form is a linear map $\omega:T_p(M)\rightarrow F$, where $F$ is the field over which the vector space $T_p(M)$ is defined.

Thus, a one form is an element of the dual vector space $(T_p(M))^*$, and can be written (for $M=\mathbb R^2$)as $w(\langle dx,dy\rangle) = adx+bdy$ (since it is linear). Note that this is exactly the differential element for the line integral over a vector field $(a,b)(x,y)$.
The action of a 1-form is to scale the projection of its input on a particular line:
$$\begin{align}w(\langle x,y\rangle) &= ax+by\\&=\langle a,b\rangle\cdot\langle x,y\rangle\\
&= \|\langle a,b\rangle\|\cdot  \operatorname{Projection}_{\langle a,b\rangle}(\langle x,y\rangle)
\end{align}
$$
# The Wedge product and m-forms
We want to define a product $\wedge$ of one-forms which is a linear function and has some meaningful geometrical representation. 
This is not the most precise motivation for 2- or n-forms, but we'll build up to the more precise ones later - they have to do with antisymmetry and generalising the Stokes theorem.
$w_1\wedge w_2:T_pM\times T_pM\rightarrow F$ is the map we're interested in - note that it takes two vectors as inputs. So we have the $4$ components $w_i(v_j)$ to play with, and (going forward I refer to the one-form $w_1$ and the dual vector it projects vectors on, $\langle a,b\rangle$, interchangeably) these components are essentially the projections of $v_1,v_2$ onto $w_1,w_2$ - we can visualise these as two vectors, the projections of $v_1,v_2$ onto the $w_1\operatorname-w_2$ plane. With two vectors in a plane, what operation could convert them to a scalar? Well, a dot product, but that does not encode the significance of this being a product - it still has length dimensions, in some sense, and has no antisymmetry. As we shall see later, we prefer something antisymmetric, something that does justice to its definition as a product - an area, $|v_{1}^{w_1\operatorname-w_2}\times v_2^{w_1\operatorname-w_2}|$:$$w_1\wedge w_2 (v_1,v_2):= \det \begin{pmatrix}w_1(v_1) & w_2(v_1)\\ w_1(v_2) & w_2(v_2)\\\end{pmatrix}$$
>[!def]- 2-forms
>The wedge product of two 1-forms.
##### Properties of the Wedge
- From the determinant structure, the two-form is **antisymmetric in inputs**: $w_1\wedge w_2(v_1,v_2)=-w_1\wedge w_2(v_2,v_1)$.
- Also from the determinant, the wedge product is **anti-commuting**:$w_1\wedge w_2=-w_2\wedge w_1$.
	- Hence the wedge of a 1-form with itself is 0.
>[!tip]- The wedge product is distributive over addition
>Proof:
>$$\begin{gather}w_1\wedge (w_2+w_3) [v_1,v_2] = w_1(v_1)(w_2+w_3)(v_2) -  w_1(v_2)(w_2+w_3)(v_1) \\= w_1\wedge w_2 [v_1,v_2]+w_1\wedge w_3 [v_1,v_2]\end{gather}$$
>Because the determinant is distributive over addition in a single row/column.

Which leads to the following:
>[!tip]+ on $\mathbb R^2$,$w_1\wedge w_2 = Cdx\wedge dy$ for $C\in F$
>Proof:$$\begin{gather}w_1\wedge w_2 = (Adx+Bdy)\wedge(Cdx+Ddy) \\= AC\cancel{dx\wedge dx} + ADdx\wedge dy+BCdy\wedge dx +BD\cancel{dy\wedge dy}\\
>= (AD-BC)dx\wedge dy
>\end{gather}$$
>One can easily see that $dx\wedge dy$ gives the (signed) area between its two input vectors, and so any two-form simply scales this area by some constant.

>[!def] m-forms
>A multilinear and alternating $w:(T_pM)^m\rightarrow F$.
>- **Multilinear** - Linear in every argument
>- **Alternating** - Antisymmetric in any pair of arguments
>
>One way to obtain an $m$-form is to construct it out of $1$-forms and wedge products:$$\begin{gather}w(v_1,\dots,v_2)=w_1\wedge \dots\wedge w_2(v_1,\dots,v_2)\\ = \det(w_i(v_j))\end{gather}$$
>For coordinates $x^i$ on $M$, any $m$-form on $T_pM$ is a linear combination of $dx^{i_1}\wedge\dots\wedge dx^{i_m}$. Thus for an $n$-dim manifold, only $m\le n$ forms are non-trivial.

>[!tip] The wedge product is associative

>[!tip]- $\alpha\wedge\beta = (-1)^{m_\alpha m_\beta}\beta\wedge\alpha$
>The proof is trivial - consider moving each component of $\beta$ through all the components of $\alpha$, each step is an anti-commutation.
>Note how this means $\alpha\wedge\alpha=0$ when $m_\alpha$ is odd, but not necessarily when it is even.

>[!tip]- $\alpha\wedge(\beta +\gamma)= \alpha\wedge\beta+\alpha\wedge\gamma$
>We already saw that the wedge is distributive over addition of one-forms. Does this extend to m-forms?
>First, consider the addition of m-forms. What does $\beta+\gamma$ mean?
>$$\begin{gather}(\beta+\gamma)(v_i):= \beta(v_i)+\gamma(v_i)\\
>\alpha\wedge(\beta+\gamma) = \sum_i\sum_j a_i (b_j+c_j)(dx^{i_1}\wedge\dots\wedge dx^{i_n})\wedge(dx^{j_1}\wedge\dots\wedge dx^{j_m})
>\end{gather}$$
>Clearly, assuming m-forms are spanned by $(dx^{j_1}\wedge\dots\wedge dx^{j_m})$ makes the proof trivial.
>Can we prove this without the expansion? I'm not sure, but the proof would certainly hold even with the weaker assumption that the m-form space is spanned by the space of all wedge products of $m$ 1-forms.
>To work without the expansion, we need to define the wedge product on two m-forms more rigorously. Considering the definition that we want an $m_1+m_2$ form, we can restrict the wedge product to be $\alpha\wedge\beta(\{v_i\},\{w_j\}) = \det \begin{pmatrix} \alpha(\{v_i\}) & \beta(\{v_i\})\\ \alpha(\{w_i\}) & \beta(\{w_i\})\end{pmatrix}$. Then the proof is trivial - it is identical to that for 1-forms.

>[!info] $dx_I = dx_{i_1}\wedge\dots\wedge dx_{i_m}$ for $I = \{i_j\}_{j=1}^m$.
>The space of all $m$-forms on a manifold, called $\Lambda^mM$, has a basis given by $\{dx_I\}$.
- $$dx_{\{i_k\}}(v^{(j)}) = \det (v_{i_k}^{(j)})_{1\le j,k\le m}$$
- It's not hard to see that$$\dim \Lambda^m M^n = {n\choose m}$$Simply by considering that the basis is $dx_I$ and $I$ cannot have repeated indices.
# Differential m-forms
These are m-forms but with differentiable functions as coefficients:$$\begin{gather}\omega := \sum\limits_I f_I dx_I,\\ f_I:M\rightarrow F\forall I\\
\omega_p := \sum\limits_I f_I(p) dx_I\end{gather}$$
So a differential m-form is really a map from $M$ to $\Lambda_p^mM$ - a smooth tensor field over the manifold, mapping to the cotangent bundle. ^812167
Alternatively, it could also map $m$ vector fields to a scalar function on the manifold (tensor field innit).
The space of all differential $m$-forms is a module over the space of all forms over a manifold, $\Lambda(\mathbb R^n)=\bigoplus_{m=0}^n \Lambda^m(\mathbb R^n)$. $\dim\Lambda^m(\mathbb R^n)= {n\choose m},\dim\Lambda(\mathbb R^n) = 2^n$. 
# Integrating m-forms
#### Integrating 2-forms
Take a surface $S$ embedded in $M^n$ parametrised by $\phi:D\rightarrow M^n$, $D\subset \mathbb R^2$ and a differential 2-form $\omega$.
Consider the Reimann integral:$$ \iint _D f(x,y) dA = \lim\limits_{\delta_x\rightarrow 0,\delta_y\rightarrow 0}\sum\limits_{ij} f(x_i,y_j) \delta_x\delta_y$$We've defined the integral by discretising space. Now we can take a point $p$ in $D$ and two points away from it, defining two vectors in $\mathbb R^2$, and map these to three points and two vectors in $M^n$. As the other points approach $p$ in $D$, the vectors in $M^n$ become tangent vectors at $\phi(p)$. We use this in the discrete space by taking $p=(u_i,v_j)$ and the other two points $(u_{i+1},v_j),(u_{i},v_{j+1})$. Then
$$\begin{gather}\int_S \omega := \lim_{\delta_u,\delta_v\rightarrow 0}\sum\limits_{i,j} \omega_{\phi(u_i,v_j)} (\phi(u_{i+1},v_j) - \phi(u_i,v_j),\phi(u_{i},v_{j+1}) - \phi(u_i,v_j))\\
= \lim_{\delta_u,\delta_v\rightarrow 0}\sum\limits_{i,j} \omega_{\phi(u_i,v_j)} \left(\frac{\phi(u_{i+1},v_j) - \phi(u_i,v_j)}{\delta_u},\frac{\phi(u_{i},v_{j+1}) - \phi(u_i,v_j)}{\delta_v}\right)\delta_u\delta_v\\
= \iint _D \omega_{\phi(u,v)} \left(\partial_u\phi,\partial_v\phi\right) dA
\end{gather}$$
#### And now m-forms
- $\omega = \sum\limits_I f_I dx_I,\; I\in\{1,\dots,n\}^m,\; dx_I = dx_{i_1}\wedge\dots\wedge dx_{i_m}\text{ for }I=\{i_j\}_{j=1}^m$
- $S\subseteq M^n$ parametrised by $\phi:D\rightarrow M^n, \; D\subseteq \mathbb R^m$.
$$\int_S\omega := \int\dots\int_D \omega_{\phi(u_1,\dots,u_m)}\left(\partial_1\phi,\dots,\partial_m\phi\right)\underbrace{du_1\dots du_m}_{dV_m}$$
Note that $\partial_i\phi$ is an n-dim vector, and $\omega$ will act on it. The $dx_I$ components of $\omega$ will extract the $I$th components of each input vector, and take the determinant of all the components, $m$ from each of the $m$ vectors. The rest is merely multivariate integration.
From this definition, by comparing two different parameterisations, we can derive the multivariate variable substitution rule $\int f(v) dv = \int f(\phi(u))|\det D\phi| du$, where $D\phi$ is the Jacobian matrix.
# Exterior Derivative
We want to define a derivative which takes an $m$ form to an $m+1$ form.
Let's start by considering a 0-form to a 1-form:
Given a 0-form (a function) $f$ on $\mathbb R^n$, we want to define a geometrically sensible 1-form $df$, which will be evaluated at a point $p$ in $\mathbb R^n$ and a vector $v\in T_p\mathbb R^n$. What could do this for a scalar $f$? Well, a scalar field, and a derivative at a point related to a direction at that point - the natural definition is the directional derivative!$$\begin{gather}(df)_p(v) = D_v f |_{x=p} = \nabla f |_p \cdot v\\ = \sum\limits_i \frac{\partial f}{\partial x_i} v_i = \sum\limits_i \frac{\partial f}{\partial x_i} dx_i (v)\end{gather}$$Great, that seems good. What about extending this? A natural extension might be:$$ \begin{gather} d(f dx_I) = \sum\limits_i \frac{\partial f}{\partial x_i} dx_i\wedge dx_I\\\implies d\omega = \sum\limits_{I,i} \frac{\partial f_I}{\partial x_i} dx_i\wedge dx_I \end{gather}$$Where $\omega = \sum\limits_I f_I dx_I$, where $I$ parametrises the elementary $m$ forms $dx_I$. It is worth noting the rigorous definition: $I$ is a multi-index $(i_1,\dots,i_m),\; 1\le i_1\lt \dots\lt i_m\le n$, and $dx_I:= dx_{i_1}\wedge\dots\wedge dx_{i_m}$.
In this sum, only terms with no common $dx_i$ remain, since $dx_i\wedge dx_i=0$. This maintains the rule that $d\omega=0$ if $\omega$ is an $m\ge n$ form.
### Product Rule
>[!tip] **Proposition** 
>$\omega$ is an $m$ form, then $$ d(\omega\wedge\mu) = (d\omega)\wedge \mu+(-1)^m\omega\wedge(d\mu)$$
>>[!info]+ Proof
>>$$\begin{gather}\omega =\sum\limits_I f_I dx_I,\quad\mu=\sum\limits_J g_Jdx_J\\ d(\omega\wedge\mu)=\sum\limits_{I,J,r} \partial_r(f_I g_J) dx_r\wedge dx_I\wedge dx_J\\
>>=\sum\limits_{I,J,r} (\partial_rf_I) g_J (dx_r\wedge dx_I)\wedge dx_J + f_I(\partial_r g_J) (-1)^m dx_I\wedge (dx_r\wedge dx_J)\\
>>= (d\omega)\wedge \mu+(-1)^m\omega\wedge(d\mu)\end{gather}$$
>>Which completes the proof. Note in the second-last step $dx_r$ was moved past $dx_I$, hence accumulating a factor of $(-1)^m$.
### Nilpotency of index 2
Nilpotency of index $k$ is when an operator (generally a matrix) to the power $k$ is null.
>[!tip] Proposition
>$$d^2(\omega) := d(d\omega)=0$$
>>[!info]+ Proof
>>$$\begin{gather}\omega=\sum\limits_I f_I dx_I\\
>>d\omega = \sum\limits_{I,j}\partial_jf_I dx_j\wedge dx_I\\
>>d^2\omega = \sum\limits_{I,j,k}\partial_k\partial_jf_I dx_k\wedge dx_j \wedge dx_I\end{gather}$$
>>Now notice that when $j=k$, $dx_k\wedge dx_j=0$.
>>When $j\neq k$, $\partial_k\partial_j \phi =\partial_j\partial_k \phi$ (theorem of mixed partials, applicable for smooth functions $\phi$, which we always assume for the coefficients $f_I$ in our differential forms). Combine this with $dx_k\wedge dx_j= -dx_j\wedge dx_k$ - think of it like contracting a fully symmetric tensor with a fully antisymmetric function - and it is clear that all terms will cancel, and the result will be $0$.
### Generalisation of Multivariable Calculus on $\mathbb R^3$
The familiar vector derivatives on $\mathbb R^3$ are:
$$\text{Scalar}\xrightarrow{\text{Divergence}}\text{Vector}\xrightarrow{\text{Curl}}\text{Vector}\xrightarrow{\text{Gradient}}\text{Scalar}$$
We can treat these like $0,1,2$ & $3$ forms respectively - $n$ forms can also feel like scalars, and $n-1$ forms can also act like vectors. Under this generalisation, the 3 derivatives all unify to become the exterior derivative $d$ in different contexts. This provides a satisfying and unified proof for $\vec\nabla\cdot(\vec\nabla\times \vec A)=0$ and $\vec\nabla\times(\vec\nabla \phi)=0$ - these are both $d^2\omega=0$ for different $m$.
# Hodge Operator
Recall that the space of all differential $m$-forms is a module over the space of all forms over a manifold, $\Lambda(\mathbb R^n)=\bigoplus_{m=0}^n \Lambda^m(\mathbb R^n)$. $\dim\Lambda^m(\mathbb R^n)= {n\choose m},\dim\Lambda(\mathbb R^n) = 2^n$. 
Notice that $\dim\Lambda^m(\mathbb R^n)= {n\choose m} = {n\choose n-m} = \dim\Lambda^{n-m}(\mathbb R^n)$. Furthermore, when representing the multivariable calculus of $\mathbb R^3$ in the language of forms, we wrote both the $1$ forms and $2$ forms as vectors. This is all suggestive of a deeper relation between the $m$ and $n-m$ forms, which does exist - it is known as the **Hodge duality**, powered by the **Hodge operator**.
>[!def] **Definition** : Hodge Operator
>$$\begin{gather}*:\Lambda^m(\mathbb R^n)\rightarrow \Lambda^{n-m}(\mathbb R^n)\\
> * dx_I = dx_J, \text{ s.t. }dx_I\wedge dx_J = dx_1\wedge \dots\wedge dx_n
>\end{gather}$$
>Where $dx_1\wedge \dots\wedge dx_n$ is also known as the canonical $n$-Volume form.

It is trivial to prove that $\omega=\sum\limits_If_Idx_I\implies *\omega=\sum_I f_I(*dx_I)$.
>[!tip] Proposition :  $*^2\omega_m=(-1)^{m(n-m)}\omega_m$
>>[!info]+ Proof
>>$$\begin{gather}\text{Let }*dx_I = dx_J\\
>>*(*dx_I) = *dx_J,\text{ let } *dx_J=dx_K\\
>>dx_J\wedge dx_K = dx_1\wedge\dots\wedge dx_n = dx_I\wedge dx_J\\
>>\implies (-1)^{\dim J\times \dim K}dx_K\wedge dx_J = dx_I\wedge dx_J\\
>>\implies *^2dx_I=dx_K = (-1)^{m(n-m)}dx_I\end{gather}$$

>[!example] Example
>Working on $\mathbb R^2$,$$\begin{gather}*1 = dx\wedge dy\\ *dx=dy, \quad *dy=-dx\\
>*(dx\wedge dy) = 1\end{gather}$$
>Working on $\mathbb R^3$, let's look at 1 and 2 forms, since the 0 and $n$ forms trivially map to each other$$\begin{gather}*dx=dy\wedge dz,\quad *dy = -dx\wedge dz,\quad *dz=dx\wedge dy\end{gather}$$
>The rest of the relations can be derived from the property $*^2\omega_m=(-1)^{m(n-m)}\omega_m$.
### Another look at $\mathbb R^3$
Scalars are 0-forms, and vectors are 1-forms with $dx_i$ identified as the basis of the vector space. Then:
- $\text{grad}(\phi) = d\phi$
- $\text{curl}(\vec A)=*d\omega_A$ - the exterior derivative of a vector is a 2-form, which we then convert to the corresponding 1-form.
- $\text{div}(\vec A)=*d(*\omega_A)$ - take the exterior derivative of the 2-form corresponding to a vector, which gives us a 3-form. Turn that into a 0-form, a scalar.
The proofs are trivial algebra and are left to the reader.
### Hodge Operator generalised with the Inner product
This is a generalisation that will aid the eventual goal of writing Maxwell's equations in the language of forms.
>[!def] Definition : $*$ Hodge star operator
>For $m$ form $\alpha$, $*\alpha$ is the unique $n-m$ form s.t. $\forall \beta\in\Lambda^m(\mathbb R^n)$,$$\beta\wedge(*\alpha)=\langle\alpha,\beta\rangle dV$$
>Where $dV$ is the canonical $n$-volume form.

>[!def] **Definition** : Bilinear form on $k$-forms, $\langle\cdot,\cdot\rangle:(\Lambda^k(\mathbb R^n))^2\rightarrow \mathbb R$
>Generally defined as $\langle dx_I,dx_J\rangle=\delta_{IJ}$, which gives the Hodge star operator as defined previously - however, we have the freedom to define it differently to generalise the Hodge star.
### Generating $\langle\cdot,\cdot\rangle_k$ from  $\langle\cdot,\cdot\rangle_1$
Say we know $\langle dx_i,dx_j\rangle$. How could we generalise this? What is a natural extension?
Consider the set of permutations of $(1,\dots,m)$, called $S_m$. For the extension, a simple suggestion is $\langle dx_I,dx_J\rangle = \langle dx_{i_1},dx_{j_1}\rangle\dots \langle dx_{i_n},dx_{j_n}\rangle$, but this won't do, we should consider the permutations of $J$ with respect to $I$, which is the set $S_m$. So the extension becomes:
$$\begin{gather}\langle dx_I,dx_J\rangle = \sum\limits_{\sigma\in S_m} \text{sgn}(\sigma)\langle dx_{i_1},dx_{j_{\sigma(1)}}\rangle\dots \langle dx_{i_n},dx_{j_{\sigma(n)}}\rangle\end{gather}$$Note $\text{sgn}(\sigma)$ is the sign of the permutation, $1$ for an even number of swaps and $-1$ for an odd number of swaps.
### Codifferential
>[!def] Definition : Codifferential
>The formal adjoint (aka Hodge dual) of the exterior derivative $d:\Lambda^p(M)\rightarrow\Lambda^{p+1}(M)$ is the map $\delta:\Lambda^p(M)\rightarrow\Lambda^{p-1}(M)$, a generalisation of the divergence, defined as$$\delta = (-1)^{n(p+1)+1}*d* \Leftrightarrow d = (-1)^{np}*\delta*$$ 
>Essentially the dual of the derivative of the dual of a $p$-form, up to a sign. On an even-dim manifold, the sign is always $-1$.
- $\delta$ of a 0-form is 0.
- If $\alpha=d\beta$, $\beta$ is the *exact* form of $\alpha$. If $\alpha=\delta\beta$, $\beta$ is the *coexact* form of $\alpha$.
- $\alpha$ is *closed* if $d\alpha=0$, and it is $coclosed$ if $\delta\alpha=0$ - in which case $*\alpha$ is closed.
- $d^2=0$ and $\delta^2=0$
- $\delta*=(-1)^{p+1}*d,\quad *\delta=(-1)^p*d$
- $d\delta * = *\delta d,\quad*d\delta=\delta d*$

>[!def] Definition : Hodge Laplacian
>Defined by coupling the co-differential to the exterior derivative, $$\begin{gather}\Delta:\Lambda^p(M)\rightarrow\Lambda^p(M)\\\Delta = \delta d+d\delta = (d+\delta)^2\end{gather}$$
>Properties:
>- $[\delta,\Delta]=[d,\Delta]=[*,\Delta]=0$
>- $\delta\Delta=\delta d\delta$
>- $d\Delta = d\delta d$

A $p$ form is called a harmonic if $\Delta\alpha=0$.
>[!tip] Proposition : A form is harmonic iff it is closed and coclosed.
>Proof of the forward implication: 
>$$\begin{gather}
>\Delta\alpha=0\implies \alpha\wedge*\Delta\alpha=0\implies\langle\alpha,\Delta\alpha\rangle=0
>\\\langle\alpha,\Delta\alpha\rangle = \langle\alpha,d\delta\alpha \rangle+\langle\alpha,\delta d\alpha\rangle = \langle\delta\alpha,\delta\alpha\rangle+\langle d\alpha, d\alpha\rangle\end{gather}$$
>Since the norm is positive-definite, $\langle\delta\alpha,\delta\alpha\rangle$ and $\langle d\alpha,d\alpha\rangle$ must vanish separately. Hence proved.
>The converse, $d\alpha=\delta\alpha=0\implies\Delta\alpha=0$, is trivial.
## Hodge Decomposition Theorem
# Maxwell's equations in Differential Forms
### Minkowski Inner Product
When working in $\mathbb R^4$, 4D spacetime, our coordinates are $(t,x,y,z)$, Lorentz 4-vectors. In a flat spacetime, their inner product is the Minkowski metric, $\text{diag}(1,-1,-1,-1)$ (with the negative signature).
On this manifold, the 1-forms will be $dt,dx,dy,dz$, with the same inner product.
Using this inner product, we will define inner products over $m$-forms, and hence generalise the Hodge star to 4D spacetime. Then we will be able to use it to rewrite Maxwell's equations.
Furthermore, in General Relativity, the spacetime metric generalises to a tensor field over the manifold, and so the $m$-form inner product and the Hodge star also become position-dependent. The formalism we have discussed allows us to continue using this powerful language in GR.
### Extended to $2$-forms
The 6 $2$-forms on 4D spacetime are $dt\wedge dx_i$ and $dx_i\wedge dx_j$. The results of the inner product's extension are tabulated:
- $\langle dt\wedge dx_i,dt\wedge dx_i\rangle=-1$
- $\langle dt\wedge dx_i,dt\wedge dx_{j\neq i}\rangle=0$
- $\langle dx_i\wedge dx_j,dx_i\wedge dx_j\rangle= 1$
- $\langle dx_i\wedge dx_j,dx_i\wedge dx_{k\neq j}\rangle= 0$
Where $i\neq j$ is implicit in the last two.
The matrix form of this inner product is diagonal.
![[Pasted image 20231110154956.png|400]]
### And to $3$-forms
We have 4 $3$-forms, $dx\wedge dy\wedge dz$ and $dt\wedge dx_i\wedge dx_j$. We could explicitly calculate the inner products, which I have verified with, but simply from the Hodge duality and symmetry principles one would expect a matrix proportional to $\text{diag}(1,-1,-1,-1)$. Close enough, the actual inner product matrix turns out to be $\text{diag}(-1,1,1,1)$.
### Computing the Hodge duals
- $*dt =\ ?$ We want $dt\wedge(*dt) = \langle dt,dt\rangle dV=dV$, so $*dt = dx\wedge dy\wedge dz$.
- $*dx =\ ?$ We want $dx\wedge(*dx) = \langle dx,dx\rangle dV=-dV$, so $*dx = dt\wedge dy\wedge dz$. And similarly for $dy,dz$.
- $*(dt\wedge dx)$ : Clearly we'll get $Ady\wedge dz$, but we need $A$. Since $\langle dt\wedge dx_i,dt\wedge dx_i\rangle=-1$, and $(dt\wedge dx)\wedge(dy\wedge dz)=dV$, $*(dt\wedge dx)=-dy\wedge dz$.
- $*(dx\wedge dy)$ : $(dx\wedge dy)\wedge(dt\wedge dz)=dV$, and the inner product is 1, so this is exactly what we want, $*(dx\wedge dy) = dt\wedge dz$.
### And then there was light
The equations:$$\begin{gather}\nabla\cdot E = \rho\\\nabla\cdot B =0\\\nabla\times E = -\partial_t B\\
\nabla\times B = j+\partial_t E \end{gather}$$To convert these, we need to define the current 1-form:$$J=\rho dt -\vec j\cdot(dx,dy,dz)\\
= \rho dt-j_x dx -j_y dy - j_z dz$$And also define the electromagnetic field strength tensor as a 2-form to encode the fields $E,B$:$$\begin{gather} F = E_x dx\wedge dt + E_y dy\wedge dt+E_z dz\wedge dt\\
+B_x dy\wedge dz + B_y dz\wedge dx+B_z dx\wedge dy
\end{gather}$$Then the source-free and sourced pairs of Maxwell's equations can be concisely written as:$$\begin{gather}dF=0\\ *d(*F)=J\end{gather}$$Connecting these to Maxwell's equations is a little bit of algebra, which I shall omit.
The definition of $F$ may feel a little arbitrary, but those familiar with the electromagnetic 4-potential formulation may realise that $F$ is simply $dA$, $A$ being a 1-form, which gives a first-principles proof for $dF=0$, leaving $*d(*F)=J$ to be the equation of motion derived from the action written in terms of $A$.
This has strong connections to [[Chern-Simons gauge theory]], where the 1-form $A$ is extended to be the representation of a Lie group $G$, and $F:=dA+A\wedge A$.
# Generalising Stokes' Theorem
We'd like to rewrite Stokes' Theorem in the language of differential forms, and hence extend it to general dimensions and manifolds. We know how to integrate differential forms - they're the integrand and measure all in one. But what we don't have as well-defined is the region they will integrate over. So we define:
## $m$-cells and chains
>[!def] Definition : $m$-cell $\sigma$
>The image of a differentiable map $\phi:[0,1]^m\rightarrow \mathbb R^n$, with a specified orientation.
>More intuitively, an $m$-dim hypersurface embedded in $\mathbb R^n$.
- A 0-cell is a point
- A 1-cell is a curve
>[!def] Definition : $m$-chain $\Sigma$
>A linear combination of $m$-cells.
>$$\Sigma= \sum\limits_i n_i\sigma_i$$

Then we integrate an $m$-form over an $m$-chain:$$\begin{gather}\int_\Sigma \omega=\sum\limits_in_i\int_{\sigma_i}\omega\\=\sum\limits_i n_i\int_{D\ \subseteq\  \mathbb R^m} \omega_{\phi(u)}(\nabla \phi) dV_m \end{gather}$$When the coefficient $n_i$ is negative, that amounts to reversing the orientation of the $m$-cell.
## Boundaries
>[!def] Definition : Boundary of an $m$-cell
>The boundary of $\sigma$, called $\partial\sigma$, is defined as $$
>\partial\sigma=\sum\limits_i^m (-1)^{i+1} \left(\phi(x_i=1) - \phi(x_i=0) \right)$$
>Where $\phi$ is the map whose image is the cell $\sigma$.

Note that this is a linear combination of $m-1$ cells of the kind $\phi(x_i=a)$ - in other words, an $m-1$ chain.
The orientation of these boundary cells is decided by the direction the parameters $x_i$ increase in, but can further be effectively reversed by factors of $-1$. Thus the formula acts to define the boundary concordant with our intuition - for example, for a 2D surface like a quadrant of a disc, the boundary becomes the expected closed loop $(0,R)\rightarrow(R,0)\rightarrow(0,0)\rightarrow(0,R)$.
For cells with $\phi(x_i=0)=\phi(x_i=1)$, the formal linear combination of the $m-1$ cells is $0$, so the boundary is the $m-1$ chain $0$ - a null set, to relate to the 'image of a differentiable map' definition.
Sometimes, one of the $m-1$ cells may actually be a lower-dimensional cell with an overspecification of coordinates - for example, working in polar coordinates, we often get the origin as one of the boundary cells. These have a $0$ contribution to the integral, which is intuitive since their $m-1$D measure (or hypervolume) is 0, and can be rigorously shown by showing that the Jacobian in the integral is singular. Presumably a pure form-language proof exists as well.
>[!def] Definition : Boundary of an $m$-chain
>$$\begin{gather}\Sigma=\sum\limits_in_i\sigma_i\\\implies\partial\Sigma=\sum\limits_in_i\partial\sigma_i\end{gather}$$



