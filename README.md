# Determining Credit Risk

## Resampling Techniques

### Oversampling

#### Naïve Random Oversampling

- **Accuracy score (validation)**: 0.761

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|13029  4075|
|   29    72|
--         --
</pre>
 
- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|-|---|---|---|---|---|---|---|
|0|1.00|0.76|0.71|0.86|0.74|0.55|17104|
|1|0.02|0.71|0.76|0.03|0.74|0.54|101|
|avg / total|0.99|0.76|0.71|0.86|0.74|0.55|17205|


#### SMOTE Oversampling 

- **Accuracy score (validation)***: 0.764

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|13066  4038|
|   29    72|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.76|0.71|0.87|0.74|0.55|17104|
|1|0.02|0.71|0.76|0.03|0.74|0.54|101|
|avg / total|0.99|0.76|0.71|0.86|0.74|0.55|17205|

#### Undersampling

- **Accuracy score (validation)**: 0.663

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|11335  5769|
|   22    79|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|--|---|---|---|
|0|1.00|0.66|0.78|0.80|0.72|0.51|17104|
|1|0.01|0.78|0.66|0.03|0.72|0.52|101|
|avg / total|0.99|0.66|0.78|0.79|0.72|0.51|17205|

#### Combination (Over and Under) Sampling

- **Accuracy score (validation)**: 0.738

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|12621  4483|
|   28    73|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.74|0.72|0.85|0.73|0.53|17104|
|1|0.02|0.72|0.74|0.03|0.73|0.53|101|
|avg / total|0.99|0.74|0.72|0.84|0.73|0.53|17205|

## Ensemble Learners

### BalancedRandomForestClassifier

- **Accuracy score (validation)**: 0.883

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|15134  1985|
|   35    51|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.88|0.59|0.94|0.72|0.54|17119|
|1|0.03|0.59|0.88|0.05|0.72|0.51|86|
|avg / total|0.99|0.88|0.59|0.93|0.72|0.54|17205|

### EasyEnsembleClassifier

- **Accuracy score (validation)**: 0.942

- **Confusion matrix**:

<pre style="text-align:center">
--         --
|16211  908|
|   11    75|
--         --
</pre>

- **Imbalanced Classification Report**:

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.95|0.87|0.97|0.91|0.83|17119|
|1|0.08|0.87|0.95|0.14|0.91|0.82|86|
|avg / total|0.99|0.95|0.87|0.97|0.91|0.83|17205|


## Analysis

### Accuracy<br>

| Classification method               | Accuracy |
|-------------------------------------:|:----------:|
|Undersampling                        |0.663|
|Combination (Over and Under) Sampling|0.738|
|Naïve Random Oversampling            |0.761|
|SMOTE Oversampling                   |0.764|
|BalancedRandomForestClassifier       |0.883|
|EasyEnsembleClassifier               |0.942|

The table above shows the classification methods sorted by the prediction accuracy, in ascending order. It can be observed that the worst accuracy results are achieved with undersampling which, considering that the technique involves shrinking the dataset to a very small number, is not surprising. The best accuracy is achieved by the **Ensemble AdaBoost Classifier**.

### Imbalanced Classification Report<br>

#### F1 Score

|	|TP	|FP	|FN	|Precision	|Recall	|F1|
|-|---|---|---|----------|-------|--|
|Naïve Random Oversamplingsampling	|72	|4075	|29	|0.017361948396431	|0.712871287128713	|0.033898305084746|
|SMOTE Oversampling	|72	|4038	|29	|0.017518248175183	|0.712871287128713	|0.034196152932795|
|Undersampling	|79	|5769	|22	|0.013508891928865	|0.782178217821782	|0.026559085560599|
|Combination (Over and Under) Sampling	|73	|4483	|28	|0.016022827041264	|0.722772277227723	|0.031350654928065|
|BalancedRandomForestClassifier	|51	|1985	|35	|0.025049115913556	|0.593023255813954	|0.048067860508954|
|EasyEnsembleClassifier	|75	|908	|11	|0.076297049847406	|0.872093023255814	|0.140318054256314|

The table above shows that classification methods with their F1 scores. In a confirmation of the finding related to accuracy, this table also shows that the best F1 score has been achieved by the **Ensemble AdaBoot Classifier**.

## Conclusion

The classification method that achieves the best results by far and wide is the **Ensemble AdaBoost Classifier**.