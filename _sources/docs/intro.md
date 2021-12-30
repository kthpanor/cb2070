# Motivation

Theoretical chemistry has made tremendous progress in the past few decades and is today an indispensable tool in all fields of molecular science, exemplified by biochemistry and nanotechnology, where it can be employed to reveal the microscopic origins of functionality and interactions as well as to tune performance and guide synthesis. The interplay between simulation and experiment is a key enabling factor for advancements in life and material sciences alike and the motions of electrons and nuclei in molecular systems are governed by the laws of quantum mechanics {cite}`Norman2018`.

Alongside the development of methods and algorithms for quantum molecular modeling, we are witnessing an ever ongoing advancement of high-performance computing (HPC) cluster resources to reach higher number of floating point operations per second. As an example, the [EuroHPC](https://eurohpc-ju.europa.eu/) project is leading Europe toward exascale computing and comprises an entire supercomputing ecosystem with the ambition to strengthen European industry and academia alike. It brings us an exciting future at the same time as it challenges us.

Stated goals of the [VeloxChem](https://veloxchem.org) program:

> To deliver a science- and education-enabling software platform for quantum molecular modeling on contemporary and future HPC systems, and to be part of the EuroHPC ecosystem.

Behind the term *science-enabling* there are a multitude of software requirements that we find important in our work, including (i) coverage of system sizes up to and beyond 500 atoms in the quantum region at the level of density-functional theory, (ii) accurate description of electronically excited states that shows a more diffuse character than the ground state, (iii) stable and reliable convergence of iterative equation solvers also with use of diffuse basis sets, (iv) time-efficient prototyping of novel scientific approaches, (v) transparent exposure of data structures to enable in-depth analyses also for standard users, (vi) flexible ways to interact with other components of the simulation, e.g., molecular dynamics, parameterizing the embedding, and data visualization, and, not least, (vii) a fast return of results as to remain in synchronicity with experimental project partners. 

The term *education-enabling* adds to this already long list another set of software requirements. In this context, the notion of *deeper learning* refers to taking the student's understanding of the subject matter to a another (deeper) level. Our experience tells us that the process of implementing methods to solve fundamental equations is supremely efficient to reach deeper learning, but only few students are granted this opportunity as such core modules of scientific software are written a long time ago and often made obscure by code optimization. We aim to offer access to the needed building blocks to explore quantum chemistry in very much the same manner that we can use the Python NumPy package to explore linear algebra.

All of the above mentioned considerations have gone into the design of the VeloxChem program. Aided by the computer exercises, this course gives insights into the foundations of many-electron wave functions and provides a basis for advanced studies and research in molecular physics.

```{figure} ../images/vision-statement.*
---
name: vision-fig
---
Vision and goal statement for the VeloxChem project.
```
