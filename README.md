# Exploratory-Data-Analysis
In the data exploration, we use the collected data to identify the measurement level of variables, investigate the univariate, and bivariate distributions, try to identify the variability between the variables, and pre-process the data so that it can be used as an input for different segmentation algorithms. Data exploration helps in understanding the data more clearly through visualization which in return helps to extract market segments.
## 1.	Steps that are performed in data exploration:

### a)	Data cleaning:

The first thing we need to do when we get the data is to deal with the data cleaning part. It is very important as mistakes happen during the data entry which leads to errors in data. We need to check whether a specific feature is a numeric or categorical variable. In the case of categorical variables, we need to check the consistency of the labels so that each label is giving an almost equal contribution. In the case of numeric variables, we deal with the situation by using statistical measures like mean, median, and mode.

### b)	Descriptive Analysis:

After cleaning the data we should try to visualize the features of the data through a graphical representation by using histogram plots, bar plots, boxplots, etc. Histograms help us understand whether the data is skewed and the number of distributions in the data. We need to select an appropriate number of bins to get a histogram that is precise. In cases, if we are unable to justify the number of bins we can use a boxplot which helps to determine the median, first and third quartile, and outliers if the data is unimodular.

### c)	Data pre-processing:

#### I.	Categorical variables:

In the case of categorical variables, we can do two types of data pre-processing where the categorical labels can be merged to a single label or they can be converted to numeric. The categorical variables are assumed to be converted to numeric data if the adjacent distances between the categorical variables in the ordinal scale are approximately equal whereas binary variables do not require pre-processing because there are only two outcomes.

#### II.	Numeric Variables:

For numeric variables, we standardize the data to bring every segmentation variable to the same scale. If any data points are missing we can use statistical measures like mean, median and mode to fill the gaps.

### d)	Principal Components Analysis:

Principal components analysis (PCA) transforms a multivariate data set containing metric variables into a new data set with variables referred to as the principal components which are uncorrelated and ordered by importance. The first variable (principal component) contains most of the variability, the second principal component contains the second most variability, and so on. In most cases, the transformation obtained from principal components analysis is used to project high-dimensional data into lower dimensions for plotting purposes. The fact that the first few principal components do not explain much of the variance indicates that all the original items (survey questions) are needed as segmentation variables. From a projection perspective, this is bad news because it is not easy to project the data into lower dimensions. Check if the segmentation variables are correlated. If they are, choose a subset of uncorrelated segmentation variables.

# Extracting segments
## 1.	Grouping Consumers:

The combination of exploratory methods and unstructured consumer data means that results from any method used to extract market segments from such data will strongly depend on the assumptions made on the structure of the segments implied by the method. Many segmentation methods used to extract market segments are taken from the field of cluster analysis. It is important to try out different types of clustering algorithm methods to explore market segmentation solutions. It is also important to understand how different algorithms impose structure on the extracted segments. If consumer data is well-structured and well-separated, distinct market segments exist, the tendencies of different algorithms matter less. If, however, data is not well-structured, the tendency of the algorithm influences the solution substantially.

## 2.	Distance-Based Methods:

### I.	Distance measures:

It uses a typical data matrix. Each row represents an observation, and every column represents a variable. Mathematically, this can be represented as an n × p matrix where n stands for the number of observations (rows) and p for the number of variables (columns). Numerous approaches to measuring the distance between two vectors exist; several are used routinely in cluster analysis and market segmentation. A distance is a function with two arguments: the two vectors x and y between which the distance is being calculated. The result is the distance between them (a nonnegative value). The distance metrics that are widely used are Euclidian distance, Manhattan distance (absolute distance), and asymmetric binary distance.

### II.	Hierarchical Methods:

Hierarchical clustering methods are the most intuitive way of grouping data because they mimic how a human would approach the task of dividing a set of n observations (consumers) into k groups (segments). There are 2 types of hierarchical clustering:

•	Divisive hierarchical clustering methods start with the complete data set X and splits it into two market segments in the first step. Then, each of the segments is again split into two segments. This process continues until each consumer has their own market segment.
•	Agglomerative hierarchical clustering approaches the task from the other end. The starting point is each consumer representing their own market segment (n singleton clusters). Step by step, the two market segments closest to one another are merged until the complete data set forms one large market segment.

The result of hierarchical clustering is typically presented as a dendrogram. A dendrogram is a tree diagram. The root of the tree represents the one-cluster solution where one market segment contains all consumers.

### III.	Partitioning Methods:
Hierarchical clustering methods are particularly well suited for the analysis of small data sets with up to a few hundred observations. For larger data sets, dendrograms are hard to read. 

#### a.	k-Means and k-Centroid Clustering:

The most popular partitioning method is k-means clustering. The following generic algorithm represents a heuristic for solving the optimization problem of dividing consumers into a given number of segments such that consumers are similar to their fellow segment members, but dissimilar to members of other segments. This algorithm is iterative; it improves the partition in each step, and is bound to converge, but not necessarily to the global optimum. The key idea is to systematically repeat the extraction process for different numbers of clusters (or market segments), and then select the number of segments that leads to either the most stable overall segmentation solution, or to the most stable individual segment. The machine learning community has also proposed a number of clustering algorithms. Within this community, the term unsupervised learning is used to refer to clustering because groups of consumers are created without using an external (or dependent) variable. In contrast, supervised learning methods use a dependent variable.  The smaller this number, the more homogeneous the segments; members assigned to the same market segment are like one another.

