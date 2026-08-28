# Dataset for Thermal Transport Properties of MGa2O4 (M = Mg, Zn, Cd, Hg)

This repository contains the core dataset and calculation files for the investigation of thermal transport properties in $M\text{Ga}_2\text{O}_4$ ($M =$ Mg, Zn, Cd, Hg) compounds. 

The data is provided to support the reproducibility of the first-principles calculations and phonon Boltzmann Transport Equation (BTE) simulations.

## File Structure

The dataset is organized by material system into `.zip` archives. For `MgGa2O4.zip`, `CdGa2O4.zip`, and `HgGa2O4.zip`, each archive contains the following four main directories:

- **`youhua/`**: Contains the input and output files for the primitive cell structural optimization (using VASP).
- **`FORCE_CONSTANTS_2ND/`**: Contains the dataset for extracting the 2nd-order harmonic interatomic force constants (IFCs).
- **`FORCE_CONSTANTS_3RD/`**: Contains the dataset for extracting the 3rd-order anharmonic interatomic force constants.
- **`ShengBTE/`**: Contains the ShengBTE configuration and main output files (e.g., `CONTROL`, `kappa`, `BTE.w`) calculated using a $17 \times 17 \times 17$ q-point mesh across a temperature range from 100 K to 1200 K.

### Special Note on ZnGa2O4
Due to file size organization, the ShengBTE calculation results for $\text{ZnGa}_2\text{O}_4$ are divided into two separate archives:
- **`ZnGa2O4.zip`**: Contains the structural optimization, 2nd/3rd IFCs, and ShengBTE results specifically at **300 K**.
- **`ZnGa2O4-other.zip`**: Contains the ShengBTE calculation results for the remaining temperature range (100 K–200 K, 400 K–1200 K).

## Methodology
All first-principles calculations were performed using the Vienna Ab initio Simulation Package (VASP). The lattice thermal conductivity was evaluated by iteratively solving the phonon BTE using the ShengBTE code.
