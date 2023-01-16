#Theory/AI #Laboratory/AI 
# What is a Decision Tree
A Decision Tree is a tree with nodes representing deterministic decisions based on
variables and edges representing path to next node or a leaf node based on the
decision. The complexity of Decision trees can be really big, therefore they should be stored once created.
![[Pasted image 20230102113703.png]]

# Creating a Decision Tree
To build a Decision Tree this algorithm should be followed:
1. Build the root with the most importatn variables
2. Build a decision with [[#Highest Information Split]]
3. Recursevly apply steps 1 and 2 to its subtrees


## Highest Information Split
The decision is based on information split, this relies usually in **Information Gain** and **Gini Impurity** which are used for Categorical and Continuous respectively.
### Entropy
Entropy falls in the information gain category and inmathematics, it is part of Information theory. Its base is that less impure nodes require less information where as more impure require more information. With entropy we measure the amount of information contained in each variable. I recommend checking this video by [3blue1brown](https://youtu.be/v68zYyaEmEA) on how to solve wordle with entropy.

The entropy formula looks like this:
$$H  = - \sum^{n}_{i=1}(p_{i}\log_2{p_i})$$
From H Outcome we get the smallest value always, however from Information Gain we will get the biggest one.
![[Pasted image 20230102115759.png]]
Here variable 1 will give us less bits of information than variable two so we choose variable 2 in the decision tree.

### Gini Impurity
Gini impurity is a measure of how often a randomly chosen element from the set is
incorrectly labelled if it were labelled according to the distribution of labels in the
subset. Higher values imply more erros whereas lower values imply more pure variables.
$$Ic(p) = \sum^J_{i=0}{p_i(1-p_i)}$$
In constructing a Decision Tree split, the goal is to split with the lowest weighted Gini
impurity value for the child trees.
