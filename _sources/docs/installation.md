Software installation
=====================

Conda is an open-source package and environment management system that runs on Windows, MacOS, and Linux. The conda repository contains a large number of open-source certified packages enabling scientific work. It is recommended that you install the minimal installer for conda named miniconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others.

Retrieve miniconda from the following website

> <https://docs.conda.io/en/latest/miniconda.html>

Install the version for 64 bit computers that comes with Python 3.9.

Start a conda terminal, or Anaconda Powershell as it is referred to on a Windows system. Conda supports multiple *environments* and you start in the one named `base` as is typically indicated by the prompt. To create a new and additional environment named `vlxenv` and install VeloxChem, Matplotlib, and Jupyter notebook (and package dependencies such as NumPy and SciPy) into it, you enter the following command line statement

```bash
conda create -n cb2070 veloxchem jupyterlab matplotlib py3Dmol -c veloxchem -c conda-forge
```

You can list your conda environments

```bash
conda env list
```

The activated environment will be marked with an asterisk (the `base` environment to begin with) and you can activate your new environment with the command

```bash
conda activate vlxenv
```

as should be indicated by getting a modified prompt.

Inside this newly created environment, you should now be ready to start a Jupyter notebook with the command

```bash
jupyter-notebook
```

which should open in your default web browser. A notebook allows for interactive execution of Python code written into cells.
