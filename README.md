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
$$
\langle \mathcal{O} \rangle = \frac{1}{n_{\text{bins}}}\sum_{i=1}^{n_{\text{bins}}}\bar{\mathcal{O}}_i
$$

**Error bar:**
$$
\mathrm{err}_\mathcal{O} = \frac{1}{\sqrt{n_{\text{bins}}}} \sqrt{ \frac{1}{n_{\text{bins}}-1} \sum_{i=1}^{n_{\text{bins}}} \left( \bar{\mathcal{O}}_i - \langle \mathcal{O} \rangle \right)^2 }
$$

where
$$
\bar{\mathcal{O}}_i = \frac{1}{n_{\text{points per bin}}} \sum_{j=1}^{n_{\text{points per bin}}} \mathcal{O}_j
$$

## Usage

Current implementation is in Jupyter Notebooks. Enter your parameters at the top and SmoQy_Saver will look through your listed output directory for SmoQyDQMC folders.

## Future Work

- Use SQLite3 for condensing save data into a SQL database file.

- Add more indexes for $U$, $\beta$, etc.

- More measurement outputs

- Move to a python script/package with commandline arguments
