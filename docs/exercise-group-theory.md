(exercise-4)=
Group theory and spatial symmetries of wave functions
=====================================================

Molecular system
----------------
In this exercise, we will study the ethylene molecule and reveal the spatial symmetries of ground- and excited-state wave functions as well as the molecular orbitals (MOs). The exercise is based on the results derived in the associated problem in the problem set. We will adopt a minimal basis set, STO-3G, and the following molecular structure corresponding to the equilibrium geometry in the electronic ground state:

```
mol_str = """
H        1.21655197    0.92414474    0.00000000
H        1.21655197   -0.92414474    0.00000000
H       -1.21655197   -0.92414474    0.00000000
H       -1.21655197    0.92414474    0.00000000
C        0.67759997    0.00000000    0.00000000
C       -0.67759997    0.00000000    0.00000000
"""
molecule = vlx.Molecule.read_str(mol_str, units='angstrom')
```

Ordering of atomic orbitals
---------------------------
The program internal ordering of atomic orbitals (AOs) is determined by

1. Orbital angular momentum, $l$
2. Projection of orbital angular momentum, $m_l$
3. The order of atoms in the user input

Orbital notation
----------------
It can be convenient to introduce the following notation
%
\begin{equation*}
    | \boldsymbol{\chi} \rangle = 
    \Big(
    | \chi_1 \rangle, \ldots, | \chi_n \rangle
    \Big); \quad
    | \boldsymbol{\phi} \rangle = 
    \Big(
    | \phi_1 \rangle, \ldots, | \phi_n \rangle
    \Big)
\end{equation*}
%
i.e., we collect the AO basis functions, $\{\chi_\alpha(\mathbf{r})\}$, and (spatial) MOs, $\{\phi_i(\mathbf{r})\}$, in their ket-form into *row* vectors. The associated bra-forms are then identified as *column* vectors that can be compactly written
%
\begin{equation*}
    \langle \boldsymbol{\chi} | = | \boldsymbol{\chi} \rangle^\dagger; \quad
     \langle \boldsymbol{\phi} | = | \boldsymbol{\phi} \rangle^\dagger
\end{equation*}
%
The set of MOs relate to the set of AOs by means of the matrix of MO coefficients
%
\begin{equation*}
     | \boldsymbol{\phi} \rangle =  
     | \boldsymbol{\chi} \rangle \mathbf{C}
\end{equation*}
%
and the overlap and Fock matrices in AO basis become
%
\begin{equation*}
     \mathbf{S} = \langle \boldsymbol{\chi} | \boldsymbol{\chi} \rangle; \quad
     \mathbf{F} = \langle \boldsymbol{\chi} | \hat{f} | \boldsymbol{\chi} \rangle
\end{equation*}

Electric dipole moment operator
-------------------------------
The electric dipole moment operator takes the form

$$
\hat{\boldsymbol{\mu}} = \sum_{i=1}^N \hat{\boldsymbol{\mu}}(i)
$$

The AO representation of this one-electron operator, or its three Cartesian components to be specific, is accessible as follows
```
dipole_drv = vlx.ElectricDipoleIntegralsDriver()

dipole_mats = dipole_drv.compute(molecule, basis)

mu_x = dipole_mats.x_to_numpy()
mu_y = dipole_mats.y_to_numpy()
mu_z = dipole_mats.z_to_numpy()
```

````{note}
In this exercise, we will need to print out and examine matrices. It is recommended to format the printout of NumPy arrays by the following settings

```
np.set_printoptions(precision=2, suppress=True, linewidth=132)
```
````

Exercises
---------

1. Perform an SCF optimization to obtain $|\Psi_\mathrm{HF}\rangle$. Print out the MO coefficients and orbital energies. Identify the occupied and unoccupied orbitals.

2. Inspect the MO coefficients and determine which irreducible representations the MOs span. To your help, you have the character table.

3. With help of results obtained in the associated problem in the problem set, perform a unitary change of basis to produce symmetry-adapted atomic orbitals (SAOs) according to $| \boldsymbol{\chi}' \rangle = | \boldsymbol{\chi} \rangle  \, \mathbf{U}$. This transformation should accomplish an ordering of the SAOs according to their symmetry and adhering to the order of irreps in the character table.

4. Determine the overlap matrix in the new basis, i.e., $\mathbf{S}' = \langle \boldsymbol{\chi}' | \boldsymbol{\chi}' \rangle$. Comment on the matrix structure.

5. Determine the molecular orbital coefficients in the new basis, i.e., $\mathbf{C}'$. Comment on the matrix structure.

6. Determine the dipole moment of your system $\boldsymbol{\mu} = \langle \Psi | \hat{\boldsymbol{\mu}} | \Psi \rangle$ by determining the MO representation of the operator and using the established formula for expectation values of one-electron operators in the Hartree--Fock approximation. Comment on your result from the perspective of molecular symmetry.

7. Determine the AO representation of the operator (all three Cartesian components) in the new basis. Comment on the matrix structures.

8. Intensities in UV/vis absorption spectra are proportional to the absolute square of the transition moment, i.e., $I \propto \left| \rule{0pt}{10pt}
\langle S_n | \hat{\boldsymbol{\mu}} | \Psi_\mathrm{HF}\rangle
\right|^2$. For ethylene, the dominant electronic transition in the spectrum is that associated with the excitation from the highest-occupied to the lowest-unoccupied molecular orbital forming excited state $|S_1\rangle$ of singlet spin symmetry. Which of the three Cartesian components of the transition dipole moment contribute to the intensity? Explain your result from the perspective of symmetry?

9. Determine the intensity for this transition using the result from the associated problem in the problem set and the MO representation of the electric dipole moment operator.
