(setq markdown-css-paths '("style.css"))

# Determining Credit Risk

## Resampling Techniques

### Oversampling

#### Naive Random Oversampling

. Accuracy score (validation): 0.761

. confusion matrix

<pre>
--         --
|13029  4075|
|   29    72|
--         --
</pre>
 
. Imbalanced Classification Report

||pre|rec|spe|f1|geo|iba|sup|
|-|---|---|---|---|---|---|---|
|0|1.00|0.76|0.71|0.86|0.74|0.55|17104|
|1|0.02|0.71|0.76|0.03|0.74|0.54|101|
|avg / total|0.99|0.76|0.71|0.86|0.74|0.55|17205|

#### SMOTE Oversampling 

. Accuracy score (validation): 0.764

. confusion matrix

<pre>
--         --
|13066  4038|
|   29    72|
--         --
</pre>

       
. Imbalanced Classification Report

||pre|rec|spe|f1|geo|iba|sup|
|---|---|---|---|---|---|---|---|
|0|1.00|0.76|0.71|0.87|0.74|0.55|17104|
|1|0.02|0.71|0.76|0.03|0.74|0.54|101|
|avg / total|0.99|0.76|0.71|0.86|0.74|0.55|17205|

#### Undersampling

. Accuracy score (validation): 0.663

. confusion matrix

<pre>
--         --
|11335  5769|
|   22    79|
--         --
</pre>
       
. Imbalanced Classification Report

||pre|rec|spe|f1|geo|iba|sup|
||---|---|---|--|---|---|---|
|0|1.00|0.66|0.78|0.80|0.72|0.51|17104|
|1|0.01|0.78|0.66|0.03|0.72|0.52|101|
|avg / total|0.99|0.66|0.78|0.79|0.72|0.51|17205|

#### Combination (Over and Under) Sampling

. Accuracy score (validation): 0.738

. confusion matrix

<pre>
--         --
|12621  4483|
|   28    73|
--         --
</pre>
     
. Imbalanced Classification Report

||pre|rec|spe|f1|geo|iba|sup|
||---|---|---|---|---|---|---|
|0|1.00|0.74|0.72|0.85|0.73|0.53|17104|
|1|0.02|0.72|0.74|0.03|0.73|0.53|101|
|avg / total|0.99|0.74|0.72|0.84|0.73|0.53|17205|

## Ensemble Learners

### BalancedRandomForestClassifier

. Accuracy score (validation): 0.883

. confusion matrix

<pre>
--         --
|15134  1985|
|   35    51|
--         --
</pre>

. Imbalanced Classification Report:

||pre|rec|spe|f1|geo|iba|sup|
||---|---|---|---|---|---|---|
|0|1.00|0.88|0.59|0.94|0.72|0.54|17119|
|1|0.03|0.59|0.88|0.05|0.72|0.51|86|
|avg / total|0.99|0.88|0.59|0.93|0.72|0.54|17205|

### EasyEnsembleClassifier

. Accuracy score (validation): 0.942

. confusion matrix

<pre>
--         --
|16211  908|
|   11    75|
--         --
</pre>

. Imbalanced Classification Report:

||pre|rec|spe|f1|geo|iba|sup|
||---|---|---|---|---|---|---|
|0|1.00|0.95|0.87|0.97|0.91|0.83|17119|
|1|0.08|0.87|0.95|0.14|0.91|0.82|86|
|avg / total|0.99|0.95|0.87|0.97|0.91|0.83|17205|