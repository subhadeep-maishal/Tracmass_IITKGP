:warning: Warning
-----------------
This TRACMASS version is a **beta** version.
It is currently under development. The following features from older versions are not available yet in this version:

* Time analytical scheme
* Subgrid turbulence parameterisations

Previous versions of TRACMASS are stored in the following repository:

https://github.com/TRACMASS/Tracmass_previous.git


TRACMASS v7
===========
[![Documentation Status](https://readthedocs.org/projects/tracmass/badge/?version=latest)](https://tracmass.readthedocs.io/en/latest/?badge=latest)

TRACMASS is a Lagrangian trajectory code for ocean and atmospheric general circulation models. The code makes it possible to estimate water paths, Lagrangian stream functions (barotropic, overturning, etc.), exchange times, etc. TRACMASS has been used in studies of the global ocean circulation, of sea circulation in the Baltic Sea, the Mediterranean Sea and in coastal regions.

The code is written in FORTRAN 90 with modules and runs on UNIX platforms such as MAC OS X and Linux.

TRACMASS has been set up to run with velocities integrated with models such as NEMO or IFS-ECMWF, of satellite datasets such as AVISO.

Documentation
=============

You can find documentation about TRACMASS in

https://tracmass.readthedocs.io/en/latest/

Quickstart
==========

1. Download the code

```bash
git clone https://github.com/TRACMASS/Tracmass.git
```

2. Enter the TRACMASS directory

```bash
cd Tracmass
```

3. Modify the *Makefile* to fit your system. You will need to set ARCH, which is the name of your system, i.e. tetralith. You will also need to configure how TRACMASS should find the netCDF libraries, if at all. For most systems, we recommend the option **automatic-44**.

4. Then you can run the make command

```bash
make
```

Running a first test case
-------------------------

We recommend testing that TRACMASS was properly compiled by letting PROJECT and CASE be **"Theoretical"** in the *Makefile* (which is the default). In this case, TRACMASS will use a simple oscillating velocity field to trace trajectories.

1. Make sure in *Makefile* both PROJECT and CASE are set to Theoretical.

2. Recompile the code

```bash
make clean
make
```

3. Run the code by typing

```bash
./runtracmass
```

Download test data
------------------

You can find some input data for testing the code on

```bash
https://www.dropbox.com/sh/b6leim7tb99i3hm/AAA7M0mxuYTwJLKjqmLnoJuca?dl=0
```

This test data includes data from NEMO, IFS and AVISO.
Before doing any analysis we recommend to download some of the test data and make sure TRACMASS is working properly.

In order to set up TRACMASS to run trajectories on e.g. NEMO data, you will need to change PROJECT and CASE to NEMO, and then re-compile the code.

```bash
make clean
make
./runtracmass
```

Run your analysis
-----------------

If you wish to run another case or a very specific case of the above models, you may create your own project in the projects directory.
To run with e.g. your own IFS data, you will need to modify the projects/IFS/namelist_IFS.in namelist to suit your needs.
