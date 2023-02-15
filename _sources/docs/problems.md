# Problems

## Session 1

**1**.
The direct product of matrices is also known as the Kronecker product and it is defined as

$$
\mathbf{A} \otimes \mathbf{B} =
\begin{pmatrix}
a_{11} \mathbf{B} & \cdots & a_{n1} \mathbf{B} \\
\vdots & \ddots & \vdots \\
a_{n1} \mathbf{B} & \cdots & a_{nn} \mathbf{B} \\
\end{pmatrix}
$$

Two important identities are

\begin{eqnarray*}
\mathbf{A} \otimes (\mathbf{B} + \mathbf{C} ) & = &
\mathbf{A} \otimes \mathbf{B} + \mathbf{A} \otimes \mathbf{C} \\
(\mathbf{A} \otimes \mathbf{B})(\mathbf{C} \otimes \mathbf{D}) & = &
(\mathbf{A} \mathbf{C}) \otimes (\mathbf{B} \mathbf{D}) 
\end{eqnarray*}

Let $\mathbf{A}$ and $\mathbf{B}$ be operator matrices in charge conjugation and spin spaces of a single electron, respectively. Let $\mathbf{C}$ and $\mathbf{D}$ be two corresponding state vectors. Show the second identity by explicit matrix calculations.

---------------------------------------------------------------------------

**2**.
Generators for rotations of electronic wave functions are the angular momentum operators. A finite rotation an angle $\phi$ about axis $\mathbf{n}$ is achieved by the *total* angular momentum operator

$$
\hat{R}(\phi, \mathbf{n} ) = 
\exp(-i\frac{\phi}{\hbar}(\mathbf{n} \cdot \hat{\mathbf{j}})) = 
\exp(-i\frac{\phi}{\hbar}(\mathbf{n} \cdot \hat{\mathbf{l}})) \otimes 
\exp(-i\frac{\phi}{\hbar}(\mathbf{n} \cdot \hat{\mathbf{s}})) 
$$

Show that

$$
\hat{\mathbf{j}} = \hat{\mathbf{l}} \otimes \hat{\mathbf{I}} +
\hat{\mathbf{I}} \otimes \hat{\mathbf{s}}
$$

or, in other words,

$$
e^{\mathbf{A}} \otimes e^{\mathbf{B}} = 
e^{\mathbf{A}\otimes \mathbf{I} + \mathbf{I} \otimes \mathbf{B}}
$$

---------------------------------------------------------------------------

**3**.
The rotation operator in spin space, resulting in a rotation an angle $\phi$ about axis $\mathbf{n}$, is
%
$$
R(\phi, \mathbf{n}) = e^{-i\phi(\mathbf{n} \cdot \boldsymbol{\sigma})/2}
$$
where the Cartesian components of the spin operator, $\boldsymbol{\sigma}$, are the Pauli spin matrices. Show that
%
$$
R(\phi, \mathbf{n}) = \cos(\phi/2) \mathbf{I} - i 
\sin(\phi/2) (\mathbf{n} \cdot \boldsymbol{\sigma})
$$

---------------------------------------------------------------------------

**4**.
A state vector in a two-electron spin-space is given by

$$
| \Psi \rangle =
\begin{pmatrix}
\alpha_1 \\ \beta_1
\end{pmatrix}
\otimes
\begin{pmatrix}
\alpha_2 \\ \beta_2
\end{pmatrix} =
\begin{pmatrix}
\alpha_1 \alpha_2 \\ \alpha_1 \beta_2 \\
 \beta_1  \alpha_2 \\  \beta_1 \beta_2
\end{pmatrix}
$$

(a) What are the explicit forms of the $z$-component of the spin operator, $\hat{S}_z$, expressed with and without use of direct products?

(b) Is $\hat{S}_z$ a one- or two-electron operator?

(c) Determine $\hat{S}_z | \Psi \rangle$.

(d) Is $| \Psi \rangle$ an eigenvector to $\hat{S}_z$?

(e) What are the eigenvalues and eigenvectors of $\hat{S}_z$?

