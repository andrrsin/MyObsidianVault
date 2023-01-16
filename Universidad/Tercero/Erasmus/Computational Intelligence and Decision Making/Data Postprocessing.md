#Laboratory/AI #Theory/AI 

At the time of Postprocessing data the two most common problems faced are Underfitting and Overfitting.

- **Underfitting**: The prediction model is too simple to represent the realtionship between the decriptive features and the target features.
- **Overfitting**: This problem arises when the model is too complex that it becomes sensitive to the noise of the data

![[Pasted image 20221227073008.png]]

# Preventing Overfitting
The most common ways are: 
- Cross Validation
- More data(data augmentation)
- Remove Irrelevant Features
- Early stopping
- Regularization
- Ensemble(Collective decision)

# Evaluating a model
This technique consists on splitting the data in two parts usually being 70/30 or 60/40. The first group would be the training set which is used to build the decision making model and after the test set which is used to analyze the results.
## Other sampling techniques
Cross validation is a technique to test the data in an iterative way.
### Leave p-out or Exhaustive cross-validation
![[Pasted image 20221227073703.png]]
### K-folding cross-validation
![[Pasted image 20221227074027.png]]
### Stratified K-fold cross-validation
![[Pasted image 20221227074107.png]]
### Bootstraping
![[Pasted image 20221227074148.png]]

# Metrics
Metrics is as always, we like numbers and with this we get them.
## Confusion Matrix
The confusion matrix is a table containing the performance on classificating of a decision making model: The options are
- **True Positive (TP)** - a positive target feature value and correct prediction.
- **True Negative (TN)** - a negative target feature value and correct prediction
- **False Positive (FP)** - a positive target feature value and incorrect prediction
- **False Negative (FN)** - a negative target feature value and incorrect prediction

With this data we can calculate the missclasification rate and the accuracy:
$$missclasificationRate = \frac{(FP+FN)}{(TP+TN+FP+FN)}$$
$$classificationAccuracy = \frac{(TP+TN)}{(TP+TN+FP+FN)}$$
![[Pasted image 20221227075024.png]]
This is how a confussion matrix looks like. From here the measurements can be taken:
$$truePositiveRate(TPR)=\frac{TP}{TP+FN}$$
$$trueNegativeRate(TNR)=\frac{TN}{TN+FP}$$
$$falsePositiveRate(FPR)=\frac{FP}{TN+FP}$$
$$falseNegativeRate(FNR)=\frac{FN}{TP+FN}$$
## Continuous Targets
With continuous datathe best measures can be taken with:

![[Pasted image 20221227075504.png]]
However there are other good techniques such as the mean absolute error, $R^2$,...
## Object and Image Detection Targets
In cases like here where the actual cas is the red and the predicted is the green, the metrics can be taken by the intersection of both areas. There are other measures such as mean Average Precision (mAP)
$$IoU(A,B)=\frac{A\cap B}{A\cup B}$$
![[Pasted image 20221227075755.png]]
