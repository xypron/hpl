# hpl - High Performance Computing Linpack Benchmark (HPL)

## Overview

HPL is a software package that solves a (random) dense linear
system  in   double  precision  (64   bits)   arithmetic   on 
distributed-memory  computers.   It can thus be regarded as a
portable as well as  freely  available implementation  of the
High Performance Computing Linpack Benchmark.

The  HPL  software  package requires the availibility on your
system of an implementation of the  Message Passing Interface
MPI  (1.1 compliant).  An  implementation of either the Basic
Linear Algebra Subprograms  BLAS  or the  Vector Signal Image
Processing Library VSIPL is also needed.  Machine-specific as
well as generic implementations of MPI, the  BLAS  and  VSIPL
are available for a large variety of systems.

## Debian packaging

A project to package hpl as a Debian package is maintained at
https://github.com/xypron/hpl/.

    wget http://www.netlib.org/benchmark/hpl/hpl-2.2.tar.gz
    mv hpl-2.2.tar.gz hpl_2.2.orig.tar.gz
    git clone https://github.com/xypron/hpl.git
    tar -xzf hpl_2.2.orig.tar.gz
    cp hpl-2.2/* hpl -rf
    cd hpl
    sudo apt-get install libatlas-base-dev libopenmpi-dev \
     openmpi-bin libmpich-dev build-essential debhelper \
     fakeroot
    dpkg-buildpackage
    cd ..
    sudo dpkg -i hpl_2.2-4_amd64.deb
    cd /usr/share/doc/hpl
    mpirun -np 4 xhpl