(f) Are the eigenvectors unique?

---------------------------------------------------------------------------

**Extra**

Consider the operator
%
$$
\hat{\Omega} = 
\begin{pmatrix}
a & c\\
c & b\\
\end{pmatrix} ; \quad a,b,c>0; \quad b>c
$$

(a) Based on a starting vector, $| {\Psi}_1 \rangle$, pointing in a predefined direction, design a scheme to define a bi-orthogonal basis. The basis should fulfill
%
\begin{eqnarray*}
| \Phi_i \rangle = \hat{\Omega} | \Psi_i \rangle; \quad 
\langle \Psi_i | \Phi_j \rangle = \delta_{ij}
\end{eqnarray*}

(b)
In this basis, show that
%
$$
\hat{\Omega} = \sum_i | \Phi_i \rangle\langle \Phi_i |
$$

(c) Implement your scheme in Python and demonstrate that it numerically works for 
%
$$
\hat{\Omega} = 
\begin{pmatrix}
3 & 1\\1 & 7\\
\end{pmatrix}; \quad
%
| \Psi_1 \rangle = N
\begin{pmatrix}
1\\2\\
\end{pmatrix}
$$

where $N$ is a normalization constant.

(d) Describe how the situation changes when the starting vector is chosen as an eigenvector of $\hat{\Omega}$.

---------------------------------------------------------------------------

## Session 2

**1**.
Let us define the one-electron density operator as

$$
\hat{n}(\mathbf{r}) = 
\sum_{i=1}^N \delta(\mathbf{r} - \mathbf{r}_i)
$$

Show that
%
\begin{equation*}
\label{eq:den1-oper}
n(\mathbf{r}) = \langle \Psi | \hat{n}(\mathbf{r}) | \Psi \rangle
\end{equation*}
%
is in agreement with the definition of the one-electron density based on a probabilistic interpretation of the wave function.

---------------------------------------------------------------------------

**2**.
For an $N$-electron system in a state described by a Slater determinant, show that the one-electron density becomes
%
$$
n(\mathbf{r}) = \sum_{i=1}^N |\psi_i(\mathbf{r})|^2
$$
%
Reflect on your results in terms of a system of independent particles.

---------------------------------------------------------------------------

**3**.
For an $N$-electron system in a state described by a Slater determinant, show that the two-electron density becomes
%
\begin{equation*}
n(\mathbf{r}_1, \mathbf{r}_2)
= \sum_{i=1}^N
\sum_{j=1}^N 
\left[\rule{0pt}{12pt}
|\psi_i(\mathbf{r}_1)|^2
|\psi_j(\mathbf{r}_2)|^2
-
\psi_i^\dagger(\mathbf{r}_1)
\psi_j^\dagger(\mathbf{r}_2)
\psi_j(\mathbf{r}_1)
\psi_i(\mathbf{r}_2)
\right]
\end{equation*}
%
Reflect on your results in terms of a system of independent particles. Specifically focus the discussion around orbital pairs $(i,j)$ with identical and opposite spins, respectively.

---------------------------------------------------------------------------

## Session 3

**1**.
Consider the one-electron operator

$$
\hat{\Omega} = \sum_{i=1}^N \hat{\omega}(i)
$$

Show that the transition matrix element for $\hat{\Omega}$ between a reference Slater determinant and a corresponding single electron excited determinant equals

$$
\langle \Psi_i^s | \hat{\Omega} | \Psi \rangle =
\langle \psi_s | \hat{\omega} | \psi_i \rangle 
$$

where orbitals $i$ and $s$ are occupied and unoccupied in the reference state, respectively. Reflect on your results in terms of a system of independent particles. If $\hat{\Omega}$ is a pure orbital operator, what is the implication on the transition matrix elements?

---------------------------------------------------------------------------

**2**.
Repeat the steps in the preious exercise and derive an expression for transition moments between a reference determinant and an associated doubly-excited determinant, i.e.,

$$
\langle \Psi_{ij}^{st} | \hat{\Omega} | \Psi \rangle 
$$

