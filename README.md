# Reinforcement Learning for Optimal Power Flow in PyPSA

This repository contains code detailed in the thesis at https://drive.google.com/drive/folders/1b117TVKHYPXa93C_bvukALWbPtTvXOH0?usp=sharing

## Overview

The project implements RL agents that learn optimal power dispatch strategies for electricity networks. The main implementation uses Jupyter notebooks with PyTorch-based PPO algorithms applied to network models generated from pypsa-earth.

## Repository Structure

### Core Implementation

**main_summation.ipynb** and **main_replacement.ipynb**
- Contains the key classes and implementation for the RL environment and PPO agent
- Start here to understand the main algorithm and environment setup
- One notebook for each of the different reward methods for which preliminary experiments have been run

### Supporting Files

- Network analysis utilities and results visualization
- RL training result processing and evaluation scripts
- Configuration and helper functions

## Requirements

### Data Files

The code requires `.nc` (NetCDF) files representing electricity networks. These can be obtained in two ways:

#### Option 1: Download Precomputed Networks
Pre-generated network files are available at https://drive.google.com/drive/folders/1b117TVKHYPXa93C_bvukALWbPtTvXOH0?usp=sharing.

#### Option 2: Generate Networks Using pypsa-earth

Generate your own network files using [pypsa-earth](https://github.com/pypsa-meets-earth/pypsa-earth):

1. Install pypsa-earth following their documentation
2. Run pypsa-earth with either:
   i. `config.RSA_nonextendable.yaml` as included in this repo
   ii. your own config file, with custom country/ region and technical specifications. See the pypsa-earth documentation for detailed configuration options.
3. The generated `.nc` file can be directly used as input to the RL training scripts

## Usage

1. **Prepare network data**: Either download precomputed `.nc` files or generate them using pypsa-earth as described above
2. **Open the notebook**: Start with one of the `EnvDispatch_PPO.ipynb` notebooks depending on your GPU setup
3. **Load the network**: Point the notebook to your `.nc` network file
4. **Train the agent**: Execute the training cells to learn optimal dispatch policies

## Dependencies

- PyTorch
- Gym / Gymnasium
- NumPy / Pandas
- xarray (for NetCDF file handling)
- pypsa-earth (for network generation)

## Contact
For questions or issues, please open an issue on the repository.