#### b.	“Improved” k-Means:

Many attempts have been made to refine and improve the k-means clustering
algorithm. The simplest improvement is to initialize k-means using “smart” starting values, rather than randomly drawing k consumers from the data set and using them as starting points. One way of avoiding the problem of the algorithm getting stuck in a local optimum is to initialize it using starting points evenly spread across the entire data space. Such starting points better represent the entire data set.

#### c.	Hard Competitive Learning:

Hard competitive learning, also known as a learning vector differs from the standard k-means algorithm in how segments are extracted. Hard competitive learning randomly picks one consumer and moves this consumer’s closest segment representative a small step in the direction of the randomly chosen consumer.

#### d.	Neural Gas and Topology Representing Networks:

Here, not only the segment representative (centroid) is moved towards the randomly selected consumer. Instead, also the location of the second closest segment representative (centroid) is adjusted towards the randomly selected consumer. However, the location of the second closest representative is adjusted to a smaller degree than that of the primary representative.

#### e.	Self-Organising Maps:

Another variation of hard competitive learning is self-organizing maps also referred to as self-organizing feature maps or Kohonen maps. The self-organizing map algorithm is like hard competitive learning: a single random consumer is selected from the data set, and the closest representative for this random consumer moves a small step in their direction. In addition, representatives which are direct grid neighbors of the closest representative move in the direction of the selected random consumer. The process is repeated many times; each consumer in the data set is randomly chosen multiple times and used to adjust the location of the centroids in the Kohonen map.

#### f.	Neural Networks:

Auto-encoding neural networks for cluster analysis work mathematically differently than all cluster methods presented so far. The most popular method from this family algorithm uses a so-called single hidden layer perceptron. Neural network clustering is an example of a so-called fuzzy segmentation with membership values between 0 (not a member of this segment) and 1 (member of only this segment). Membership values between 0 and 1 indicate membership in multiple segments.

### IV.	Hybrid Approaches:

Several approaches combine hierarchical and partitioning algorithms in an attempt
to compensate the weaknesses of one method with the strengths of the other the data for applying these methods. Also, dendrograms become very difficult to interpret when the sample size is large.

#### i.	Two-Step Clustering:

The two steps consist of running a partitioning procedure followed by a hierarchical procedure. The exact number of clusters k in this first step is not crucial. For large empirical data sets, much larger numbers of clusters can be extracted. The choice of the original number of clusters to extract is not crucial because the primary aim of the first step is to reduce the size of the data set by retaining only one representative member of each of the extracted clusters. Such an application of cluster methods is often also referred to as vector quantization.

#### ii.	Bagged Clustering:

Bagged clustering also combines hierarchical clustering algorithms and partitioning clustering algorithms but adds bootstrapping. Bootstrapping can be implemented by random drawing from the data set with replacement. That means that the process of extracting segments is repeated many times with randomly drawn (bootstrapped) samples of the data. Bootstrapping has the advantage of making the final segmentation solution less dependent on the exact people contained in consumer data.

## 3.	Model-Based Methods:

### 	Finite Mixtures of Distributions:

The simplest case of model-based clustering has no independent variables x, and
simply fits a distribution to y.

#### 	Normal Distributions:

For metric data, the most popular finite mixture model is a mixture of several multivariate normal distributions. The multivariate normal distribution can easily model covariance between variables, and approximate multivariate normal distributions occur in both biology and business.

#### 	Binary Distributions:

For binary data, finite mixtures of binary distributions, are sometimes also referred to as latent class models or latent class analysis. The mixture model assumes that respondents in different segments have different probabilities of undertaking certain activities. For example, some respondents may be interested in alpine skiing and not interested in sightseeing. This leads to these two variables being negatively correlated in the overall data set. However, this correlation is due to groups of respondents interested in one of the two activities only.

### 	Finite Mixtures of Regressions:

Finite mixtures of distributions are like distance-based clustering methods
and in many cases result in similar solutions. Compared to hierarchical or partitioning clustering methods, mixture models sometimes produce more useful, and sometimes less useful solutions. A finite mixture of regression models assumes the existence of a dependent target variable y that can be explained by a set of independent variables x. The functional relationship between the dependent and independent variables is considered different for different market segments.

### 	Extensions and Variations:

Finite mixture models are more complicated than distance-based methods. The
additional complexity makes finite mixture models very flexible. finite mixture models can accommodate a wide range of different data characteristics: for metric data, we can use mixtures of normal distributions, for binary data we can use mixtures of binary distributions. For nominal variables, we can use mixtures of multinomial distributions or multinomial logit models. For ordinal variables, several models can be used as the basis of mixtures. Ordinal variables are tricky because they are susceptible to containing response styles. To address this problem, we can use mixture models disentangling response style effects from content-specific responses while extracting market segments.






