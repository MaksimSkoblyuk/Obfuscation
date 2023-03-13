# Obfuscation
## Introduction:
The project is aimed to develop a tool for binary classification obfuscated PowerShell commands.
## Technologies:
- Python 3.9.16
- Revoke-Obfuscation tool (https://github.com/danielbohannon/Revoke-Obfuscation)
- clr_loader 0.2.5
- pythonnet 3.0.1
- jupyter 1.0.0
- notebook 6.5.2
- matplotlib 3.6.2
- numpy 1.23.5
- pandas 1.5.2
- openpyxl 3.0.10
- scikit-learn 1.1.3
## Description for directories:
- Tokenizer: 
1) Tokenization of source PowerShell dataset with tagged data and also of additional datasets for testing models via Revoke-Obfuscation tool
2) Analyzing tokenized dataset
- Balancing:
1) Dropping useless features from tokenized dataset
2) Checking distributions of features in updated dataset
3) Checking imbalance ratio (IR)
4) Using under/oversampling methods to balance samples ratio, plotting via PCA and T-SNE dimension reduction
5) Analyzing quantities of samples with different combinations of obfuscation techniques
6) Balancing samples by increasing clear commands quantity and excluding PowerShell commands containing CMD wrapper
- Selection:
1) Using PCA to find the most important features for covering 95% and 99% of the variance
2) Using filter, wrapper and embedded methods for selection the most significant features
3) Comparing important features by amount of methods selected them
- LearningModels:
1) Dividing balanced dataset into train/validate/test (60/20/20)
2) Learning ML models using 5-fold CrossValidation and hyperparameters tuning using GridSearchCV
3) Analyzing models quality using accuracy, recall and precision metrics
4) Running additional test data on the best models of each algorithm
5) Analyzing and comparing models performance over all obfuscated PowerShell comand processing pipeline
