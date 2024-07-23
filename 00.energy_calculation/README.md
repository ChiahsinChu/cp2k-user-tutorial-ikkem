> This example is adapted from `cp2k/benchmarks/QS/H2O-64.inp`.

# First trial: energy calculation as simple as possible

Please follow the [official tutorial](https://www.cp2k.org/howto:static_calculation) to understand the sections/keywords used in `input.inp`, including:

- `GLOBAL`: global setup (e.g., name, run type, etc.)
- `FORCE_EVAL/SUBSYS`: system information (e.g., cell, atoms, etc.)

  Instead of using `COORD` section (as in the website), atomic coordinates can also be written in an additional file (e.g., `coord.xyz`) and be included via

  ```text
  &TOPOLOGY
      COORD_FILE_FORMAT XYZ
      COORD_FILE_NAME coord.xyz
  &END TOPOLOGY
  ```

- `FORCE_EVAL/DFT`: DFT setup
  - `SCF`: convergence, maximum number of SCF cycles, etc.
  - `XC`: exchange-correlation functional
  - `BASIS_SET_FILE_NAME` and `POTENTIAL_FILE_NAME`: Gaussian basis set and pseudopotential
  - (optional) `MGRID`: multigrid settings -> how the basis set would be used for periodic systems
