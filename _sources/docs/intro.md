Introduction
============

Theoretical chemistry has made tremendous progress in the past few decades and is today an indispensable tool in all fields of molecular science, exemplified by biochemistry and nanotechnology, where it can be employed to reveal the microscopic origins of functionality and interactions as well as to tune performance and guide synthesis. The interplay between simulation and experiment is a key enabling factor for advancements in life and material sciences and spectroscopy represents one of the most important meeting points in between the two disciplines {cite}`Lindon2010`. It is imperative to base spectroscopic modeling on first principles as the underlying microscopic events are quantum-mechanical in origin {cite}`Norman2018`---although typically in combination with classical force-field molecular dynamics for the sampling of configuration space---and in order to study complex molecular systems and delocalized electronic transitions, it is therefore important that such first-principles approaches are developed into forms where they may be tractably applied to large systems. It is therefore not surprising that a vast amount of work in computational chemistry has been carried out to extend the computationally tractable system domain boundaries with respect to time and length scales {cite}`Akimov2015`.

```{figure} ../images/vision-statement.*
---
name: vision-fig
---
Vision and goal statement for the VeloxChem project.
```

Alongside the development of methods and algorithms, we are witnessing an ever ongoing advancement of high-performance computing (HPC) cluster resources to reach higher number of floating point operations per second. As an example, the EuroHPC project is leading Europe toward exascale computing and comprises an entire supercomputing ecosystem with the ambition to strengthen European industry and academia alike. It brings us an exciting future at the same time as it challenges us. A view of the most recent TOP500 list gives a clear indication that heterogeneous hardware solutions are to be expected when such extreme performance numbers are to be reached and there is a community consensus among quantum chemists that an efficient utilization of general-purpose graphical processing units (GP-GPUs) is difficult to achieve in our software where the compute-intensive kernels involve 10$^4$--10$^5$ lines of code.

The stated goals of the VeloxChem and Gator programs encompass (see also {numref}`vision-fig`):

> To deliver a science- and education-enabling software platform for quantum molecular modeling on contemporary and future HPC systems, and to be part of the EuroHPC ecosystem.

Behind the term *science-enabling* there are a multitude of software requirements that we find important in our work, including (i) coverage of system sizes up to and beyond 50 and 500 atoms in the quantum region at the levels of wave-function and density-functional theory, respectively, (ii) accurate description of electronically excited states that shows a more diffuse character than the ground state, (iii) stable and reliable convergence of iterative equation solvers also with use of diffuse basis sets, (iv) time-efficient prototyping of novel scientific approaches, (v) transparent exposure of data structures to enable in-depth analyses also for standard users, (vi) flexible ways to interact with other components of the simulation, e.g., molecular dynamics, parameterizing the embedding, and data visualization, and, not least, (vii) a fast return of results as to remain in synchronicity with experimental project partners. The term *education-enabling* adds to this already long list another set of software requirements. In this context, the notion of *deeper learning* refers to taking the student's understanding of the subject matter to a another (deeper) level. Our experience tells us that the process of implementing methods to solve fundamental equations is supremely efficient to reach deeper learning, but only few students are granted this opportunity as such core modules of scientific software are written a long time ago and often made obscure by code optimization. We aim to offer access to the needed building blocks to explore quantum chemistry in very much the same manner that we can use the Python NumPy package to explore linear algebra.

All of the above mentioned considerations have gone into the design of the VeloxChem program, which also serves as the engine for the Gator program by the provision of integrals and Hartree--Fock (HF) reference states for the implemented post-HF methods. Our ambition is to (i) scale standard spectroscopy calculations beyond 10,000 central processing unit (CPU) cores as to be relevant for the EuroHPC project and, at the same time, (ii) provide a platform for students to explore (in Python, on a laptop) quantum chemistry. The selected exercises in this workshop give a guided tour to some of the program features, illustrated on a few small- and medium-sized systems as to fit within the restricted time available.

References
----------
```{bibliography}
```
