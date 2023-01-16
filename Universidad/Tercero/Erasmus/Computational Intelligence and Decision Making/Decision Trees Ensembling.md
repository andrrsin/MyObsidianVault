#Theory/AI 
# Ensemble Decision Trees
Ensemble [[decision trees]] is creating numerous decision trees and aggregating the results, they usually deliver better results with the same computational an dalgorithmic complexity.
There are Three main types.
- Bagging
- Random Forest
- Boosting

The first two they can be parallelized to create the individual trees.

## Bagging
Bagging consists on splitting the data in a fixed number of sets with random sampling. Training a decision tree for each of the new datasets. After aggregating the results by average if it's a regression problem or voting for clasiffication(counting the categories and the biggest)
![[Pasted image 20230102121305.png]]

## Random Forest
Random forest are quite simmilar they consist on splitting the data in a fixed number of sets with random sampling. Training a decision tree for each of the new datasets. After aggregating the results by average if it's a regression problem or voting for clasiffication(counting the categories and the biggest). However random forest also traing their decision trees with a ==***random set of features***== 

## Boosting
The models are constructed sequentially. It evalueates the missclasifications of the DT of before and gives higher weights in loss functions. The aggregate result is a weighted aggregate of the predictions made by the individual models.
![[Pasted image 20230102121747.png]]
