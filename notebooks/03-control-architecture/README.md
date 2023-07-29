# FCND Part 3: Controls (CPP)

## Section 3: Control Architecture

**Note:** The notebooks are in the order of the exercises from the section. The first link is the original exercise, possibly with my solution. The second link is the official solution, if available.


1. [Linearization Exploration](https://github.com/ivogeorg/FCND-Controls-CPP/blob/main/notebooks/03-control-architecture/1-Linearization.ipynb).    
2. [Linear Controller](https://github.com/ivogeorg/FCND-Controls-CPP/blob/main/notebooks/03-control-architecture/2-Linear-Controller.ipynb). ([solution](https://github.com/ivogeorg/FCND-Controls-CPP/blob/main/notebooks/03-control-architecture/2-Linear-Controller-Solution.ipynb))  
   > **Notes on Dynamics Parameter Tuning** 
   > 1. The exercise (and solution) notebook has notes on the advised sequence of implementation. Note that _implementation sequence_ means coding all three controllers, setting some default values for `z_k_p`, `z_k_d`, `y_k_p`, `y_k_d` (to maintain position close to the center of the required figure-8 trajectory) and focusing on tuning `phi_k_p` and `phi_k_d` to match the trajectory. As mentioned in these notes, starting by increasing `phi_k_p` quickly matches the overall shape (up to 12.5 was enough to get the deviation to a very small value). Contrary to the usual rule-of-thumb 1:10 ration of `k_p` and `k_d`, this was the exact opposite. Indeed, the official solution values are 150 and 50 for `phi_k_p` and `phi_k_d`, respectively. For $z$ and $y$, default values of around 1 and around 10, respecively, work fine.  
   > 2. In the flight trajectory simulation and visualization, `pylab` is uded alongside `pyplot`. `pylab` is [**deprecated**](https://matplotlib.org/stable/tutorials/introductory/quick_start.html#the-explicit-and-the-implicit-interfaces) and its use is strongly discouraged because of _namespace polution_ (it imports `matplotlib.pyplot` and `numpy` under the same namespace). Need to modify the examples and the test code to work without `pylab`. Its use is actually very lazy and limited.  
   > 3. The main idea is to create a multidimensional-grid visualization of the resulting figure-8 trajectories corresponding to sets of the 6 parameters `z_k_p`, `z_k_d`, `y_k_p`, `y_k_d`, `phi_k_p`, and `phi_k_d`.  
   > 4. The parameter sets should be at first logarithmic (e.g. {0.1, 1.0, 10.0, 100.0}), within the recommended ranges (e.g. P parameters should be within [0.0, 1.0]), to get the correct order for each parameter from a simple glance, and then focus on fine tuning a smaller sub-range.  
   > 5. The `zy_flight()` function in [simulate.py](simulate.py), `plot_zy_flight_path()` function in [plotting.py](plotting.py), and `figure_8()` in [trajectories.py](trajectores.py) essentially contain everything necessary for creating a single plot in the grid.  
   > 6. The figure-8 curve is actually one of the simplest of a family of curves known as [Lissajous curves](https://en.wikipedia.org/wiki/Lissajous_curve). Write a function to parameterize the generation of the curves and test the drone on all these trajectories. May yield more data for parameter fine tuning. Here are some examples:
   >  
   > <img src="https://github.com/ivogeorg/FCND-Controls-CPP/blob/main/assets/Lissajous_relaciones.png" width="200" />   
   > 
   > 8. Here's a [list of algebraic curves](https://en.wikipedia.org/wiki/List_of_curves) to explore for more cool flight trajectories to use for fine-tuning the flight dynamics parameters. In particular, the [Lemniscate](https://mathworld.wolfram.com/Lemniscate.html) is similar to but different from the figure-8 curve in `figure_8()`.  
   > 9. Alternatively, the `simulate.py` and `figure_8` functions, with some modification, can be used in a fast loop to sort all the parameters sets by ascending trajectory error. _How to calculate trajectory error?_  Exercise tests evaluate and visualize target-vs-actual errors!  
3. ...  
4. ...  
5. ...  

