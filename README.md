# Electrolyte Conductivity Prediction Using Machine Learning

## Project Overview
The purpose of this repository is to develop and evaluate machine learning models for predicting electrolyte conductivity in lithium-ion battery electrolytes. The dataset used for training and evaluation is the CALiSol-23 dataset, which contains experimental electrolyte conductivity data for various lithium salts and solvent combinations. The models implemented include Lasso regression, Ridge regression, and a feedforward neural network to analyze the relationship between temperature, salt concentration, and solvent composition in electrolyte solutions.

## Package Requirements
Install the following packages to seamlessly run the notebooks:
* plotly
* tensorflow
  
## Data
The CALiSol-23 dataset comprises 13,825 individual data points extracted from 27 different experimental studies. The dataset includes data for 38 solvents and 14 lithium salts over a broad temperature range. To ensure reliable analysis, only salts with more than 1,000 data points were considered for detailed modeling- those being LiPF6, LiBF4, LiAsF6, and LiBOB.

The dataset contains the following key features:

* Temperature (Kelvin)
* Conductivity (mS/cm) (used as the target variable)
* Salt concentration
* Solvent component ratios (38 solvent components)

Download the CALiSol-23 dataset used from the "CALiSol-23 Dataset.csv" file. For standardization, concentration and solvent ratios were converted into a consistent unit of moles before model training.
### Preprocessing
Before training the models, run the pre-processing steps in the Data_Preprocessing(1).ipynb notebook:

* Extract the numeric columns of the dataset
* Convert salt concentrations originally reported in molality and molarity  into moles of salt
* Convert solvent ratios expressed in weight, volume, or molar ratios into moles
* Export the newly transformed data to a csv

## Lasso Regression

Lasso regression was implemented in the lasso.ipynb notebook using the Lasso and LassoCV functions from Scikit-learn. Lasso regression applies L1 regularization, which helps with feature selection by shrinking less relevant features to zero. Open and run the lasso.ipynb notebook to perform lasso regression:

* Import the data from the "Pre-processed data.csv" file
* Select the relevant data from the salts with the most data-  LiPF6, LiBF4, LiAsF6, and LiBOB
* Run the lassoregress function for all salts
* Report results

## Ridge Regression

Ridge regression was implemented using the Ridge and RidgeCV functions from Scikit-learn. Unlike Lasso, Ridge regression applies L2 regularization, which penalizes large coefficients without forcing them to zero. Open and run the ridge.ipynb notebook:

* Import the data from the "Pre-processed data.csv" file
* Select the relevant data from the salts with the most data-  LiPF6, LiBF4, LiAsF6, and LiBOB
* Run the ridgeregress function for all salts
* Report results

## Feedforward Neural Network

A fully connected feedforward neural network was designed for regression tasks, predicting electrolyte conductivity based on salt composition, temperature, and solvent mole fractions.

Model Architecture:

* Input Layer: Accepts all numerical features
* Hidden Layers: Three layers with 64, 128, and 64 neurons, respectively, using the ReLU activation function
* Dropout Layer: Applied after the second hidden layer with a 20% drop-rate to prevent overfitting
* Output Layer: A single neuron with a linear activation function for continuous conductivity prediction

Open and run the FeedForward_Neural_Network.ipynb notebook:

* Create the ConductivityNN class
* Import the data from the "Pre-processed data.csv" file
* Select the relevant data from the salts with the most data- LiPF6, LiBF4, LiAsF6, and LiBOB
* Split data into training and testing sets
* Perform grid search with 5-fold cross validation for each salt with the training set to pick the best hyperparameters for each model
* Finish training the models on the full training sets and evaluate with the testing set
* Save models in .h5 files to a saved models folder
