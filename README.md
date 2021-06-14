# Blueberry-wine  

## Introduction

This project starts after the contact of BlueBerry Winery, a start-up wine maker in Portuguese region of Vinho Verde, that is trying to enter the wine business with a good amount of analytics and research on domain knowledge.  
The company provided me with 3 datasets, all details are provided in the below section.  
Through Data Mining techniques the aim is to extract high-level knowledge from this raw data. There are several algorithms, each one with its own advantages. 
The goal of this physicochemical analysis is to provide the company with useful insights on wine composition and the quality perceived by the consumers in order to:  
* pick the right grapes  
* improve the production process
* gain a significant advantage on the competition
* target marketing (consumers preferences of niche and/or profitable markets) 

## Data description

[Wine Quality dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality) is public available for research in the University of California, Irvine Machine Learning repository created by Paulo Cortez (Univ. Minho), Antonio Cerdeira, Fernando Almeida, Telmo Matos and Jose Reis (CVRVV) in 2009. This repository has [two datasets](https://github.com/davidellavalle/Blueberry-wine/tree/main/Data) of red and white wine samples which consists of inputs includes objective tests (e.g. PH values) and the output is based on sensory data (median of at least 3 evaluations made by wine experts). Each expert graded the wine quality between 0 (very bad) and 10 (very excellent). There are 1599 samples of red wine and 4898 samples of white wine in the data sets. Each wine sample (row) has the following characteristics (columns):

* Wine type - Red and White. 
* Fixed acidity - acids are major wine properties and contribute greatly to the wine’s taste. Usually, the total acidity is divided into two groups: the volatile acids and the nonvolatile or fixed acids. Among the fixed acids that can be found in wines are the following: tartaric, malic, citric, and succinic. This variable is expressed in g(tartaricacid)/dm3 in the data sets.
* Volatile acidity - the volatile acidity is basically the process of wine turning into vinegar. In the U.S, the legal limits of Volatile Acidity are 1.2 g/L for red table wine and 1.1 g/L for white table wine. In these data sets, the volatile acidity is expressed in g(aceticacid)/dm3.
* Citric acid - one of the fixed acids that in wines. It’s expressed in g/dm3 in the two data sets.
* Residual sugar - typically refers to the sugar remaining after fermentation stops, or is stopped. It’s expressed in g/dm3 in the red and white data.
* Chlorides - contributor to saltiness in wine. Here expressed in g(sodiumchloride)/dm3.
* Free sulfur dioxide - the part of the sulfur dioxide that is added to a wine and that is lost into it is said to be bound, while the active part is said to be free. The winemaker will always try to get the highest proportion of free sulfur to bind. This variable is expressed in mg/dm3 in the data.
* Total sulfur dioxide - the sum of the bound and the free sulfur dioxide (SO2). Here expressed in mg/dm3. There are legal limits for sulfur levels in wines: in the EU, red wines can only have 160mg/L, while white and rose wines can have about 210mg/L. Sweet wines are allowed to have 400mg/L. For the US, the legal limits are set at 350mg/L, and for Australia, this is 250mg/L.
Density
* pH - numeric scale to specify the acidity or basicity the wine. Solutions with a pH less than 7 are acidic, while solutions with a pH greater than 7 are basic. With a pH of 7, pure water is neutral. Most wines have a pH between 2.9 and 3.9 and are therefore acidic.
* Sulphates - are to wine as gluten is to food. They are a regular part of winemaking around the world and are considered necessary. Here expressed in g(potassiumsulphate)/dm3.
* Alcohol - wine is an alcoholic beverage and its percentage of alcohol can vary from wine to wine. This variable is expressed in % vol.
* Quality - score between 0 and 10

[Wine sales data](https://github.com/davidellavalle/Blueberry-wine/tree/main/Data)

* Country- country of wine production.
* Province - region of wine production.
* Description - review provided by wine experts.
* Designation - Winery producing the type of wine.
* Points - rating given by the expert.
* Price - wine selling price.
* variety - grape sort.
* winery - Winery producing the type of wine.

## [Exploratory Analysis](https://github.com/davidellavalle/Blueberry-wine/blob/main/Exploratory%20analysis.ipynb)

The data I received was already clean, datatypes were consistent and there were no missing values. I merged the 2 data sets (red and white), added an extra column where I grouped the wine quality (expressed here with values from 3 to 9) into three buckets (low - medium - high) for simplicity and finally proceed with statistical analysis and visualizations.

**Univariate Analysis** perhaps the simplest way to visualize all the variables. I used here histograms.  
**Multivariate Analysis** allowed me to analyse multiple variables and their relationship at once. This analysis showed me that there were patterns and relationship among the physicochemical attributes of the wine sample. This insights were really helpful during the modeling process to reduce the number of feature which were not having a high impact on the results I was looking for. I used here a heatmap depicting the correlation coefficient between each pair of features in the dataset.  
Several other plots were used to discover more patterns and the relationship between the variables. (Boxplot - jointplot - scatterplot)

### Conclusions

Total number of **red** wine data: 1599  
Wines with rating 8 and above: 18  
Wines with rating less than 5: 744  
Wines with rating 5 to 7: 837  
Percentage of wines with quality 7 and above: 1.13%  

Total number of **white** wine data: 4898  
Wines with rating 8 and above: 180  
Wines with rating less than 5: 1640  
Wines with rating 5 to 7: 3078  
Percentage of wines with quality 7 and above: 3.05%  

There is an high correlation between **alcohol** and overall wine **quality**: The more alcoholic the better the wine, a higher percent generally receive better ratings by the consumers.  
The **mean quality** of red wine is less than that of white wine.  
Wine with 'Low level' of **acidity** (≃ 0.4) receives a higher average rating from consumers.  
**Sulphates** play a more important role with red wines rather than whites. While in whites Suplhates concentration is below 0.5 throughout all quality labels, red wines show that an higher quantity improves quality. High quality wines anyway don't usually pass the 0.8 threshold.  
The optimal level of **pH** is to be found between 3.2 and 3.4 for both type of wines.  
There is a fundamental difference between the concentration of **Total sulfur dioxide** between whites (higher) and reds (lower).  

## [Modelling](https://github.com/davidellavalle/Blueberry-wine/tree/main/Modelling)  

I used here a *Supervised learning* type of machine learning since the data at my disposal was composed by measured features and had labels associated to it.  
My goal was to train a model that could in future be used to apply the same labels to new, unknown data.  
For this purpose I used the *classification* concept which basically categorizes a set of data into classes. The labels I are quality labels (low - medium - high) or wine type (red - white).   

Machine learning models:
* **Logistic Regression** to find the best-fitting relationship between the dependent variable (the discrete value I mentioned before) and the set of independent variables.  
* **Knn** K Nearest Neighbour, a simple algorithm that stores all the available cases and classifies the new data or case based on a similarity measure.
* **Decision Tree** where the data is continuously split according to a certain parameter. The tree can be explained by two entities, namely decision nodes and leaves: the leaves are the decisions or the final outcomes and the decision nodes are where the data is split.
* **Random Forest** conctruction of a multitude of decision trees at training time and output the class that is the mode of the classification.

Step by step

* Selection of the variables. The selection of variable is infact useful to discard irrelevant inputs and leads to simpler models that are easier to interpret and that usually give better performances.  
Complex models may overfit the data, losing the capability to generalize, while a model that is too simple will present limited learning capabilities.
* Fitting the model and prediction of the results.
* Accuracy check 
* Confusion Matrix - table allowing visualization of the performance of an algorithm
* Classification report
The precision is the ratio tp / (tp + fp) where tp is the number of true positives and fp the number of false positives. The precision is intuitively the ability of the classifier to not label a sample as positive if it is negative.
The recall is the ratio tp / (tp + fn) where tp is the number of true positives and fn the number of false negatives. The recall is intuitively the ability of the classifier to find all the positive samples.
The F-beta score can be interpreted as a weighted harmonic mean of the precision and recall, where an F-beta score reaches its best value at 1 and worst score at 0. The F-beta score weights the recall more than the precision by a factor of beta. beta = 1.0 means recall and precision are equally important.
The support is the number of occurrences of each class in y_test.
* Cross Validation as a resample procedure used to evaluate the machine learning model on a limited data sample. Called as well k-fold cross validation due to the single parameter called k (here cv) that refers to the number of groups that a given data sample is to be split into.

### Plots

Several Visualization are available in this [folder](https://github.com/davidellavalle/Blueberry-wine/tree/main/Plots%20-%20exploratory%20analysis)
