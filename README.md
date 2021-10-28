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
Clone to the same directory (e.g., ../code/gasoline-ics and ../code/mdl)

### Gasoline
