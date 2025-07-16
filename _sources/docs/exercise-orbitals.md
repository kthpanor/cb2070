(lab-1)=
# 1. Orbitals and one-particle densities

{download}`Template lab 1 <../template_lab_1.ipynb>`

## Basis sets

The SCF solution of the Hartree--Fock equation is found in a finite basis of predefined and tabulated atomic orbitals (AOs) in which the molecular orbitals (MOs) are expanded as a linear combination of atomic orbitals (LCAO):

$$
    \phi_a(\mathbf{r}) = 
    \sum_A^\mathrm{atoms}
    \sum_\alpha C^A_{\alpha a} 
    \chi^A_{\alpha}(\mathbf{r} - \mathbf{R}_A)
$$

The AOs are centered at the atomic positions. Typically one adopts identical sets of basis functions for all atoms of a given element and the sets adopted for the different elements should have a balanced accuracy. A statement such as "*we employed the 6-31G basis set in the calculation*" means that such a balanced set of sets of AOs was adopted for all elements.

**Table**: Categories of basis set.
| Category | Character | Example |
| -------- | --------- | ------- |
| Minimal | Single basis function per occupied atomic orbital, size for second-row elements is $[2s1p]$ | STO-3G |
| Double-$\zeta$ | Two basis functions per occupied valence atomic orbital, size for second-row elements is $[3s2p]$ | 6-31G | 
| Triple-$\zeta$ | Three basis functions per occupied valence atomic orbital, for second-row elements $[4s3p]$ | 6-311G |
| Polarization | Basis functions with higher angular momenta; important for chemical bonding; size for second-row elements is $[3s2p1d]$ | cc-pVDZ |
| Diffuse | Basis functions with small exponents; important for excited states; sizes for second-row elements are $[4s3p]$ for 6-31+G and $[4s3p2d]$ for aug-cc-pVDZ |  6-31+G, aug-cc-pVDZ |

## One-particle densities

The values of orbitals and one-particle densities at points in space are readily obtained with use of the `VisualizationDriver` object. Examples are found [here](https://kthpanor.github.io/echem/docs/elec_struct/reduced_density.html).

## Exercises

1. For neon, determine the Hartree--Fock energy, $E_\mathrm{HF}$, with use of the basis sets listed in the table above. Assess and rank the quality of the basis sets based on your results.

2. Continue with basis set cc-pVDZ:  Plot the values of the valence orbitals along a radial line. Does your result depend on the line direction? 

3. Discuss nodal points and orthogonality in between all occupied orbitals.

4. Plot the radial orbital densities for the valence sub-shells $2s$ and $2p$. Does your result depend on the line direction? 

5. Plot the total radial density, $n(r)$. Identify the atomic *K*- and *L*-shells in your plot. Mark the van der Waals radius of 154 pm in your plot and comment on how reasonable this value is as an estimate of the atomic size.

6. With use of SciPy routine `integrate.simpson`, integrate $n(r)$. Compare your result to the number of electrons in the system.

7. Based on Koopmans' theorem, determine the ionization potential. How does your result compare with the experimental value of 21.56 eV. What are the main sources of error in your calculation?