---------------------------------------------------------------------------

**3**.
Derive an explicit expression for the HF energy in terms of one- and two-electron integrals. Use the following notation for the $N$-electron Hamiltonian

$$
\hat{H} = \sum_{i=1}^N \hat{h}(i) +
\sum_{j>i}^N \hat{g}(i,j)
$$

For the specific (and important) case of a closed-shell HF ground state, simplify your result so that the final expression is given in terms of integrals with respect to spatial orbitals.

---------------------------------------------------------------------------

**Extra**

Let $|\Psi \rangle$ be a Slater determinant and $\hat{\Omega}$ a two-electron operator

$$
\hat{\Omega} = \sum_{j>i}^N \hat{\omega}(i,j)
$$
Show the following relations for the corresponding integrals
%
\begin{align*}
    \langle \Psi | \hat{\Omega} | \Psi \rangle &=
    \frac{1}{2} \sum_{i,j}^N
    \left[\rule{0pt}{12pt}
    \langle ij| \hat{\omega} | ij \rangle - \langle ij|  \hat{\omega} |ji \rangle
    \right]
    \\
    \langle \Psi | \hat{\Omega} | \Psi_{i}^{s} \rangle &=
    \sum_{j}^N
    \left[\rule{0pt}{12pt}
    \langle ij|  \hat{\omega} |sj \rangle - \langle ij|  \hat{\omega} |js \rangle
    \right]
    \\
    \langle \Psi | \hat{\Omega} | \Psi_{ij}^{st} \rangle &=
     \langle ij|  \hat{\omega} |st \rangle - \langle ij|  \hat{\omega} |ts \rangle
\end{align*}

---------------------------------------------------------------------------

## Session 4

**1**.
The Fock operator reads

$$
\hat{f} = \hat{h} + \sum_{i=1}^N 
\left(
\hat{J}_i - \hat{K}_i
\right)
$$

