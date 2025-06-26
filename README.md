# Contact-angle-prediction-of-polymers
We adopted the classical fully connected network (FFN) architecture commonly used in the Boston housing price prediction task, owing to its reliability and proven effectiveness in regression problems. We trained a neural network regression model using dataset(https://www.accudynetest.com/polytable_03.html?sortby=contact_angle) to predict contact angles, thereby enabling the machine-learning-assisted selection of hydrophilic materials.

We estimated functional group density as the ratio of the number of functional groups to the total number of atoms in a monomer unit. This metric provides an approximate measure of the availability of polar groups per atom in the polymer chain. For example, in polyvinyl alcohol (PVA), the density of hydroxyl groups is approximately 1/7 ≈ 0.143. These descriptors—surface energy of functional groups and the density of various functional groups—were encoded as features in a multivariate input matrix. The contact angle was used as the regression label.

Our neural network model involves several hyperparameters, including the number of iterations, learning rate, number of nodes, activation function, loss function, and optimizer. These parameters are tuned based on the root mean squared error (RMSE) results on the train and validation sets. 

# Setup

## Basic information of equipment and software
Contact angle of polymer database: https://www.accudynetest.com/polytable_03.html?sortby=contact_angle

Python version: Python 3.11.8 (tags/v3.11.8:db85d51, Feb 6 2024, 22:03:32) [MSC v.1937 64 bit (AMD64)] on win32

CPU: AMD Ryzen 7 500H with Radeon Graphics

GPU: NVIDIA GeForce RTX 3060 Laptop GPU

PyCharm version: PyCharm 2024.1.1 (Community Edition)

## Install as a pip package:
`pip install pandas` `pip install numpy` `pip install sklearn` `pip install torch` `pip install tqdm` `pip install matplotlib`

# Parameter optimization of the model
By adjusting several hyperparameters of the neural network model, including the number of iterations, learning rate, number of nodes, activation function, loss function and optimizer, we obtained the optimized model. The process and results of the optimization are presented in the "Supporting Information" and "Optimization results of parameters" folders. Additionally, readers can view the training results of the model by adjusting "Contact angle prediction.py".

# Usage & Examples

An example of predicting the contact angle:

<pre>```python
pred_contact_angle = model(torch.tensor( [41.1, 0.227272727, 0, 0.045454545, 0.227272727, 0, 0.090909091, 0, 0.090909091, 0, 0, 0, 0, 0, 0, 0, 0, 0.045454545], dtype=torch.float)) 
pred_contact_angle = pred_contact_angle.reshape(len(pred_contact_angle)) 
pred_contact_angle = pred_contact_angle.detach().numpy()
print("CS", pred_contact_angle) ```</pre>

When making the prediction of contact angle, the feature of the predicted polymer needs to be input. The input order of the feature should be consistent with the format order in the "Contact_angle_database.csv" file, which is "Surface Energy (dynes/cm)", "C-H bond", "CH3", "CH2", "CH", "C-C double bond (Mole Fraction)", "Hydroxy", "ketone group", "ether bond", "sulfide", "benzene ring", "Sulfone", "ester group", "nitrile grouping", "F", "Cl", "Si", "amido bond".

The input feature can be either an integer or a floating-point number. For example, the feature for predicting chitosan would be "[41.1, 0.227272727, 0, 0.045454545, 0.227272727, 0, 0.090909091, 0, 0.090909091, 0, 0, 0, 0, 0, 0, 0, 0, 0.045454545]". Input "feature" into the above code and place it at the end of the code in the "Contact angle prediction.py" file. Then run it to obtain the prediction of the contact angle.
