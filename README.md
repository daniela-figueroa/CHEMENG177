# Electrolyte Conductivity Prediction Using Machine Learning

## Project Overview
The purpose of this repository is to develop and evaluate machine learning models for predicting electrolyte conductivity in lithium-ion battery electrolytes. The dataset used for training and evaluation is the CALiSol-23 dataset, which contains experimental electrolyte conductivity data for various lithium salts and solvent combinations. The models implemented include Lasso regression, Ridge regression, and a feedforward neural network to analyze the relationship between temperature, salt concentration, and solvent composition in electrolyte solutions.

## Data
The CALiSol-23 dataset comprises 13,825 individual data points extracted from 27 different experimental studies. The dataset includes data for 38 solvents and 14 lithium salts over a broad temperature range. To ensure reliable analysis, only salts with more than 1,000 data points were considered for detailed modeling, including LiPF6, LiBF4, LiAsF6, and LiBOB.

The dataset contains the following key features:

* Temperature (Kelvin)

* Conductivity (mS/cm) (used as the target variable)

* Salt concentration

* Solvent component ratios (38 solvent components)

For standardization, concentration and solvent ratios were converted into a consistent unit of moles before model training.
### Preprocessing
Before training the models, the dataset underwent several pre-processing steps in the Data_Preprocessing(1).ipynb notebook:

Standardization of Units:

Salt concentrations originally reported in molality and molarity were converted into moles per kilogram of solvent.

Solvent ratios expressed in weight, volume, or molar ratios were transformed into mole fractions.

Equation-Based Conversion:

Five equations were used to convert the salt concentrations and solvent component ratios.

For salt concentrations, molality and molarity were converted using equations (1) and (2), considering solvent volume based on density averaging.

Solvent component weight, molar, and volume ratios were converted using equations (3), (4), and (5), respectively.
## Lasso Regression
## Ridge Regression
## FeedForward Neural Network
