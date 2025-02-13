(lab-3)=
# 3. Dissociation of covalent bonds

In this exercise, we will study the hydrogen molecule with use of the restricted (HF) and unrestricted (UHF) Hartree--Fock methods. The properties of H$_2$ are known with high precision and some experimental data are listed in the table below. Data referring to the potential energy curve (PEC) are derived under the assumption of a Morse potential, so that the rovibrational eigenvalue equation for a diatomic molecule can be solved directly and results in energy levels that are specified by

$$
E_{\nu,J} = \omega_e \left(\nu + \frac{1}{2}\right) + 
\omega_e \chi_e \left(\nu + \frac{1}{2}\right)^2 +
B_\nu J(J+1) + \cdots 
$$

**Table**: Experimental parameters for the H$_2$ molecule.
| Quantity | Value |
| -------- | ----- |
| Bond energy | 4.478 eV |
| Total energy | 31.675 eV |
| Ionization energy, IP | 15.426 eV |
| Internuclear distance, $R_e$ | 0.741 Å |
| Vibrational energy, $\omega_e$ | 0.516 eV |
| Anharmonicity constant, $\omega_e \chi_e$ | 121.33 cm$^{-1}$ |
| Rotational energy | 0.01509 eV |


## Unrestricted Hartree--Fock wave function
The key lines of Python to perform the SCF optimization of a UHF wave function are
```
molecule.set_charge(0)
molecule.set_multiplicity(3)

scf_drv = vlx.ScfUnrestrictedDriver()
scf_drv.compute(molecule, basis)
```

## Exercises

1. Calculate the HF ground state for H$_2$ adopting the experimental bond distance and using of the minimal STO-3G basis set. As a result you will have produced two molecular orbitals denoted $\sigma_g$ (*gerade*) and $\sigma_u$ (*ungerade*), respectively. Plot the values of these orbitals along the internuclear axis. Explain what you see in terms of the underlying LCAO.

2. Plot the one-particle density, $n(\mathbf{r})$, along the internuclear axis for the electronic ground state, $|\sigma_g \sigma_{\overline{g}} \rangle$, as well as for the double electron excited state, $|\sigma_u \sigma_{\overline{u}} \rangle$. What is the key feature difference in these densities that explains covalent bonding.

3. Shift to use of the 6-311G basis set. Determine the restricted HF energy of H$_2$ for 20 equidistant internuclear distances between 0.7 to 10.0 Bohr. Plot these data points. Interpolate your data points with cubic splines using the SciPy routine `interpolate.CubicSpline` to add a smooth curve connecting your data points. The unit of energy should be eV and the energy minimum should define the zero level. You have thereby created a PEC illustration.

4. Locate the energy minimum and add more data points in this region as to get a more accurate estimate of the energy minimum and thereby the equilibrium bond distance. Determine $R_e$ and compare with the experimental value. Explain the difference and why it is prototypical for the HF method.

5. From your result at long internuclear separation distances, estimate the bond energy. Compare with experimental data. If your result is far off from experiment, explain why.

6. Change to using the UHF method and determine the corresponding PEC. Add this curve to your plot. Again estimate the bond energy and comment on the comparison with experiment. If the comparison has improved, explain why.
