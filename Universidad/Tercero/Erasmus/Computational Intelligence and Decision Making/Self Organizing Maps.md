#Theory/AI 
# What is a SOM
It is a form of [[unsupervised learning]] that is used for visualization, clustering and exploratory data analysis of high dimensional datasets. A dimensionality reduction technique that can give insights about high dimensional data with minimal required computing.

The dataset is divided in a grid, having lattice nodes with parameters $l_{i} \in \mathbb{R}^{2}$ being the position in the 2D space and it never changes, and $\omega_{i} \in \mathbb{R}^d$ being the position in the real space and d the dimension of the input data. This says that if a node is cloe to each other in the input lattice they should be close in the input space.

The algorithm works as explained:
1. Initialize laticce nodes
2. Initialize weights(positions in the input data space)
3. While the conditions are not met do:
	1. Pick a random point in the dataset
	2. Find its best matching unit c(closest lattice node)
	3. Move the weight of c closer to x
	4. move weights of c neighbors closer to x

## Initializing Weights
There are several ways to initialize the ways with their pros and cons
- Random Initialization: Weights initialized with random values, this makes it slow for converging
- Random Sapmpling Initialization: Random points are chosen as initial vectors.
- Best candidate sampling initialization: place samples randomly to maximize the distance between sample.
- Principal component initialization: the weight vectors are initialized with respect the eigenvectors of two largest [[Eigenvalues]]

# Training SOM
Input data should be rescaled (usually, to [0,1]) to ensure that each feature has the same scale. Making it easier to wrok with.
## Online update step
𝐱 ∈ ℝ𝑑 - random datapoint from the input dataset
Index of best matching unit to the point 𝐱: 𝑐 𝐱 = arg min ||𝑖 𝐱 − 𝛚𝑖 ||
Update values of weight vectors for 𝑘 + 1 iteration: 𝛚𝑖 = 𝛚𝑖 + 𝛼 𝑘 ℎ𝑖,𝑐 𝐱 (𝐱 − 𝛚𝑖) 
𝛼 𝑘 - learning rate in the kth iteration (usually decreases exponentially during training) 
ℎ𝑖,𝑐 𝐱 - [[#Neighborhood functions]]

## Batch update step
Find best matching units (BMU) to all datapoints in dataset 𝐷 and number of datapoints with node 𝑗 as BMU: 𝑛𝑗 =$\sum$ 𝐱∈𝐷 ቊ 1, 𝑖𝑓 𝑐 𝑥 = 𝑗 0, 𝑜𝑡ℎ𝑒𝑟𝑤𝑖𝑠𝑒 
Update values of weight vectors for 𝑘 + 1 iteration
xj is the average of all data points closest to the 𝑗 lattice node 
ℎ𝑗,𝑖 - neighborhood distance function from 𝑖 to j

# Neighborhood functions
This functions are used to move the lattice nodes in the input space. They are the requirements for $h_{i,j}$  neighbourhood function between i to j. They should ==attain its maximum when $\parallel{l_i-l_j}\parallel=0$== as it means that i and j are the same node and they are symetric about the winning node j. ==They also decrease as $\parallel{l_i-l_j}\parallel$ increases== so further points have less effects. This are examples of usual functions used to update weights:
![[Pasted image 20230102162901.png]]
Being the from red more updated to deep blue, not updated.

# Visualizing a SOM
## Class representation map
Shows the most common type of class in each node. It is possible to construct continuous class representation. 
This example uses 3 labels. This means that each node has a color, but the black ones are really mixed and cannnot choose clearly a favorite label.
![[Pasted image 20230102163124.png]]
## U-Matrix
It's visualized as a cell for each node in the lattice space with color proportional to the average distance in the input space to neighbors of that node. Useful to find clusters and outliers. The brighter the color the further they are in that section from neighborgh nodes.
![[Pasted image 20230102163254.png]]
## Component planes
Shows the value of the weight vectors of the SOM in each dimension. It can be useful to analyze the impact of a variable in the model.
![[Pasted image 20230102163539.png]] ![[Pasted image 20230102163550.png]]