# Introduction
This code provides the continuation/GMRES method (C/GMRES method) based solver for nonlinear model predictive control (NMPC). 

- The original C/GMRES method 
- The multiple shooting based C/GMRES method with
- The multiple shooting based C/GMRES method with condensing of variables with respect to the constraints of the saturation function on the control input


# Requirement
- C++11
- Cmake
- Eigen 3
- Python3, numpy, seaborn (for plotsim.py and 2linkanimation.py)
- ffmpeg (to save animations generated by 2linkanimation.py)


# Usage
First, set the parameters of your model of NMPC in nmpc_model.hpp, write equations in nmpc_model.cpp, and set simulation conditions in main.cpp. Next, build files as follows:

```
$ mkdir build
$ cd build
$ cmake ..
$ make
```


After performing a numerical simulation, you can see graphs by

```
$ python3 plotsim.py example
```

save graphs by

```
$ python3 plotsim.py example save example
```

see an animation of 2link robot by

```
$ python3 2linkanimation.py example
```

and save its animation by

```
$ python3 2linkanimation.py example save example
```

# Demo
### The multiple shooting based C/GMRES method for a pendubot
![pendubot_multiple_shooting_gif](https://raw.githubusercontent.com/wiki/mayataka/CGMRES/images/fps=20.gif)
![pendubot_multiple_shooting_png](https://raw.github.com/wiki/mayataka/CGMRES/images/pendubot_multiple_shooting.png)


# References
1. T. Ohtsuka A continuation/GMRES method for fast computation of nonlinear receding horizon control, Automatica, Vol. 40, No. 4, pp. 563-574 (2004)
2. C. T. Kelly, Iterative methods for linear and nonlinear equations, Frontiers in Apllied Mathematics, SIAM (1995)
3. Y. Shimizu, T. Ohtsuka, M. Diehl, A real‐time algorithm for nonlinear receding horizon control using multiple shooting and continuation/Krylov method, International Journal of Robust and Nonlinear Control, Vol. 19, No. 8, pp. 919-936 (2008)