# Blueberry-wine  

## Introduction

This project starts after the contact of BlueBerry Winery, a start-up wine maker in Portuguese region of Vinho Verde, that is trying to enter the wine business with a good amount of analytics and research on domain knowledge.  
The company provided me with 3 datasets, all details are provided in the below section.  
Through Data Mining techniques the aim is to extract high-level knowledge from this raw data. There are several algorithms, each one with its own advantages. Here.....(type of data, model).............. was used to determine .................  
The goal of this physicochemical analysis is to provide the company with useful insights on wine composition and the quality perceived by the consumers in order to:  
* pick the right grapes  
* improve the production process
* gain a significant advantage on the competition
* target marketing (consumers preferences of niche and/or profitable markets) 

## Data description

[Wine Quality dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality) is public available for research in the University of California, Irvine Machine Learning repository created by Paulo Cortez (Univ. Minho), Antonio Cerdeira, Fernando Almeida, Telmo Matos and Jose Reis (CVRVV) in 2009. This repository has two datasets of red and white wine samples which consists of inputs includes objective tests (e.g. PH values) and the output is based on sensory data (median of at least 3 evaluations made by wine experts). Each expert graded the wine quality between 0 (very bad) and 10 (very excellent). There are 1599 samples of red wine and 4898 samples of white wine in the data sets. Each wine sample (row) has the following characteristics (columns):

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

## Exploratory Analysis

The data was already clean when I receved it, I just merged the 2 data sets (red and white), added an extra column where I grouped the wine quality (expressed here with values from 3 to 9) into three buckets (low - medium -high) for simplicity and finally proceed with statistical analysis and visualizations.

**Univariate Analysis** perhaps the simplest way to visualize all the variables. I used here histograms.
**Multivariate Analysis** allowed me to analyse multiple variables and their relationship at once. This analysis showed me that there were patterns and relationship among the physicochemical attributes of the wine sample. This insights were really helpful during the modeling process to reduce the number of feature which were not having a high impact on the results I was looking for. I used here a heatmap depicting the correlation coefficient between each pair of features in the dataset.
Several other plots were used to discover more patterns and the relationship between the variables. (Boxplot - jointplot - scatterplot)

### Conclusions

## Modelling  

When applying a Data Mining method, the selection of the variables and models are a critical issue. The selection of variable is infact useful to discard irrelevant inputs and leads to simpler models that are easier to interpret and that usually give better performances.  
Complex models may overfit the data, losing the capability to generalize, while a model that is too simple will present limited learning capabilities.
