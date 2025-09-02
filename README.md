# Mechanistic Model of Oxygen Transport in a Microbioreactor

This repository contains a Python implementation of a mechanistic model for spatiotemporal oxygen transport in a membrane-aerated microbioreactor, as described in Hong and Braatz (2021). The simulation solves the governing partial differential equation (PDE) using the method of lines to capture the dynamics of dissolved oxygen (DO) concentration across both a gas-permeable PDMS membrane and a cell growth well.

The project highlights the importance of using a detailed spatial model over simpler lumped-parameter models, especially for capturing fast transient dynamics critical for process control in biopharmaceutical development.

## Scientific Context

Microbioreactors are a key technology for accelerating the development of biologic drugs. A critical challenge is maintaining optimal dissolved oxygen concentration, as levels that are too high or too low can damage or kill cells. This model simulates oxygen transport from an external source, through a membrane, and into the cell culture where it is consumed.

This implementation is based on the following research paper:

Hong, M. S., & Braatz, R. D. (2021). *Mechanistic modeling and parameter-adaptive nonlinear model predictive control of a microbioreactor.* Computers & Chemical Engineering, 147, 107255.  
https://doi.org/10.1016/j.compchemeng.2021.107255

## Key Features

- **Detailed PDE Model**: Implements the 1D reaction-diffusion PDE to model the DO concentration profile C(z, t).  
- **Lumped k_L*a Model**: Includes a simpler, traditional lumped-parameter model for direct comparison.  
- **Spatiotemporal Visualization**: Generates a 3D surface plot of the DO concentration profile over space and time, replicating Figure 3 of the paper.  
- **Transient Dynamics Comparison**: Simulates both models under slow (60s) and fast (10s) changes in the external oxygen supply, showing limitations of the lumped model (Figure 2 of the paper).  

## Installation

Clone the repository:
```bash
git clone https://github.com/iamabhinav13/Microbioreactor-Oxygen-Transport-Model.git
cd Microbioreactor-Oxygen-Transport-Model
```

Install dependencies:
```bash
pip install -r requirements.txt
```
## Usage

Run the simulation script:

```bash
python microbioreactor_model.py
```

Executing the script will run two simulations sequentially and display the resulting plots in separate windows.

## Expected Output

**Primary Simulation Plots:**

- 3D surface plot showing the spatiotemporal DO profile across the membrane and growth well.  
- 2D line plot showing DO concentration over time at three key locations: gas interface, membrane-well interface, and sensor wall.  


**Comparison Simulation Plot:**

- Figure with two subplots comparing transient responses of the PDE model vs. the k_L*a model at the sensor location for both slow and fast input changes.  


## Dependencies

- numpy  
- scipy  
- matplotlib  

All dependencies are listed in `requirements.txt`.

## Acknowledgments

This project is a Python implementation of the model developed by Moo Sun Hong and Richard D. Braatz (2021). All credit for the underlying model, parameters, and scientific validation belongs to the original authors.
