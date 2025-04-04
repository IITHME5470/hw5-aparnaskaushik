# MPI-Based 2D Heat Conduction Solver

## Overview
This program implements an MPI-parallelized solver for the two-dimensional unsteady heat conduction equation. The discretization uses a second-order central differencing scheme for spatial derivatives and the explicit Euler method for time integration.

## Requirements
- MPI Library (e.g., OpenMPI, MPICH)
- C/C++ compiler with MPI support (e.g., `mpicc`)

## Compilation
To compile the code, use the following command:
```sh
mpicc -o heat_solver parhc2d_skel.c -lm
or
gcc -o heatsolver hc2d.c -lm
```

## Running the Code
The program can be run in serial or parallel mode using different process configurations.

### Serial Execution
```sh
./heatsolver
```

### Parallel Execution (2x2, 2x4, 4x4 grids)
```sh
mpirun -np 4 ./heat_solver   # 2x2 configuration
mpirun -np 8 ./heat_solver   # 2x4 configuration
mpirun -np 16 ./heat_solver  # 4x4 configuration
```

## Output Files
- `T_x_y_{timestamp}.dat` → Temperature field at 5 time steps.
