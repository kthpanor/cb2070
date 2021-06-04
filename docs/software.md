Quantum chemistry software
==========================

VeloxChem {cite}`veloxchem` is a quantum chemistry program for the calculation of spectroscopic properties of molecular systems. It implements real and complex linear and nonlinear response theory at the level of Kohn--Sham density functional theory (DFT). The code is open source and may be downloaded from https://veloxchem.org. Documentation and reference manual are available at https://docs.veloxchem.org.

VeloxChem is designed with a C++ layer of highly optimized code for modern hardware infrastructures and a high-level Python layer that allows for ease of development and experimentation. The C++ layer uses hybrid parallel techniques using OpenMP within a multi-core node and MPI across nodes.

```{figure} ../images/code-structure.*
---
name: code-structure-fig
---
VeloxChem code structure with management of computer resources, user input/output streams, and high-level quantum chemistry written Python and compute-intensive modules written in C++. The two layers communicate with the Pybind11 library.
```

VeloxChem can be run either via input and output files as is the usual case in an HPC environment with job scheduling, as well as interactively in a Python shell or via the Jupyter notebook. It has been designed to provide both a platform for high-performance scientific computing, as well as a platform for interactive quantum chemistry. In the computer exercises, we will benefit from the latter.

