# Determining Credit Risk

## Purpose
The aim of this project is to determine which classification technique produces the best results when applied to the task of determining credit riskiness. 

## Method

The following classification models were applied to the data and the statistics of their performance documented:

1. Resampling Techniques

    i. Oversampling - Naïve Random Overampling  
    ii. Oversampling - SMOTE Oversampling  
    iii. Undersampling  
    iv. Combination Over- and Undersampling  

2. Ensemble Learners

    i.  Balance Random Forest Classifier  
    ii. Easy Ensemble AdaBoost Classifier


## Resampling Techniques

### Oversampling

#### Naïve Random Oversampling

- **Balanced Accuracy score (validation)**: 0.835

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|14502  2602|
|   18    83|
--         --
</pre>
 
- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|-|---|---|---|---|---|---|---|
|0|1.00|0.85|0.82|0.92|0.83|0.70|17104|
|1|0.03|0.82|0.85|0.06|0.83|0.69|101|
|avg / total|0.99|0.85|0.82|0.91|0.83|0.70|17205|


#### SMOTE Oversampling 

- **Balanced Accuracy score (validation)***: 0.841

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|14883  2221|
|   19    82|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.87|0.81|0.93|0.84|0.71|17104|
|1|0.04|0.81|0.87|0.07|0.84|0.70|101|
|avg / total|0.99|0.87|0.81|0.92|0.84|0.71|17205|

### Undersampling

- **Balanced Accuracy score (validation)**: 0.824

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|13121  3983|
|   12    89|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|--|---|---|---|
|0|1.00|0.77|0.88|0.87|0.82|0.67|17104|
|1|0.02|0.88|0.77|0.04|0.82|0.68|101|
|avg / total|0.99|0.77|0.88|0.86|0.82|0.67|17205|

#### Combination (Over and Under) Sampling

- **Balanced Accuracy score (validation)**: 0.841

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|14723  2381|
|   18    83|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.86|0.82|0.92|0.84|0.71|17104|
|1|0.03|0.82|0.86|0.06|0.84|0.70|101|
|avg / total|0.99|0.86|0.82|0.92|0.84|0.71|17205|

## Ensemble Learners

### BalancedRandomForestClassifier

- **Balanced Accuracy score (validation)**: 0.792

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|14212  2904|
|   22    67|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.83|0.75|0.91|0.79|0.63|17116|
|1|0.02|0.75|0.83|0.04|0.79|0.62|89|
|avg / total|0.99|0.83|0.75|0.90|0.79|0.63|17205|

### EasyEnsembleClassifier

- **Balanced Accuracy score (validation)**: 0.902

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|15506  1610|
|    9    80|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.91|0.90|0.95|0.90|0.81|17116|
|1|0.05|0.90|0.91|0.09|0.90|0.81|89|
|avg / total|0.99|0.91|0.90|0.95|0.90|0.81|17205|


## Analysis

### Accuracy<br>

| Classification method               | Accuracy |
|-------------------------------------:|:----------:|
|BalancedRandomForestClassifier       |0.792|
|Undersampling                        |0.824|
|Naïve Random Oversampling            |0.835|
|SMOTE Oversampling                   |0.841|
|Combination (Over and Under) Sampling|0.841|
|EasyEnsembleClassifier               |0.902|

The table above shows the classification methods sorted by the prediction accuracy, in ascending order. It can be observed that the worst accuracy results are achieved with undersampling which, considering that the technique involves shrinking the dataset to a very small number, is not surprising. The best accuracy is achieved by the **Ensemble AdaBoost Classifier**.

### F1 Score

|	|F1|
|-|--|
|Undersampling	|0.04|
|BalancedRandomForestClassifier	|0.04|
|Naïve Random Oversamplingsampling	|0.06|
|Combination (Over and Under) Sampling	|0.06|
|SMOTE Oversampling	|0.07|
|EasyEnsembleClassifier	|0.09|

The table above shows that classification methods with their F1 scores. In a confirmation of the finding related to accuracy, this table also shows that the best F1 score has been achieved by the **Ensemble AdaBoot Classifier**.

## Conclusion

The classification method that achieves the best results is the **Ensemble AdaBoost Classifier**.