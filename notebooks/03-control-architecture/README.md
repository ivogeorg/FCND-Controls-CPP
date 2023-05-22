# FCND Part 3: Controls (CPP)

## Section 3: Control Architecture

**Note:** The notebooks are in the order of the exercises from the section. The first link is the original exercise, possibly with my solution. The second link is the official solution.


1. [Linearization](https://github.com/ivogeorg/FCND-Controls-CPP/blob/main/notebooks/03-control-architecture/1-Linearization.ipynb).    
2. [Linear Controller](). ([solution]())  
   > **Notes on Dynamics Parameter Tuning** 
   > 1. In the flight trajectory simulation and visualization, `pylab` is uded alongside `pyplot`. `pylab` is [**deprecated**](https://matplotlib.org/stable/tutorials/introductory/quick_start.html#the-explicit-and-the-implicit-interfaces) and its use is strongly discouraged because of _namespace polution_ (it imports `matplotlib.pyplot` and `numpy` under the same namespace). Need to modify the examples and the test code to work without `pylab`. Its use is actually very lazy and limited.
   > 2. The main idea is to create a multidimensional-grid visualization of the resulting figure-8 trajectories corresponding to sets of the 6 parameters `z_k_p`, `z_k_d`, `y_k_p`, `y_k_d`, `phi_k_p`, and `phi_k_d`.
   > 3. The parameter sets should be at first logarithmic (e.g. {0.1, 1.0, 10.0, 100.0}), within the recommended ranges (e.g. P parameters should be within [0.0, 1.0]), to get the correct order for each parameter from a simple glance, and then focus on fine tuning a smaller sub-range.
   > 4. The `zy_flight()` function in [simulate.py](simulate.py), `plot_zy_flight_path()` function in [plotting.py](plotting.py), and `figure_8()` in [trajectories.py](trajectores.py) essentially contain everything necessary for creating a single plot in the grid.
   > The figure-8 curve is actually one of the simplest of a family of curves known as [Lissajous curves](https://en.wikipedia.org/wiki/Lissajous_curve). Write a function to parameterize the generation of the curves and test the drone on all these trajectories. May yield more data for parameter fine tuning. Here are examples:  
   > <img src="/assets/Lissajous_relaciones.png" width="200" />   
   > 
   > 5. Alternatively, the `simulate.py` and `figure_8` functions, with some modification, can be used in a fast loop to sort all the parameters sets by ascending trajectory error. _How to calculate trajectory error?_  
3. ...  
4. ...  
5. ...  

