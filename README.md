# Dimensionality Reduction

## Intro
* This project was developed as a form of evaluation of the course "Dimensionality Reduction" in the MBA in Data Science at the University of Fortaleza.

## Objetive
* This project aims to analyze the mathematical descriptors of the senior year in Brazilian schools

## Description
* The Mathematics reference matrix is composed of four themes, related to skills developed by students. Within each theme there is a set of descriptors linked to the skills developed. The set of descriptors is different in each series evaluated.

  * ```THEME I``` - INTERACTING WITH NUMBERS AND FUNCTIONS
  * ```THEME II``` - LIVING WITH GEOMETRY
  * ```THEME III``` - LIVING THE MEASURES
  * ```THEME IV``` - TREATMENT OF INFORMATION

* The descriptors of each theme can be seen in ```ref_descritores.pdf```

* The analysis was divided in two levels: 
  * ```Data exploration```
  * ```Dimensionality reduction methods in relation to the performance of Machine Learning (ML) models```
  
## Data Exploration
 
* In data exploration, the following criteria were analyzed:
 
  * Total number of attributes and instances

  * Which variables are numeric? Which are categorical?

  * Distribution of the Performance Standard Indication variable

  * Frequency with which each school appears in the dataset

  * Frequency with which each county appears in the dataset

  * Is there any linear relationship between the descriptors?

## Correlation Between Themes
  
* First, an average of the descriptors of each theme was created, respectively:
  
  ![themes_avg1](/images/themes_avg1.png)
  
  ![themes_avg2](/images/themes_avg2.png)

* Then, 4 lists (m1, m2, m3, m4) were created with the average score of each municipality in relation to each theme, in which a pairplot and a correlation matrix were plotted:
   
  ![pairplot](/images/pairplot.png)
  
  ![corr_matrix](/images/corr_matrix.png)
  
* Analyzing the pairplot, we can verify that there is a positive linear correlation between the themes, which represent the descriptors

* It is observed that themes I, II and III have a higher linear correlation compared to theme IV which, nevertheless, still has a high correlation, that is, close to 1.

## Dimensionality Reduction Methods

### Importance

* A lower number of dimensions in data means less training time and less computational resources and increases the overall performance of machine learning algorithms

* Avoids the problem of overfitting and removes noise in the data

* Is useful for data visualization and for factor analysis

* Takes care of multicollinearity

* Can be used for image compression and to transform non-linear data into a linearly-separable form

Source: https://towardsdatascience.com/11-dimensionality-reduction-techniques-you-should-know-in-2021-dcb9500d388b

### Summary

  |***Features***|***Target***|
  |:--:|:--:|
  |D16 D42 D57 D76 D78 D71 D40 D52 D58 D65 D19 D67 D72 D28 D24 D64 D49 D50 D54 D55 D51 D53 D56 D20|Performance Standard Indication (Indicação do Padrão de Desempenho)| 

The ``Performance Standard Indication`` target is a categorical variable and can have 4 different values, namely: {'Critical', 'Very Critical', 'Intermediate', 'Adequate'}. In this way, it is necessary to transform these values from type ***text*** (string) to ***integer*** (numerical)

### Low Variance Filter

### Random Forests

Random forests is a tree-based model which is widely used for regression and classification tasks on non-linear data. It can also be used for feature selection with its built-in feature_importances_ attribute which calculates feature importance scores for each feature based on the ‘gini’ criterion (a measure of the quality of a split of internal nodes) while training the model.

A great advantage of a random forest is that it allows you to get an idea about the relative importance of each feature based on a score computed during the training phase. For this, he Scikit-learn RandomForestClassifier provides an attribute called feature_importances_. This returns an array of values which sum to 1. The higher the score, the more important the feature. The score is calculated based on the Gini impurity which measures the quality of a split (the lower the Gini, the better the split). Features with splits that have a greater mean decrease in Gini impurity are considered more important.

By looking at the feature importance, you can decide which features to drop because they don’t contribute enough for making the model. This is important because of the following reasons.
* Removing the least important features will increase the accuracy of the model. This is because we remove the noise by removing unnecessary features
* By removing the unnecessary features, you will avoid the problem of overfitting.
* A lesser amount of features also reduces training tim

Source: https://towardsdatascience.com/random-forests-an-ensemble-of-decision-trees-37a003084c6c

### Principal Component Analysis (PCA)

PCA is a linear dimensionality reduction technique. It transforms a set of correlated variables (p) into a smaller k (k<p) number of uncorrelated variables called principal components while retaining as much of the variation in the original dataset as possible.

The main concept behind the PCA is to consider the correlation among features. If the correlation is very high among a subset of the features, PCA will attempt to combine the highly correlated features and represent this data with a smaller number of linearly uncorrelated features. The algorithm keeps performing this correlation reduction, finding the directions of maximum variance in the original high-dimensional data and projecting them onto a smaller dimensional space. These newly derived components are known as principal components.

With these components, it is possible to reconstruct the original features — not exactly but generally close enough. The PCA algorithm actively attempts to minimize the reconstruction error during its search for the optimal components.

By reducing the dimensionality of the data, PCA will reduce the size of the data improving the performance of machine learning algorithms. PCA is an unsupervised technique, meaning that it does not use the information from the target vector and instead only considers the feature matrix.

Source: https://towardsdatascience.com/principal-component-analysis-pca-with-scikit-learn-1e84a0c731b0

## Conclusion
