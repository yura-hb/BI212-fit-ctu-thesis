### Structure of the repository

1. `src` implementation directory
    1. `impl` folder stores compressed implementations done during thesis
        1. `convolution` archive stores version of the [TNL](https://mmg-gitlab.fjfi.cvut.cz/gitlab) git repository checked out at branch with the convolution benchmarks
        2. `grid` archive stores version of the [TNL](https://mmg-gitlab.fjfi.cvut.cz/gitlab) git repository checked out at branch with grid improvements and heat benchmarks
    3. `vis` folder stores visualisation of the results
        1. `Evaluation.ipynb` the python notebook with the visualisations
        2. `data` data of the measurements.
        3. `requirements.txt` represents the environment description for the visualisation notebook  
    5. `thesis` folder stores the source code of thesis in LaTeX
2. `text` text of the work

### Visualization
To start visualization notebook you need to install libraries used in the notebook.
The suggested way is to use [miniconda](https://docs.conda.io/en/latest/miniconda.html) and create the environment in the following way from the `vis` directory.

```
conda create --name <env_name> --file requirements.txt
```

Then the environment should be activated with the following command:

```
source activate <env_name>
```

Finally, to start visualization notebook launch the following command

```
jupyter lab Evaluation.ipynb
```

### Compilation

The improvements in TNL library are compiled with the TNL build system.
Before compilation you may want to ensure, that you have at least `NVCC 11.6` and `GCC 11.2.0`, because for older versions it may not compile.
To compile the benchmarks unzip the required archive and execute the following commands in the root folder of repository.

```
./build --with-cuda=yes|no --with-mpi=yes|no benchmarks
```

The same can be done for tests.

```
./build --with-cuda=yes|no --with-mpi=yes|no tests
```
