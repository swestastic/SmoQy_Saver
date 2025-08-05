# SmoQy_Saver

A Python app to collect data from [SmoQyDQMC](www.github.com/SmoQySuite/SmoQyDQMC.jl) runs and handle data binning and calculations.

## Usage

Current implementation is in Jupyter Notebooks. Enter your parameters at the top and SmoQy_Saver will look through your listed output directory for SmoQyDQMC run files.

## Future Work

- Use SQLite3 for condensing save data into a SQL database file.

- Add more indexes for $U$, $\beta$, etc.

- More measurement outputs

- Move to a python script/package with commandline arguments
