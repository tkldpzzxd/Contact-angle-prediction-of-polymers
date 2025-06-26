# Contact-angle-prediction-of-polymers
We adopted the classical fully connected network (FFN) architecture commonly used in the Boston housing price prediction task, owing to its reliability and proven effectiveness in regression problems. We trained a neural network regression model using dataset(https://www.accudynetest.com/polytable_03.html?sortby=contact_angle) to predict contact angles, thereby enabling the machine-learning-assisted selection of hydrophilic materials.

We estimated functional group density as the ratio of the number of functional groups to the total number of atoms in a monomer unit. This metric provides an approximate measure of the availability of polar groups per atom in the polymer chain. For example, in polyvinyl alcohol (PVA), the density of hydroxyl groups is approximately 1/7 ≈ 0.143. These descriptors—surface energy of functional groups and the density of various functional groups—were encoded as features in a multivariate input matrix. The contact angle was used as the regression label.

Our neural network model involves several hyperparameters, including the number of iterations, learning rate, number of nodes, activation function, loss function, and optimizer. These parameters are tuned based on the root mean squared error (RMSE) results on the train and validation sets. 

# Setup

## Basic information of equipment and software
The database we use: 
Contact angle of polymer database:
 https://www.accudynetest.com/polytable_03.html?sortby=contact_angle
The software we use: 
Python version: Python 3.11.8 (tags/v3.11.8:db85d51, Feb 6 2024, 22:03:32) [MSC v.1937 64 bit (AMD64)] on win32
CPU: AMD Ryzen 7 500H with Radeon Graphics
GPU: NVIDIA GeForce RTX 3060 Laptop GPU
PyCharm version: PyCharm 2024.1.1 (Community Edition)
