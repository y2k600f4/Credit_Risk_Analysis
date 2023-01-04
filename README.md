# Credit_Risk_Analysis

## Overview of the loan prediction risk analysis:

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. By employing different techniques to train and evaluate models with unbalanced classes, a model can then be recommended for evaluating credit risk by comparison the outcomes of each technique.

### Purpose

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company the following (6) algorithms/models will be employed. The outcomes will be used to evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

For each method the Accuracy score, Confusion matrix and Imbalanced classification report was generated.

* oversampling (2 methods) 
    * Naïve random oversampling (RandomOverSampler)
    * SMOTE (synthetic minority oversampling technique) Oversampling
* undersampling  (ClusterCentroids)
* Combination (over and under sampling)
    * Using SMOTEENN which combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. SMOTEENN is a two-step process:
        * Oversample the minority class with SMOTE.
        * Clean the resulting data with an undersampling strategy. If the two   nearest neighbors of a data point belong to two different classes, that data point is dropped.

The above methods can be seen in the jupyter notebook 
credit_risk_resampling.ipynb (located in this directory)

* Two additional machine learning models that reduce bias was used.
	* BalancedRadnomForestClassifier
	* EasyEnsembleClassifier

These additional methods can be seen in the jupyter notebook 
credit_risk_ensemble.ipynb (located in this directory)

## Results

Balanced accuracy score and the precision and recall scores of all six machine learning models:

1. Naive Random Oversampling
    * Balanced accuracy score ~.625
    * Precision:
        * for high risk loans: 0.01
        * for low risk loans: 1.00
    * Recall
        * for high risk loans: 0.60
        * for low risk loans: 0.65

2. SMOTE OVersampling 
    * Balanced accuracy score ~.651
    * Precision:
        * for high risk loans: 0.01
        * for low risk loans: 1.00
   * Recall
        * for high risk loans: 0.64
        * for low risk loans: 0.66

3. Undersampling
    * Balanced accuracy score ~0.516
    * Precision:
        * for high risk loans: 0.01
        * for low risk loans: 1.00
    * Recall
        * for high risk loans: 0.60
        * for low risk loans: 0.43

4. Combination (Over and Under Sampling)
    * Balanced accuracy score ~.650
    * Precision:
        * for high risk loans: 0.01
         *for low risk loans: 1.00
    * Recall
        * for high risk loans: 0.72
        * for low risk loans: 0.58 

5. Balanced Random Forest Classifier
    * Balanced accuracy score ~.788 
    * Precision:
        * for high risk loans: 0.04
        * for low risk loans: 1.00
    * Recall
        * for high risk loans: 0.67 
        * for low risk loans: 0.91 

6. Easy Ensemble AdaBoost Classifier
    * Balanced accuracy score ~.925 
    * Precision:
        * for high risk loans: 0.07 
        * for low risk loans: 1.00
    * Recall
        * for high risk loans: 0.91 
        * for low risk loans: 0.94 

## Summary

Based on the above analysis of (6) different algorithms/models, I would recommend using the last method: Easy Ensemble AdaBoost Classifier algorithm. This model has the the highest accuracy score (.93 or 93%), it has the highest sensitivity of detecting true high risk loans  (0.91) and it has the highest sensitivity for detecting low risk loans (0.94).


