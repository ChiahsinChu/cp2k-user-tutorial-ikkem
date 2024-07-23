# CP2K as your first DFT code

This tutorial is prepared for the people:

1. know some basic concepts of quantum mechanics and DFT (e.g., SCF calculation)
2. have little experience in computational chemistry (i.e., don't know how to perform a DFT calculation)
3. want to use CP2K as your first DFT code

If you are not familiar with the QC/DFT basic concepts, you can refer to the following resources:

- (Chinese) [Introduction to QC and DFT](https://wiki.cheng-group.net/wiki/new_comers/qc_dft/) & [Introduction of basis set and pseudopotentials](https://wiki.cheng-group.net/wiki/new_comers/basis_pps/)
- (English) [Introduction to Density Functional Theory [Part One]](https://www.youtube.com/watch?v=Ez_Fm4iTUeo)

If you don't have experience in command-line operations, you can refer to the following resources:
- The first five sections in [*The Missing Semester of Your CS Education*](https://missing.csail.mit.edu)

If you have experience in other DFT codes (e.g., VASP) and just want to get your hand in CP2K usage, I would recommend you to follow below tutorials rather than this one:

- (Chinese) [chenggroup wiki](https://wiki.cheng-group.net/wiki/software_usage/cp2k/cp2k/)
- (Chinese) [Jingang Lan's blog](https://www.zhihu.com/column/cp2k-tutorial)
- (English) CP2K official [tutorials](https://www.cp2k.org/howto) and [exercises](https://www.cp2k.org/exercises:common:index)

## Before start...

1. Install CP2K and set up relevant environment variables. For IKKEM users, you can just run the `cp2k.slurm` later in every task.
2. Set up environment variable `CP2K_DATA_DIR` to the path holding basis set/pseudopotentials/etc. You can either download them from the [offical repository](https://github.com/cp2k/cp2k/tree/master/data) or use the data in IKKEM:

   ```bash
   export CP2K_DATA_DIR=/public/software/cp2k-2022.1-intel/cp2k-2022.1/data
   ```

## How this tutorial works...

Performing a DFT calculation is non-trivial. The users should take care of not only some variables at the theoretical level (e.g., the choice of SCF convergence) but many parameters for specific algorithms (e.g., smearing). Trying to know every detail in the first place is unnecessary and distractive. In this tutorial, I will follow some existing tutorials and show you how far you should go, as a beginner.

## Contents

> Please check the `README.md` in each folder for more details.

1. [Simplest setup for energy calculation](./00.energy_calculation/)
2. [How density mixing works](./01.density_mixing/)
