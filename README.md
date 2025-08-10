# SmoQy_Saver

A Python app to collect data from [SmoQyDQMC](www.github.com/SmoQySuite/SmoQyDQMC.jl) runs and handle data binning and calculations.

## About

This notebook currently supports the following SmoQyDQMC outputs:

- `global_stats.csv`

- `local_stats.csv`

- `spin_z_position_equal-time_stats.csv`

- `spin_x_position_equal-time_stats.csv`

Averages and error bars are calculated using bin averaging, as follows:

The averages and error bars are calculated using bin averaging as follows:

**Average:**

```math
\langle \mathcal{O} \rangle = \frac{1}{n_{\text{bins}}}\sum_{i=1}^{n_{\text{bins}}}\bar{\mathcal{O}}_i
```

**Error bar:**

```math
\mathrm{err}_\mathcal{O} = \frac{1}{\sqrt{n_{\text{bins}}}} \sqrt{ \frac{1}{n_{\text{bins}}-1} \sum_{i=1}^{n_{\text{bins}}} \left( \bar{\mathcal{O}}_i - \langle \mathcal{O} \rangle \right)^2 }
```

where

```math
\bar{\mathcal{O}}_i = \frac{1}{n_{\text{points per bin}}} \sum_{j=1}^{n_{\text{points per bin}}} \mathcal{O}_j
```

## Usage

Current implementation is in Jupyter Notebooks. Enter your parameters at the top and SmoQy_Saver will look through your listed output directory for SmoQyDQMC folders. It will then output a .CSV file to your current working directory containing all observables and relevant information.

Note that it expects a folder named as follows: `hubbard_{lattice}_U{U:.2f}_mu{mu:.2f}_L{L}_b{beta:.2f}-{sID}`

### Flags

If setting `LessIO = True`, then it will assume all .CSV files are in the root of the data folder (for use with [SmoQyDQMC - LessIO](https://www.github.com/swestastic/SmoQyDQMC.jl). If `LessIO = False`, it will assume they follow standard SmoQyDQMC folder structure.

## Future Work

- Use SQLite3 for condensing save data into a SQL database file.

- Move to a python script/package with commandline arguments

- N_bonds and N_orbitals supported for more lattices

- Dynamic model naming in folder lookup, currently hardcoded for Hubbard model.

- Add support for `time_displaced`, `integrated`, and `spaces` flags.
