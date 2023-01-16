#Laboratory/AI #Theory/AI 
# What is a feature?
There are two main types of features, raw and derived.
- Raw features: this features come directly from the data sources.
- Derived features: They are data obtained such from Raw Features.
	- Aggregates: (Count,Sum,average...)
	- Flags(binary features)
	- Ratios(continuos features with a realtionship between two or more data)
	- Mappings(converting continuous to categorical)

# Which are the types of Data?
The Data can be transformed in two big groups.
- Continuous: This type of data are the ones which allow arithmetical operations on them. Its variations are.
	- Numeric: True numeric values, which allow all arithmetic operations
	- Intervals: Values that allow ordering or substraction, but no other operations.
- Categorical: 
	- Ordinal: They allow ordering but no other operations. (usually they are dates)
	- Categorical: they cannot be ordered nor any other operation.
	- Binary: They act like booleans
	- Textual: Usually short text.


```ad-note
For categorical data we use the mode and the continuous features will use the mean
```

# Viewing the Data
## Boxplot
It consists on 5 points using the Quartiles. Marking the lower quartile and the upper as boundaries, the median, the maximum and the minimum values of the dataset. Note: the little lines out of the boundaries are abnormal points.
![[Pasted image 20221226172751.png]]
## Histogram
Histograms are a type of bar plot for ==numeric== data which group the data in bins.
![[Pasted image 20221226173011.png]]
# Data Quality
There are three main data quality issues tha we can get presented: missing values, irregular cardinality problems and outliers.
## Missing Values
Missing values are errors made by data generation or integration, they can also be made by human factor. 
```ad-warning
If the number of $NA\geqslant 60%$ then this feature must be removed, as it's not valid
```
In case of **NA** use imputation:
- For continuous use the mean value.
- For categorical use the mode value.

## Irregular Cardinality Problems
Cardinality shows the number of distinct values present for a feature. From here there are 3 main errors we can have:
- Cardinality of 1
- Too many cardinality for the categorical data
- The categorical data wrongly labeled as numeric
## Outliers
It is the data that is far away from the main tendency, they can either be invalid data like noise or that it appeared by mistake. Or they can be valid, rare values obtained.
Dealing with outliers give a much more general model that is more precise in a general scope.

For this we will use the [[Clamp transofrmation]].
## Data Standarization or Normalization
Sometimes the data is desired to be in a more simpler range. For that we can either Normalize the data to a range of $[0,1]$ or we can standarize the data to the Standard Normal Distribution with mean 0 and deviation of 1.
