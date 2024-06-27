
# Transfer Learning in Turbulent Systems

In this project, we train neural networks to perform Large Eddy Simulations (LES) in the case of Rayleigh Benard Convection. 

We also explore how transfer learning can be used to extrapolate networks to more turbulent systems of higher Rayleigh number.

# Notebooks

The simulation and training are performed using jupyter notebooks in the notebooks folder.

The RB_simulation.ipynb notebook performs simulation of Rayleigh Benard convection for the specified parameters. Filtering and coarse graining are also performed.

The train_BNN.ipynb notebook trains a network to predict the sub-grid scale stress terms.

The train_TLNN.ipynb notebook takes the Base neural network and performs transfer learning on the target system.

# Process

First, the simulation data can be generated using RB_simulation.ipynb for the base (Ra=10^4) and target (Ra=10^6) system by setting the parameters. 

For each case there are 4 files which can be downloaded: input_normalized.h5, input_normalized_val.h5, output_normalized.h5, output_normalized_val.h5, which will be used as training and validation data.

Then, the Base network can be trained using the data for the base system (Ra=10^4) using train_BNN.ipynb, the neural networks weights can be saved as a zip file. 

Then transfer learning can be performed using the trained network and the target system data in train_TLNN.ipynb.
