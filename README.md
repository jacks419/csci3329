# csci3329
# csci3329
# CSCI 3329 — Homework 3 Report 
  
## 1. Dataset
Parkinsons / UCI Machine Learning Repository / number of samples: 195 / number of classes: 2 
Class distribution (table or bar chart):
|class  | meaning  | count |
|-------|----------|-------|
|0      | healthy  | 48    |
|1      |parkinsons| 147   |

  
## 2. Preprocessing - Missing-value handling - Encoding and scaling decisions, with rationale
Pandas was used to check for missing values in the dataset. Rows that were missing are removed with dropna but parkinsons had no missing values. StandardScaler was used for feature scaling because the dataset contained feautures on different numeric ranges. It was used to improve the performance of KNN and neural networks.
  
## 3. Part 2 — Algorithm Comparison 
| Algorithm         | Mean Accuracy | Std | 
|-------------------|---------------|-----| 
|linear classifier  | 0.84          | 0.08| 
|logistic regression| 0.88          | 0.06|
| KNN               | 0.91          | 0.05|
|gaussian NB        | 0.70          | 0.10|
|neural network     | 0.92          | 0.04|
  
## 4. Part 3 — Feature Selection - Search method and justification 
| Algorithm         | Best Feature Subset    | Mean Accuracy | Std | 
|-------------------|------------------------|---------------|-----|
|linear classifier  |MDVP:Fhi(Hz),PPE,spread1| 0.86          | 0.07|
|logistic regression|PPE,spread1,spread2,RPDE| 0.90          | 0.05|
|KNN                |PPE,spread1,DFA         | 0.93          | 0.04|
|gaussian NB        |RPDE,DFA,spread2        | 0.74          | 0.09|
|neural network     |PPE,spread1,spread2,DFA | 0.94          | 0.03|
  
## 5. Discussion - Part 2 vs Part 3 comparison - Per-algorithm observations - Limitations and ideas for improvement 
Part 2 and part 3 show that removing features simplified the models to reduce noise in the dataset and feauture selection improved classification accuracy as well as reducing standard deviation. 
The neural network had a higher performance rate and KNN also performed well after scaling and feature selection due to the normalized data with gaussian NB having the weakest performance within the dataset.
A limitation is the size of the parkinsons dataset being smaller than most and the class imbalance between healthy and parkinson's samples. Ideas for improvement would be to include testing of additional classification algorithms.

# 6. Reproduction - Python version, key library versions - Run command (e.g., `python main.py`) 
Python Version: 3.12.1
Libraries: numpy, pandas, scikit-learn
Run command: python3 main.py
