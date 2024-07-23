> This example is adapted from `cp2k/benchmarks/QS/H2O-64.inp`.

TLDR: The setup in [`MIXING`](https://manual.cp2k.org/trunk/CP2K_INPUT/FORCE_EVAL/DFT/SCF/MIXING.html) would influence the **efficiency of the SCF convergence**. Please check the setup in similar systems or test it carefully by yourself, especially if you suffer from a slow SCF convergence.

Compared with the previous example, we change the setup of density mixing here:

```text
&MIXING
    METHOD BROYDEN_MIXING
&END MIXING
```

You can find that the iteration number of SCF changes compared with the previous example. However, it becomes larger here, which means a slower SCF convergence :( Well... I cannot tell you which method is the best and which setup is the most efficient. It depends on the specific system. What I will explain in the following is the general idea of density mixing.

As you know, DFT calculation is actually an optimization problem: finding the electron density (matrix) to minimize the total energy. In addition, the density matrix is both the input and the output in the SCF loop. We can therefore take some clues from the existing, general optimization algorithms (e.g., [Broyden method](https://nickcdryan.com/2017/09/16/broydens-method-in-python/)) to accelerate and/or stabilize the SCF convergence. For the method implemented in CP2K:

- `DIRECT_P_MIXING`
  - slow!
  - $\rho^{in}_{i+1}=\alpha\rho^{in}_i+(1-\alpha)\rho^{out}_i, \alpha\in(0,1)$
- `BROYDEN_MIXING`
- `PULAY_MIXING`
- `KERKER_MIXING`
- `MULTISECANT_MIXING`

For more details, you can refer to:

- (Chinese) [Abacus manual](https://mcresearch.github.io/abacus-user-guide/algorithm-mix.html)
- (English) [JCTC paper](https://doi.org/10.1021/acs.jctc.1c00630)
