# DataCon2025
## Project Overview
  This project focuses on developing a therapeutic approach for Alzheimer's Disease (AD) by targeting the Adenosine Receptor A2A (ADORA2A), a GTPase protein whose native ligand is adenosine. Our strategy aims to mitigate neuroinflammation rather than directly targeting tau or amyloid-beta proteins.
## Scientific Background
### Alzheimer's Disease Challenge
#### Alzheimer's Disease is a complex polygenic disorder characterized by:
 
 #####   1)Accumulation of amyloid-beta plaques
 
 #####   2)Neurofibrillary tangles of tau protein
 
 #####   3)Chronic neuroinflammation leading to neuronal death

### ADORA2A as a Therapeutic Target

#### Native ligand: Adenosine (a purine nucleoside)

#### Function: Plays crucial roles in:

 ##### 1)Modulation of neurotransmitter release

 ##### 2)Regulation of cerebral blood flow

 ##### 3)Neuroinflammatory processe

## Data Preparation 
#####   For the human adenosine A2A receptor, we extracted 10,924 known ligand entries for the human adenosine A2A receptor from BindingDB. After performing data sanity checks, we generated Morgan fingerprints as molecular representations. Both IC50 and Ki values (treated as pharmacologically equivalent) were converted to pValues (-log10(Value), measured in nM) to standardize activity measurements across different experimental conditions.

## Feature Processing & ML 
##### After data preprocessing and feature engineering, we implemented and evaluated several machine learning algorithms for predicting ligand activity, including ensemble methods (XGBoost, CatBoost, Random Forest, and LGBMRegressor) along with k-Nearest Neighbors (KNN) as a baseline approach. These models were selected to provide diverse learning paradigms: gradient-boosted trees (XGBoost, CatBoost, LGBM) for their high predictive performance with structured data, Random Forest for robust feature importance analysis, and KNN to capture local similarity patterns in the chemical space. Each algorithm was rigorously optimized through hyperparameter tuning using cross-validation to ensure optimal performance while maintaining generalizability to novel compounds. The comparative analysis of these approaches allowed us to identify the most effective modeling strategy for our A2A receptor activity prediction task.

## Virtual Screening and Molecular Generation
#### Following model development, we employed DRUG GPT for de novo ligand generation, leveraging its demonstrated capability in structure-based molecular optimization and high validity rate of output SMILES representations. The system generated 55 novel ligand candidates, which subsequently underwent comprehensive in silico profiling:

##### Drug-likeness evaluation (QED score)

##### Synthetic accessibility (SA Score)

##### Toxicity risk assessment (Toxicophore detection)

##### Rule-of-Five compliance (Lipinski's filters)

##### BBB permeability prediction (Topological Polar Surface Area)

#### Through this multi-parameter screening pipeline, we identified 8 lead compounds exhibiting:
##### ✓ Optimal QED scores (0.6–0.8)
##### ✓ Favorable SA Scores 
##### ✓ No critical toxicophores
##### ✓ Full Lipinski compliance
##### ✓ Predicted BBB penetration

