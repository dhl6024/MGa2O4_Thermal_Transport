# Dataset for Thermal Transport Properties of MGa2O4 (M = Mg, Zn, Cd, Hg)

This repository contains the core dataset and calculation files for the investigation of thermal transport properties in MGa2O4 (M = Mg, Zn, Cd, Hg) compounds.

The data is provided to support the reproducibility of the first-principles calculations and phonon Boltzmann Transport Equation (BTE) simulations.

## File Structure

The dataset is organized by material system into `.zip` archives. For `MgGa2O4.zip`, `CdGa2O4.zip`, and `HgGa2O4.zip`, each archive contains the following structure:

- **`youhua/`** (Directory): Contains the input and output files for primitive-cell structural optimization.
- **`FORCE_CONSTANTS_2ND`** (File): The extracted second-order harmonic interatomic force constants.
- **`FORCE_CONSTANTS_3RD`** (File): The extracted third-order anharmonic interatomic force constants.
- **`ShengBTE/`** (Directory): Contains the ShengBTE configuration and output files calculated using a 17 × 17 × 17 q-point mesh.

### Special Note on ZnGa2O4

Due to file-size organization, the ShengBTE calculation results for ZnGa2O4 are divided into two separate archives:

- **`ZnGa2O4.zip`**: Contains the structural optimization files, second- and third-order IFCs, and ShengBTE results at **300 K**.
- **`ZnGa2O4-other.zip`**: Contains ShengBTE calculation results for the remaining temperatures, including 100–200 K and 400–1200 K.

The archived datasets include calculations over a temperature range extending to 1200 K. The revised manuscript reports temperature-dependent lattice thermal conductivity results over **100–800 K**.

## Computational Input Files

The `Computational_Inputs/` directory provides input files used for the first-principles and related calculations of MgGa2O4, ZnGa2O4, CdGa2O4, and HgGa2O4.

Each material has a separate subdirectory:

- `MgGa2O4/`
- `ZnGa2O4/`
- `CdGa2O4/`
- `HgGa2O4/`

Each material directory contains the following subdirectories:

- **`Elastic/`**: Input files for elastic-property calculations.
- **`DFPT_Born/`**: Input files for density functional perturbation theory (DFPT) calculations of the dielectric tensor and Born effective charges.
- **`2nd_3rd_IFC_Common_Settings/`**: Common VASP `INCAR` and `KPOINTS` files used for displaced-supercell calculations of second-order and third-order interatomic force constants (IFCs).
- **`AIMD800/`**: Input files for ab initio molecular dynamics (AIMD) simulations at 800 K.

## MgGa2O4 Convergence Tests

The `MgGa2O4_Convergence_Tests/` directory contains additional ShengBTE calculations used to examine the convergence of the lattice thermal conductivity of MgGa2O4 with respect to the third-order IFC cutoff and the q-point mesh.

- **`Cutoff.tar.xz`**: ShengBTE calculations using a fixed 13 × 13 × 13 q-point mesh while varying the third-order IFC cutoff. The archive contains the directories `13-3` through `13-10`, corresponding to different neighbor cutoffs.
- **`Q_Mesh.tar.xz`**: ShengBTE calculations using a fixed 8th-neighbor cutoff while varying the q-point mesh. The archive contains the directories `15-8` through `20-8`, corresponding to q-point meshes from 15 × 15 × 15 to 20 × 20 × 20.

## Methodology

All first-principles calculations were performed using the Vienna Ab initio Simulation Package (VASP). The lattice thermal conductivity was evaluated by iteratively solving the phonon Boltzmann transport equation (BTE) using the ShengBTE code.
