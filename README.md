# nersc-mpi4py
mpi4py on NERSC

[Parallel Python](https://docs.nersc.gov/development/languages/python/parallel-python/)

use the nersc-mpi4py conda environment that we provide, built against PrgEnv-gnu, which you can clone if you want to add more packages:

```
module load python
conda create --name my_mpi4py_env --clone nersc-mpi4py
```

Then check:

```
elvis@login01:~> salloc -N 1 -t 30 -C cpu -q interactive
...
elvis@nid00195:~> module load python
elvis@nid00195:~> srun python -c "from mpi4py import MPI;print(MPI.Get_library_version())"
MPI VERSION    : CRAY MPICH version 8.1.25.17 (ANL base 3.4a2)
MPI BUILD INFO : Sun Feb 26 15:15 2023 (git hash aecd99f)
```
