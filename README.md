# Machine Learning-Guided Discovery of Small Molecule Inhibitors Targeting PD-L1 for Cancer Immunotherapy

This repository holds the computational pipeline created to accelerate drug discovery, specifically for PDL1 as the target molecule.This approach aims to overcome the 
limitations of monoclonal antibodies by developing candidates with advantages like improved tumor penetration and the possibility of oral administration.

## Jupyter Notebooks Overview
### Data Exploration
This notebook involves the initial data cleaning and visualization steps. Molecular structures were standardized, cannonical SMILES
were generated along with deduplication which was followed by different visualization techniques to further explore the data

### Regressors
Machine Learning models were constructed, tasked with predicting the pIC50 of the compounds. Multiple Fingerprinting techniques were used. 
Regression analysis performed was hyperoptimized with Optuna software to maximize the R^2 score.

### Classifiers
The models were tasked with Classification of simple binary prediction of a compound's activity. It utilizes the same set of featurization techniques and model algorithms as in Regressors.

### Extra Classifiers
This notebook is crucial for establishing model robustness through extensive cross-dataset validation. It details training models 
on one dataset (ChEMBL or patent data) and evaluating them on the other. Most importantly, it covers the development of the final 
combined model (trained on both ChEMBL and patent data), which demonstrated superior performance and generalizability across varied chemical space.

### Virtual screening and interpretation
Demonstration of the practical application of the developed models. The Random Forest model with RDK fingerprints was chosen for virtual screening of 
the external Enamine dataset due to the ease of extracting and justifying feature importances. Importantly, investigation of the models feature importantance 
was performed to  understand the model’s decision-making process. This analysis confirmed that the model correctly assigns high importance to known structural features relevant for 
bioactivity, such as the biaryl core (biphenyl) and the linker motif, adding credibility to its predictions.

## DISCLAIMER (DATA USAGE)
The "data" folder only hosts the data downloaded from ChEMBL. The referenced paper and dataset used throughout is from https://www.mdpi.com/article/10.3390/ph15050613/s1. 
