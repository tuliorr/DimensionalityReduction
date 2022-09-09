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
 
## Dimensionality reduction methods
  
* First, an average of the descriptors of each theme was created, respectively:
  
  ![themes_avg1](/images/themes_avg1.png)
  
  ![themes_avg2](/images/themes_avg2.png)

* Then, 4 lists (m1, m2, m3, m4) were created with the average score of each municipality in relation to each theme, in which a pairplot and a correlation matrix were plotted:
   
  ![pairplot](/images/pairplot.png)
  
  ![corr_matrix](/images/corr_matrix.png)
