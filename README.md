# Wee Archie

This repository contains a number of activities designed to run on Wee Archie, a Raspberry-Pi parallel computer, designed to be taken to outreach events to demonstrate how parallel computers work and thus illustrate the underlying principles of supercomputers.

## Environment

Requires Python, wxpython, python3-vtkplotter, python3-vtk9, conda, python3-flask . Also requires OpenMPI

## Running

There are two components, the backend simulation code and the frontend. 

To compile the simulation code, go into `windtunnel/simulation` and execute `make` . You will need OpenMPI (or mpich) installed. This will generate the `windtunnel` executable. 

There is a server that listens to launch the simulation code, this is in `framework/server` and `python3 run.py` . However, the paths to the simulation executable need to be set in the `simulations.db` . If you load this with sqlite 3 and `select * from Simulations;` will show how it is set up, you will need to edit this with the appropriate SQL to set the path to the `windtunnel` executable.

To have the server side ready to go, you need to execute `python3 run.py` and have this running in a terminal. Then, under `windtunnel` directory, execute `python3 Start.py` and this will bring up the UI. If everything is set correctly it should run a simulation and pull back results that are then visualised.

<!-- Licensing and copyright stuff below -->
<br>
<a href="http://www.epcc.ed.ac.uk">

!["EPCC logo"](imgs/EPCC_logo2.png)
</a>

<a rel="license" href="https://opensource.org/licenses/BSD-3-Clause">
<img alt="BSD-3 Clause License" style="border-width:0" 
     src="https://img.shields.io/badge/License-BSD%203--Clause-blue.svg" />
</a><br />
This work is licensed under a <a rel="license" href="https://opensource.org/licenses/BSD-3-Clause">
BSD 3-Clause License</a>.<br/>
&copy; Copyright EPCC, The University of Edinburgh 2016-2022.
