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

### Summary

  |***Features***|***Target***|
  |:--:|:--:|
  |D16 D42 D57 D76 D78 D71 D40 D52 D58 D65 D19 D67 D72 D28 D24 D64 D49 D50 D54 D55 D51 D53 D56 D20|Performance Standard Indication (Indicação do Padrão de Desempenho)| 

* The ``Performance Standard Indication`` target is a categorical variable and can have 4 different values, namely: {'Critical', 'Very Critical', 'Intermediate', 'Adequate'}. In this way, it is necessary to transform these values from type ***text*** (string) to type ***integer*** (numerical)

### Low Variance Filter

### Random Forests

### Principal Component Analysis (PCA)

## Conclusion
