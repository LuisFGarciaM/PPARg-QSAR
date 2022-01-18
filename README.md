This repository is focused on the creation of a machine learning model in order to predict the dose at which a given molecule will activate partially a therapeutic target. This is with drug discovery purposes. 

The aforementioned approach is a Quantitative structure-activity relationship (QSAR) model for a therapeutical target named Peroxisome Proliferator-Activated Receptor gamma (PPARG), which is involved in several diseases such as fibrosis, diabetes and obesity. This method reveals relationships between structural properties of candidate molecules and biological activities. 

The model is divided into five Jupyter notebooks. 

1) PPARg_Bioactivity_Data.ipynb 
Here is where data preprocessing from the CHEMBL database is performed and the main dataframe is obtained for furhter analysis. Here I've used Pandas to manipulate and clean the data. Molecules are selected based on the EC50, which is the concentration that is effective in order to produce the 50% of the maximal response in the target (PPARg in this case). This is a way of comparing drug potencies. 

2) PPARg_Exploratory_Data_Analysis.ipynb
This is where I perform an Exploratory Data Analysis using Pandas, Numpy, RDKit, Seaborn and Matplotlib based on the Lipinski descriptors. These are rules that state to what extent a drug is likely to become available when taken orally. Furthermore, a Mann-Whitney U statistical test is performed. Molecules are also classified in Partial Activators and Full Activators. 

3) PPARg_Descriptor_Calculator_and_Dataset_Preparation 
Here the candidate molecules are broken down into a matrix of standard descriptors. This means that every aspect of the molecule structure gets a binary value across a matrix (If X descriptor is present in the molecule, then 1, if abscent, then 0). This matrix is saved into a new dataset. 

4) PPARg_Regression_Model_Random_Forest.ipynb
Here a Random Forest regressor is applied using SciKit Learn in order to obtain a model that takes Y=predicted EC50 and X = Experimental EC50. 

5) PPARg_Comparong_Regressors.ipynb
Several regression and classifier models are compared using LazyPredict, yielding that a Decission Tree Regressor has the highest R2 value and therefore better to use in order to predict an EC50 for new molecules. 