where
%
\begin{eqnarray*}
\hat{J}_i | \psi_a \rangle & = & 
\left[
\int 
\frac{
\left|\psi_i(\mathbf{r}')\right|^2
}{
|\mathbf{r} - \mathbf{r}'|
} d^3\mathbf{r}'
\right]
| \psi_a \rangle \\
%
\hat{K}_i | \psi_a \rangle & = & 
\left[
\int 
\frac{
\psi_i^\dagger(\mathbf{r}') \psi_a(\mathbf{r}')
}{
|\mathbf{r} - \mathbf{r}'|
} d^3\mathbf{r}'
\right]
| \psi_i \rangle 
\end{eqnarray*}
%
Show that $\hat{f}$ is Hermitian.

---------------------------------------------------------------------------

**2**.
Introducing a Lagrangian

$$
\mathcal{L}[\{\psi_i\}] = E[\{\psi_i\}] - \sum_{i,j=1}^N \varepsilon_{ji}
(\langle \psi_i|\psi_j \rangle - \delta_{ij})
$$

Show that the condition that the first variation in the Lagrangian vanishes, i.e., $\delta \mathcal{L} = 0$, leads to the following equation from which we can determine the set of orbitals

$$
\hat{f} |\psi_i \rangle = \sum_{j=1}^N \varepsilon_{ji} |\psi_j \rangle
$$

Tip: You will need the previously derived expression for the HF energy.

---------------------------------------------------------------------------

## Session 5

**1**.
Introduce a unitary transformation of the occupied orbitals

$$
|\psi_i'\rangle = \sum_{j=1}^N |\psi_j\rangle U_{ji}
$$

(a) Show that the Fock operator, $\hat{f}$, is invariant under this orbital transformation.

(b) Choose a unitary transformation such that the matrix representation of the Fock operator becomes diagonal. Show that the Hartree--Fock equation in this basis takes the form

$$
\hat{f} |\psi_a \rangle = \varepsilon_{a} |\psi_a \rangle
$$

---------------------------------------------------------------------------

**2**.
Show that *ionization potentials* and *electron affinities* are given by minus the orbital energies, i.e.,
%
\begin{align*}
    \mathrm{IP} = E^{N-1}_i - E_\mathrm{HF}^N &= -\varepsilon_i \\
    \mathrm{EA} = E_\mathrm{HF}^N - E^{N+1}_s &= -\varepsilon_s
\end{align*}
%
This result is known as Koopmans' theorem.

---------------------------------------------------------------------------

## Session 6

**1**.
Introduce a set of non-orthogonal basis functions (or atomic orbitals) denoted as $\{\chi_\alpha\}$. In this basis, show that the matrix representation of the Fock operator can be written on the form

$$
F_{\alpha\beta} = 
\langle \chi_\alpha | \hat{f} | \chi_\beta \rangle = 
h_{\alpha\beta} + 
\sum_{\gamma\delta}
D_{\gamma\delta}
\left[\rule{0pt}{12pt}
\langle \chi_\alpha \chi_\gamma | \hat{g} | \chi_\beta \chi_\delta \rangle
-
\langle \chi_\alpha \chi_\gamma | \hat{g} | \chi_\delta \chi_\beta \rangle
\right]
$$

---------------------------------------------------------------------------

**2**.
Show the following relation between the one-electron density and the density matrix

$$
n(\mathbf{r}) = \sum_{\gamma\delta}
D_{\gamma\delta} \chi_\gamma^*(\mathbf{r})\chi_\delta(\mathbf{r})
$$

---------------------------------------------------------------------------

**3**.
Consider the Hartree--Fock equation
%
\begin{equation*}
    \mathbf{F}\mathbf{C} = \mathbf{S} \mathbf{C} \boldsymbol{\varepsilon} 
\end{equation*}
%
Introduce a non-unitary change of the AO basis
%
\begin{equation*}
    \chi_\alpha'(\mathbf{r}) = \sum_\beta X_{\beta\alpha}
     \chi_\beta(\mathbf{r}) ; \quad \mathbf{X} = \mathbf{S}^{-1/2} 
\end{equation*}

(a) Show that $\{\chi_\alpha'\}$ forms an orthonormal set.

(b) Show that $\mathbf{S}$ is Hermitian and positive definite.

(c) Show that the form of the Hartree--Fock equation in this new basis becomes
%
\begin{equation*}
    \mathbf{F}'\mathbf{C}' = \mathbf{C}' \boldsymbol{\varepsilon} 
\end{equation*}

---------------------------------------------------------------------------

## Session 7

**1**.
Return to Problem 4 of Session 1.

(a) What is the explicit matrix form of the spin operator, $\hat{S}^2$?

(b) Is $\hat{S}^2$ a one- or two-electron operator? How can you tell solely from the matrix representation?

(c) What are the eigenvalues and eigenvectors of $\hat{S}^2$?

(d) Determine the pairs of spin quantum numbers, $S$ and $M_S$, for the eigenvectors. Is this set of quantum numbers sufficient to uniquely label the states?

(e) Classify the states as singlets, doublets, triplets, etc.?

---------------------------------------------------------------------------

**2**.
Consider an atomic two-electron system such as helium in a state described by a Slater determinant
%
\begin{equation*}
    | \Psi \rangle = | \psi_1\psi_2 \rangle
\end{equation*}
%
where
%
\begin{equation*}
    \psi_1(\mathbf{r}) = R_1(r) Y_{00}(\theta,\varphi) \otimes 
    \begin{pmatrix}
    1\\0
    \end{pmatrix}
    ; \quad
    \psi_2(\mathbf{r}) = R_2(r) Y_{11}(\theta,\varphi) \otimes 
    \begin{pmatrix}
    1\\0
    \end{pmatrix}
\end{equation*}
%
In concern with the angular momenta of this state, we can henceforth disregard the radial parts of the orbitals and only consider the spherical harmonics, $Y_{lm}$, and the spin components. The operator of *total* angular momentum in $N$-particle space is
%
\begin{equation*}
    \hat{\mathbf{J}} = \hat{\mathbf{L}} + \hat{\mathbf{S}}
\end{equation*}
%
where
%
\begin{equation*}
    \hat{\mathbf{J}} = \sum_{i=1}^N \hat{\mathbf{j}}(i)
\end{equation*}

It is also convenient to introduce ladder operators that take the form
%
\begin{equation*}
    \hat{J}_\pm =  \hat{J}_x \pm i \hat{J}_y
\end{equation*}

(a) Show that $\Psi$ is *anti-symmetric* and *symmetric* with respect to particle interchange in orbital and spin spaces, respectively.

(b) Show that

$$
\hat{J}^2 = \hat{J}^2_z + \hbar \hat{J}_z + \hat{J}_- \hat{J}_+
$$

(c) Show that 

$$
\hat{J}_z |\Psi\rangle = 2 \hbar | \Psi \rangle
$$

(d) Based on the relation

$$
\hat{J}^2 |\Psi\rangle = J(J+1) \hbar^2 | \Psi \rangle
$$

Determine $J$ as well as the corresponding values for $L$ and $S$.

(e) Write down the *term symbol* for this given state. The term symbol notation in atomic physics is defined by

$$
{}^{2S+1} L_{J}
$$

where $2S+1$ refers to the spin multiplicity and $L$ is replaced by a letter $\{S, P, D, F, \ldots\}$ depending on its value. This nomenclature is derived from the characteristics of the spectroscopic lines corresponding to (s, p, d, f) orbitals: *sharp*, *principal*, *diffuse*, and *fundamental*.

-----------------------------------------------------------------------------

**Extra**

Consider the hydrogen molecule. In a minimal basis consisting of two $1s$ atomic orbitals (AOs), the solution of the Hartree--Fock problem will give us two spatial molecular orbitals (MOs): the bonding and symmetric $\phi_S$ as well as the anti-bonding and anti-symmetric $\phi_A$. The explicit form of these orthogonal MOs will be
\begin{eqnarray*}
\phi_S(\mathbf{r}) & = & N_S
\left[\rule{0pt}{12pt}
\chi_{1s}(\mathbf{r} - \mathbf{R}_1) +
\chi_{1s}(\mathbf{r} - \mathbf{R}_2)
\right] \\
\phi_A(\mathbf{r}) & = & N_A
\left[\rule{0pt}{12pt}
\chi_{1s}(\mathbf{r} - \mathbf{R}_1) -
\chi_{1s}(\mathbf{r} - \mathbf{R}_2)
\right]
\end{eqnarray*}
where $N_S$ and $N_A$ are normalization constants.

(a) Write down all possible Slater determinants that we can form in the minimal basis. Use a shorthand notation for determinants in terms of $|\psi_S\psi_{\bar{A}}\rangle$ to denote occupation of spin orbitals $\psi_S(\mathbf{r}) = \phi_S(\mathbf{r})\alpha$ and $\psi_{\bar{A}}(\mathbf{r}) = \phi_A(\mathbf{r})\beta$.

(b) Show that all determinants are eigenstates of the $z$-component of the many-electron spin operator, $\hat{S}_z$. What are the eigenvalues $M_S$, i.e., the spin projection of the molecule along the $z$-axis?

(c) Show that some, but not all, determinants are eigenfunctions of the magnitude of the spin operator, $\hat{S}^2$. What are the eigenvalues of the eigenstates? Identify $S$ from the eigenvalues $S(S + 1)\hbar^2$.

(d) For the set of determinants that are not eigenstates of $\hat{S}^2$, construct the spin-adapted configurations and show explicitly that these are eigenstates. Determine the eigenvalues, or rather the values of $S$.

(e) Determine the electronic energies of all the eigenstates in the minimal basis. Express your result in terms of spatial one- and two-electron integrals. Order the states in an energy level diagram and indicate their respective spin state.

(f) Let us consider the three-fold degenerate triplet state $|T_1 , M_S \rangle$ in the band gap. Determine the action of the ladder operators on $|T_1, M_S = -1 \rangle$, i.e., compute $\hat{S}_-|T_1, -1 \rangle$ and $\hat{S}_+ | T_1, -1 \rangle$. Compare your result with the action of $\hat{j}_\pm$ on the single-particle state that you studied in your course on Quantum Mechanics.

---------------------------------------------------------------------------

## Session 8

**1**.
Consider the ethylene molecule.

(a) Use the flowchart in the Appendix to determine the molecular point group.

(b) Introduce a coordinate system with the $x$-axis along the carbon--carbon bond and $z$ being the out-of-plane axis. Identify all symmetry operations of the group (ignore improper rotations).

(c) Construct the group table.

(d) Introduce a *less than* minimal basis of atomic orbitals by only considering the four hydrogen $1s$-atomic orbitals, $\{\chi_\alpha\}^4_{\alpha=1}$. This is not an adequate basis set but serves here to illustrate the principles of symmetry. Determine the action of the symmetry operations on each and every $\chi_\alpha$, in other words obtain the matrices $\Gamma(\hat{G})$ determined by

$$
\hat{G}\chi_\alpha = \sum_\beta \chi_\beta \Gamma_{\beta\alpha}(\hat{G})
$$

where $\hat{G}$ denotes a given symmetry operation. These matrices form a homomorphic, reducible, representation of the group; convince yourself why this is so.


(e) Find a unitary transformation matrix $U$ such that the transformed matrices

$$
\Gamma^{'}(\hat{G}) = U^\dagger \Gamma(\hat{G}) U
$$

become block diagonal for all $\hat{G}$, and with blocks of dimensions as small as possible. Each of the sets of sub-matrices $\Gamma^{(i)}(\hat{G})$ forms an irreducible representation (irrep) of the group.

(f) Find the characters of the matrices $\Gamma^{(i)}(\hat{G})$ and set up the character table of the group. The chemical notation for one-dimensional irreps (a one-dimensional matrix is a number) is $A$ (if the characters for all $C_2$ operations are equal to 1) or $B$ (otherwise). Furthermore, if inversion $\hat{i}$ is a symmetry operation then an additional label is used, either $g$ (gerade) or $u$ (ungerade). Thus possible irreps may be for instance $A_{1g}$, $B_{2u}$, etc.

(g) By applying $U$ to the set of basis functions $\{\chi_\alpha\}$, construct the symmetry-adapted basis functions $\{\chi_\alpha^\mathrm{SA}\}$.

(h) Each symmetry-adapted basis function transforms under the symmetry operators according to the characters in the character table, i.e.,

$$
\hat{G} \chi_\alpha^\mathrm{SAO} = \pm \chi_\alpha^\mathrm{SAO}
$$

Compare with the rows in character table and determine which irreps are spanned by your set of symmetry-adapted basis functions. 

(i)  What additional AOs would you need to add to your calculation in order to span all irreps?

---------------------------------------------------------------------------

## Session 9

**1**.
Consider a *trans*-butadiene molecule in the $xy$-plane.

(a) Use the flowchart in the Appendix to determine the molecular point group.

(b) Introduce a *less than* minimal basis of atomic orbitals by only considering the four carbon $2p_z$-atomic orbitals, $\{\chi_\alpha\}^4_{\alpha=1} = \{p^\alpha_z\}^4_{\alpha=1}$. Based on experience and intuition, form the symmetry-adapted basis functions $\{\chi_\alpha^\mathrm{SAO}\}$ and order them in energy.

(c) With the character table in the Appendix, determine to which irreducible representations the SAOs belong.

(d) Run a Jupyter notebook SCF optimization of the HF wave function

```
C         -1.83140       -0.13080        0.00000
C         -0.60240        0.39750        0.00000
C          0.60240       -0.39750        0.00000
C          1.83140        0.13080        0.00000
H         -2.70360        0.51430        0.00000
H         -1.99690       -1.20300        0.00000
H         -0.49790        1.47890        0.00000
H          0.49790       -1.47920        0.00000
H          1.99690        1.20300        0.00000
H          2.70360       -0.51430        0.00000
```

Identify the $\pi$- and $\pi^*$-orbitals in the program output and compare the printed MO coefficients with your SAOs.

(e) What are the symmetries of the HF ground state and the lowest $\pi\pi^*$-excited state?

(f) Which Cartesian components of the electric-dipole operator couple the two states, or in other words have

$$
\langle \Psi_\pi^{\pi^*} | \hat{\mu}_\alpha | \Psi_\mathrm{HF} \rangle \neq 0 ;
\quad \alpha \in \{x,y,z\}
$$

Note: This consideration is the underlying principle for *spectroscopic selection rules* in physics.


---------------------------------------------------------------------------

## Session 10

**1**.
Consider the hydrogen molecule at the equilibrium bond length of 0.741 {\AA}. The HF ground state and the doubly excited determinant are denoted

$$
| \Psi_\mathrm{HF} \rangle = |\sigma_g, \overline{\sigma}_g \rangle = |1, \bar{1} \rangle; \quad
| \Psi_{g\bar{g}}^{u\bar{u}} \rangle = |\sigma_u, \overline{\sigma}_u \rangle = |2, \bar{2} \rangle
$$

In a minimal STO-3G basis set, the following integrals  (in a.u.) are available in the spatial MO basis:

| Integral | Value |
|:----------------:|----------:|
| $h_{11}$   | $-1.2527$ |
| $h_{22}$   | $-0.4757$ |
| $(11 \mid 11)$  | $0.6746$  |
| $(11\mid 22)$  | $0.6635$  |
| $(22\mid 22)$  | $0.6975$  |
| $(12\mid 12)$  | $0.1813$  |

(a) Form the configuration interaction doubles (CID) Hamiltonian.

(b) Express the matrix elements of the CID Hamiltonian in terms of one- and two-electron integrals.

(c) Insert numerical values and determine the CID ground-state energy.

(d) Determine the CID estimate of the correlation energy both in absolute terms and relative to the HF energy.

(e) What are the percentage weights of the determinants $| \Psi_\mathrm{HF} \rangle$ and $| \Psi_{g\bar{g}}^{u\bar{u}} \rangle$ in the CID ground-state wave function?

---------------------------------------------------------------------------

## Session 11

**1**.
Consider the setup made in Problem 1 of Session 10. Write the CID ground-state wave function on the following form

$$
|\Psi \rangle = \cos\theta
| \Psi_\mathrm{HF} \rangle +
\sin\theta | \Psi_{g\bar{g}}^{u\bar{u}} \rangle
$$

(a) Show that

$$
E(\theta) = \cos^2\theta E_\mathrm{HF} + \sin^2\theta E_\mathrm{u\bar{u}} +
\sin 2\theta \, (12|12)
$$

(b) Show that the energy is minimized by

$$
\theta = \frac{1}{2} \mathrm{arctan}
\left[
\frac{
2(12|12)
}{
E_\mathrm{HF} - E_\mathrm{u\bar{u}}
}
\right]
$$

(c) Compare the minimized energy to that obtained in Problem 1 in Session 10.

---------------------------------------------------------------------------

**2**.
Consider the setup made in Problem 1 of Session 10 and partition the Hamiltonian according to

$$
\hat{H} = \hat{H}_0 + \hat{V} + V^\mathrm{n,rep}
$$

with

$$
\hat{H}_0 =
\begin{bmatrix}
2h_{11} & 0 \\
0 & 2h_{22} \\
\end{bmatrix}; \quad
\hat{V} =
\begin{bmatrix}
(11|11) & (12|12) \\
(12|12) & (22|22) \\
\end{bmatrix}
$$

The basis for Rayleigh--Schrödinger perturbation theory (RSPT) are given by the solutions to

$$
\hat{H}_0 | \Phi_n \rangle = \mathcal{E}_n | \Phi_n \rangle
$$

The exact ground state and energy are expanded in orders of $\hat{V}$:

$$
|\Psi \rangle = \sum_{k=0}^\infty |\Psi^{(n)} \rangle; \quad
E = \sum_{k=0}^\infty E^{(n)}
$$

(a) Determine $\Psi^{(0)}$ and $E^{(0)}$.

(b) Determine $E^{(1)}$ and compare your result with the HF energy.

(c) Determine $\Psi^{(1)}$ and $E^{(2)}$.

(d) What are the percentage weights of the determinants $| \Psi_\mathrm{HF} \rangle$ and $| \Psi_{g\bar{g}}^{u\bar{u}} \rangle$ in the ground-state wave function that are correct to first order in RSPT?

---------------------------------------------------------------------------

## Session 12

**1**.
Consider the setup made in Problem 1 of Session 10 and partition the Hamiltonian according to

$$
\hat{H} = \hat{F} + \hat{V} + V^\mathrm{n,rep}
$$

with

$$
\hat{V} = \hat{H} - \hat{F} - V^\mathrm{n,rep}
$$

The basis for Møller--Plesset perturbation theory (MPPT) are given by the solutions to

$$
\hat{F} | \Phi_n \rangle = \mathcal{E}_n | \Phi_n \rangle
$$

The exact ground state and energy are expanded in orders of $\hat{V}$:

$$
|\Psi \rangle = \sum_{k=0}^\infty |\Psi^{(n)} \rangle; \quad
E = \sum_{k=0}^\infty E^{(n)}; \quad
$$

(a) Determine $\Psi^{(0)}$ and $E^{(0)}$.

(b) Determine $E^{(1)}$ and compare your result with the HF energy.

(c) Determine $\Psi^{(1)}$ and $E^{(2)}$ and compare your result with the corresponding values in Problem 2 of Session 11 obtained using a different partitioning of the Hamiltonian.

(d) Determine $\Psi^{(n-1)}$ and $E^{(n)}$ up to order $n = 6$ in perturbation theory. Compare your result for the correlation energy to the variational CID result obtained in Problem 1 of Session 10.

---------------------------------------------------------------------------

**2**.
The standard expression for the MP2 correlation energy of a closed-shell system written in terms of two-electron integrals and orbital energies reads

$$
E_\mathrm{MP2} = - \sum_{i,j,s,t}
\frac{
(is|jt) \big[ 2  (si|tj) - (sj|ti) \big]
}{
\varepsilon_s + \varepsilon_t - \varepsilon_i - \varepsilon_j
}
$$

where summations run over occupied (indices $i$ and $j$) and unoccupied (indices $s$ and $t$) spatial MOs. Use this formula to determine the MP2 energy and compare to your result from Problem 1 od Session 12.

---------------------------------------------------------------------------

## Session 13

**1**.
Consider the setup made in Problem 1 of Session 10. With the approach from Problem 1 of Session 2, determine an expression for the  one-electron density, $n(\mathbf{r})$, of the CID wave function in terms of the spatial MOs.

---------------------------------------------------------------------------

**2**.
Let us define the two-electron density operator as

$$
\hat{n}(\mathbf{r}, \mathbf{r}') = 
\sum_{j>i}^N \left[
\delta(\mathbf{r} - \mathbf{r}_i) \delta(\mathbf{r}' - \mathbf{r}_j)
+
\delta(\mathbf{r} - \mathbf{r}_j) \delta(\mathbf{r}' - \mathbf{r}_i)
\right]
$$

Show that
%
\begin{equation*}
\label{eq:den2-oper}
n(\mathbf{r}, \mathbf{r}') = 
\langle \Psi | \hat{n}(\mathbf{r}, \mathbf{r}') | \Psi \rangle
\end{equation*}
%
is in agreement with the definition of the one-electron density based on a probabilistic interpretation of the wave function.

---------------------------------------------------------------------------

**3**.
Consider the setup made in Problem 1 of Session 10. With the approach from Problem 2 of Session 13, determine an expression for the  two-electron density, $n(\mathbf{r}, \mathbf{r}')$, of the CID wave function in terms of the spatial MOs.

---------------------------------------------------------------------------

## Session 14

Choose from the extra problems.

