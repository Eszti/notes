# Machine Learning

## Problems

- classification
	- supervised
- clustering
	- unsupervised

## Clustering

- clusters: similar in some sense
- unsupervised (supervised way is classification)
- applications
	- outlier detection
	- recommender systems
	- social network analysis
	- image segmentation
	- bag of visual words
- elbow method: how many clusters
- evaluation
	- cluster silhouette

### Algorithms

- how to choose
	- domain knowledge
	- trial and error
	- visualisation in lower dimensions

#### K Means

- iterative
- compute cluster centers
- K Means ++ for choosing initial centers

#### Gaussian mixture EM Algorithm

- E-step & M-step
- similar to K Means

#### DBScan algorithm

- parameters: minPts, epsilon
- core points
- border points
- outlier points
- assumption: density of all clusters  is similar
- no centers to calculate

## Cleansing

- handle errors
	- removing outliers
	- value ranges
	- numerical vs categorical data
- repair or delete
- normalize
	- feature scaling
	- min-max normalizing, value [0,1]
	- mean norm, mean: 0
	- unit vector normalisation, all sample vector have length 1
	- IQR normalization, mean: 0, different scaling for outliers
	- min-max is usually enough
	- do for
		- distance based methods: kNN, PCA, gradient descent (converges faster)
	- probably don't do for alternative methods

## Outliers

- everything that does not belong to a cluster
- usual examples
	- missing data
	- measurement errors
	- too small sample size
- isolation forest
- local outlier factor
- SVM One Class
