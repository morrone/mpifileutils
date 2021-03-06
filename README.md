# mpiFileUtils
mpiFileUtils is a suite of MPI-based tools to manage large datasets, which may vary from large directory trees to large files. High-performance computing users often generate large datasets with parallel applications that run with many processes (millions in some cases). However those users are then stuck with single-process tools like cp and rm to manage their datasets. This suite provides MPI-based tools to handle typical jobs like copy, remove, and compare for such datasets, providing speedups of up to 20-30x.
Documentation is available on [ReadTheDocs](http://mpifileutils.readthedocs.io) and in this repo:

 - [dbcast](doc/rst/dbcast.1.rst) - Broadcast files to compute nodes.
 - [dchmod](doc/rst/dchmod.1.rst) - Change permissions and group access on files.
 - [dcmp](doc/rst/dcmp.1.rst) - Compare files.
 - [dcp](doc/rst/dcp.1.rst) - Copy files.
 - [dfilemaker](doc/rst/dfilemaker.1.rst) - Generate random files.
 - [drm](doc/rst/drm.1.rst) - Remove files.
 - [dstripe](doc/rst/dstripe.1.rst) - Restripe files.
 - [dwalk](doc/rst/dwalk.1.rst) - List files.

## Experimental Utilities
To enable experimental utilities, run configure with the enable experimental option.

  ./configure --enable-experimental

 - [dfind](doc/rst/dfind.1.rst) - Find files by path name (experimental).
 - [dgrep](doc/rst/dgrep.1.rst) - Search contents of files (experimental).
 - [dparallel](doc/rst/dparallel.1.rst) - Perform commands in parallel (experimental).
 - [dtar](doc/rst/dtar.1.rst) - Create file tape archives (experimental).

## Build
mpiFileUtils depends on several libraries.  To simplify builds, there are two scripts: buildme\_dependencies and buildme.  The buildme\_dependencies script downloads and installs all the necessary libraries.  The buildme script then builds mpiFileUtils assuming the libraries have been installed.  Both scripts require that mpicc is in your path, and that it is for an MPI library that supports at least v2.2 of the MPI standard.  Please review each buildme script, and edit if necessary.  Then run them in sequence:

  ./buildme\_dependencies

  ./buildme

Alternatively, mpiFileUtils is available in [Spack](https://spack.io/), which simplifies the install to just:

  spack install mpifileutils

or to enable all features:

  spack install mpifileutils +lustre +experimental

## Build Status
The current status of the mpiFileUtils master branch is [![Build Status](https://travis-ci.org/hpc/mpifileutils.png?branch=master)](https://travis-ci.org/hpc/mpifileutils).
