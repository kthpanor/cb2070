(exercise-2)=
Fock matrices and SCF procedure
===============================

Density matrix
--------------
For a given set of molecular orbital (MO) coefficients, the density matrix becomes equal to

$$
    D_{\gamma\delta} = \sum_{i=1}^N C_{\gamma i}^* C_{\delta i}
$$

where the summation over occupied orbitals include $\alpha$- as well as $\beta$-spin orbitals. For a closed shell system, these two sets of MO coefficients are equal.

Fock matrix
-----------
A density matrix defines a Fock matrix according to

$$
    F_{\alpha\beta} = h_{\alpha\beta} + \sum_{\gamma\delta} D_{\gamma\delta}
    \left[
    \langle \alpha \gamma | \beta \delta \rangle -
    \langle \alpha \gamma | \delta \beta \rangle
    \right]
$$

introducing the one-electron Hamiltonian as well as the Coulomb and exchange two-electron integrals.

Hartree--Fock equation
----------------------
The Hartree--Fock (HF) equation in the atomic orbital (AO) basis takes the form

$$
    \mathbf{F}\mathbf{C} = \mathbf{S} \mathbf{C} \boldsymbol{\varepsilon} 
$$

The Fock matrix depends on the MO coefficients through the density matrix so this equation needs to be solved iteratively in an SCF procedure. The HF equation corresponds to a matrix eigenvalue problem in a non-orthogonal basis. The overlaps between basis functions are collected in matrix $\mathbf{S}$. In this exercise, we will go through the steps required to solve the HF equation for the eigenvalues (or orbital energies) collected on the diagonal of matrix $\boldsymbol{\varepsilon}$ and the associated eigenvectors (or MO coefficients). This exercise will use the results from the associated problem in the problem set.

Exercises
---------

1. Perform an SCF optimization to obtain the Hartree--Fock wave function of water as described [here](section-scf).

2. Diagonalize the overlap matrix, $\mathbf{S}$, with use of NumPy routine `linalg.eigh`. The access to the overlap matrix and other SCF tensors is described in [this section](section-scf-info). Check that all eigenvalues are positive and, with use of NumPy routine `matmul` for matrix multiplication, verify that $\mathbf{U}^\dagger \mathbf{U} = \mathbf{I}$, where $ \mathbf{U}$ collects the eigenvectors of $\mathbf{S}$ as columns.

3. Determine the transformation matrix $\mathbf{X} = \mathbf{S}^{-1/2}$.

4. Determine the transformed Fock matrix $\mathbf{F}'$.

5. Solve the transformed Hartree--Fock equation
    $\mathbf{F}'\mathbf{C}' = \mathbf{C}' \boldsymbol{\varepsilon}$
    for eigenvalues $\boldsymbol{\varepsilon}$ and eigenvectors $\mathbf{C}'$.

6. Determine $\mathbf{C}$ from $\mathbf{C}'$.

7. Determine the density matrix as expressed in terms of MO coefficients in the equation above and check the SCF convergence by comparing to the SCF tensor object.

