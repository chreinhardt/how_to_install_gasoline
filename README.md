# How to install Gasoline for simulating collisions

This repository provides all instructions on which software is used for collision simulations and how to install it.

## Required software
- [ Gasoline ]( https://bitbucket.org/creinh/gasoline-ics/src/master/): Smoothed Particle Hydrodynamics code (Wadsley et al. 2004) with modifications for simulating giant impacts (Reinhardt & Stadel 2007, Chau et al. 2018, Reinhardt et al. 2020, Meier et al. 2021)
- [ mdl ]( https://github.com/N-BodyShop/mdl ): Machine Dependent Library for parallel codes
- [ EOSlib ](https://github.com/Halbarath/EOSlib): General interface for equation of state (EOS) calls
- [ tillotson ](https://github.com/chreinhardt/tillotson): Interface for the Tillotson EOS
- [ ANEOSmaterial ](https://github.com/Halbarath/ANEOSmaterial): Interface for the ANalytic Equation Of State (ANEOS, M-ANEOS)
- [ tipsy ](https://github.com/N-BodyShop/tipsy):  The Theoretical Image Processing SYstem for visualizing/analyzing n-body simulations
- [ ballic ](https://github.com/chreinhardt/ballic-array): Generate low noise particle representation of planets
- [ collide ]( https://github.com/chreinhardt/collide ): Generate initial conditions for collisions
- [ tipsytools ](https://bitbucket.org/creinh/tipsytools/src/master/): Tools I wrote over the years to work with tipsy binary files
- [ tipsy_wrapper ]( https://github.com/chreinhardt/tipsy_wrapper ): A C++ wrapper for the Tipsy API
- [ skid ]( https://github.com/N-BodyShop/skid ): A group finder for n-body simulations

## Installation
Clone all repositories to the same directory (e.g., ./code/gasoline-ics and ./code/mdl) with
```
./clone-all.sh
```
but keep in mind that some of them are _private_ and require access for this script to work.

### Prerequisits
- First make sure that all required compilers are installed (e.g., ```gcc```).
- Some modules of the ```EOSlib``` require [ GSL ]( https://www.gnu.org/software/gsl/ ). If you use Ubuntu you can install it with:
```
sudo apt-get install libgsl-dev
```
- ```tipsy``` requires ```libaw7``` and ```termcap``` with header files, e.g.:
```
sudo apt-get install libxaw7-dev
```
and
```
sudo apt-get install libncurses5-dev
`````

If the version of your glibc library is >= 2.32 (e.g., if you use Ubuntu 22.04) you have to install the rpc library:
```
sudo apt-get install libtirpc-dev
```
Since all the software expects the rpc library to be installed at ```/usr/include/rpc``` you have to make a symbolic link with
```
cd /usr/include
sudo ln -s tirpc/rpc/* rpc
sudo ln -s tirpc/netconfig.h .
```
for the software to compile. Note that the library has to be explicitly included with ```-ltirpc``` in the Makefile.

### Gasoline
Go to the gasoline-ics directory (e.g., ```cd ./code/gasoline-ics```) and type
```
make null
```
to compile the code to run on a single CPU or
```
make pthread
```
to obtain a version that runs on several threads using pthread.

*Note:* Make sure that ```mdl``` and ```GSL``` are installed before compiling the code.

### tipsy
Go to the tipsy (e.g., ```cd ./code/tipsy```) and then to then to the code directory and type
```
./configure
```
to generate a Makefile. Then type
```
make
```
to compile the code. Detailed instructions are available on the official GitHib page.

*Note:* Make sure that ```libaw7``` and ```termcap``` are installed with header files and rerun ```configure``` after installing them.

### ballic
Go to the ballic directory  (e.g., ```cd ./code/ballic-array```) and compile required part of the code with
```
make solve_model_single
```
to solve a single component 1D model or
```
make ballic.solve_model_single
```
obtain a particle representation of a single component 1D model.




