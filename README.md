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






