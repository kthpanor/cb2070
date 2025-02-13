(lab-5)=
# 5. Two-particle densities and electron correlation

The Hartree--Fock method results in total electronic energies that are typically within 1 % of the exact values and several other molecular properties are quite well described as well at this level of theory. Nevertheless, tremendous efforts have been made to develop and implement computationally feasible methods that improve upon the HF description of the system. As to understand why this is motivated, there is nothing more revealing of the shortcomings of the HF wave function than a study of the reduced two-particle density. 

In this exercise, we will study $n(\mathbf{r}, \mathbf{r}')$ for the hydrogen molecule in the electronic ground state. We will adopt the minimal STO-3G basis set and make use of the HF and CI doubles (CID) levels of theory. In a minimal basis set, CID provides a full-CI description of the system and thus provides the "exact" reference data for the correlation energy and other electronic properties. The CID part of this exercise brings you back to the associated problem in the problem set.

## One- and two-particle densities
The one-particle density for an $N$-electron system is defined as

\begin{equation*}
\label{eq:one-part-den}
    n(\mathbf{r}) = N \int 
    \Psi^\dagger(\mathbf{r}, \mathbf{r}_2, \ldots,\mathbf{r}_N)
    \Psi(\mathbf{r}, \mathbf{r}_2, \ldots,\mathbf{r}_N)
    \, d^3\mathbf{r}_2 \cdots d^3\mathbf{r}_N
\end{equation*}

and it refers to the probability density of finding any one electron at position $\mathbf{r}$ in space regardless of the distribution of others. It fulfills

\begin{equation*}
     \int n(\mathbf{r}) \, d^3\mathbf{r} = N
\end{equation*}

The two-particle density for an $N$-electron system is defined as

\begin{equation*}
 \label{eq:two-part-den}
   n(\mathbf{r}_1, \mathbf{r}_2) = N(N-1)\int 
    \Psi^\dagger(\mathbf{r}_1, \mathbf{r}_2, \ldots,\mathbf{r}_N)
    \Psi(\mathbf{r}_1, \mathbf{r}_2, \ldots,\mathbf{r}_N)
    \, d^3\mathbf{r}_3 \cdots d^3\mathbf{r}_N
\end{equation*}

and it refers to the probability density of finding one electron at position $\mathbf{r}_1$ and another at position $\mathbf{r}_2$ in space regardless of the distribution of others.


## Exercises

1. Perform an SCF optimization to obtain $|\Psi_\mathrm{HF}\rangle$. Perform a cost--gain analysis of the bond formation in terms of (i) kinetic energy, (ii) electronic--nuclear potential energy, (iii) electron--electron repulsion energy, and (iv) nuclear repulsion energy. Tip: From the virial theorem in physics you know the exact atomic kinetic and potential energies.

2. Use arguments of symmetry to explain why there is no coupling between the singles and doubles block in the CISD Hamiltonian, which is the reason why CID provides a full-CI description in the present case.

3. Form the CID Hamiltonian from the one- and two-electron integrals. Diagonalize your Hamiltonian to obtain the correlation energy as well as the weights of configurations.

4. With use of the defining expression, determine a computationally tractable expression for the one-particle density for the CID wave function. Plot the densities for the HF and CID wave functions along the internuclear axis. How do the densities compare?

5. With use of the defining expression, determine a computationally tractable expression for the two-particle density for the CID wave function. Plot the densities for the HF and CID wave functions for one electron coordinate fixed to a hydrogen nucleus and the other electron coordinate varying along the internuclear axis. How do the densities compare?
