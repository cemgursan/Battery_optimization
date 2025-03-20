# Power System Optimization with PyPSA

This project demonstrates how to build and optimize an electric power system model using PyPSA (Python for Power System Analysis) along with a sensitivity analysis on battery storage capacity. The script downloads time-series data from the Open Power System Data (OPSD) repository, constructs a network model, runs a linear optimal power flow (LOPF) optimization, and evaluates the impact of varying battery capacities on the total system cost.

## Overview

The project workflow is as follows:

- **Data Acquisition:**
  - Downloads OPSD time series data using a provided CSV URL.
  - Loads and processes the data using `pandas`, converting 15-minute load data to hourly resolution.
  
- **Network Creation and Optimization:**
  - Constructs a PyPSA network by adding essential components such as a bus, load, grid connection, renewable generator, and a battery storage unit.
  - Sets up snapshots for the network using the hourly load data.
  - Runs LOPF (Linear Optimal Power Flow) to minimize total system cost and prints key results such as grid dispatch and battery storage dispatch.
  
- **Sensitivity Analysis:**
  - Varies the battery storage capacity across different values (e.g., 10, 20, 50, 100 MW).
  - Re-runs the LOPF for each scenario and collects the objective value (total system cost).
  - Plots the sensitivity of the system cost to changes in battery capacity.

## Requirements

Ensure you have Python 3 installed. The project depends on the following Python packages:

- `requests`
- `pandas`
- `matplotlib`
- `pypsa`

You can install these dependencies using the provided [requirements.txt](requirements.txt) file:

```bash
pip install -r requirements.txt
