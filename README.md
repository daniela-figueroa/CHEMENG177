# Electrolyte Conductivity Prediction Using Machine Learning

## Project Overview
The purpose of this repository is to develop and evaluate machine learning models for predicting electrolyte conductivity in lithium-ion battery electrolytes. The dataset used for training and evaluation is the CALiSol-23 dataset, which contains experimental electrolyte conductivity data for various lithium salts and solvent combinations. The models implemented include Lasso regression, Ridge regression, and a feedforward neural network to analyze the relationship between temperature, salt concentration, and solvent composition in electrolyte solutions.

## Package Requirements
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

* Convert salt concentrations originally reported in molality and molarity  into moles of salt.

* Convert solvent ratios expressed in weight, volume, or molar ratios into moles.

* Export the newly transformed data to a csv.

## Lasso Regression

Lasso regression was implemented in the lasso.ipynb notebook using the Lasso and LassoCV functions from Scikit-learn. Lasso regression applies L1 regularization, which helps with feature selection by shrinking less relevant features to zero. Open and run the lasso.ipynb notebook to perform lasso regression:

* Import the data from the "Pre-processed data.csv" file.
* Select the relevant data from the salts with the most data-  LiPF6, LiBF4, LiAsF6, and LiBOB.
* Run the lassoregress function for all salts
* Report results

## Ridge Regression


## FeedForward Neural Network
