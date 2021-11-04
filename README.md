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
- collide : Generate initial conditions for collisions
- [ tipsytools ](https://bitbucket.org/creinh/tipsytools/src/master/): Tools I wrote over the years to work with tipsy binary files


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
- ```Tipsy``` requires ```libaw7``` with header files and ```termcap```:
```
sudo apt-get install libxaw7-dev
```
and
```
sudo apt-get install libncurses5-dev
`````


### Gasoline
Go to the gasoline-ics directory (e.g., cd ./code/gasoline-ics) and type
```
make null
```
to compile the code to run on a single CPU or
```
make pthread
```
to obtain a version that runs on several threads using pthread.

### Note
Make sure that GSL () is installed:
```
sudo apt-get install libgsl-dev
```


### tipsy
Go to the tipsy (e.g., cd ./code/tipsy) and then to then to the code directory and type
```
./configure
```
to generate a Makefile. Then type
```
make
```
to compile the code. Detailed instructions are available on the official GitHib page.

#### Notes
Make sure that ```libaw7``` is installed with header files:
```
sudo apt-get install libxaw7-dev
```

For Ubuntu the termcap library is part of ```libncurses5```
```
sudo apt-get install libncurses5-dev
`````



