# <center><strong>Data Science Notes, v3</strong></center>

<!-- 
#######                                              
   #      ##   #####  #      ######     ####  ###### 
   #     #  #  #    # #      #         #    # #      
   #    #    # #####  #      #####     #    # #####  
   #    ###### #    # #      #         #    # #      
   #    #    # #    # #      #         #    # #      
   #    #    # #####  ###### ######     ####  #      
                                                     
 #####                                                 
#     #  ####  #    # ##### ###### #    # #####  ####  
#       #    # ##   #   #   #      ##   #   #   #      
#       #    # # #  #   #   #####  # #  #   #    ####  
#       #    # #  # #   #   #      #  # #   #        # 
#     # #    # #   ##   #   #      #   ##   #   #    # 
 #####   ####  #    #   #   ###### #    #   #    ####  
-->

# Table of Contents
<!-- 
Environment Meta-Work:
It's nice having a step-by-step reference for setting up Anaconda envs and Git.
Env setup can probably be copied over as-is; I use it fairly often.
Git can be mostly copy-pasted, but I'd like to add authentication instructions.
I might want to add a script to update packages...
-->
I.    [Environment Meta-Work         ](#environment-meta-work)
1.    [Environment Setup             ](#environment-setup)
1.    [Git Setup                     ](#git-setup)
1.    [Git Work                      ](#git-work)

<!-- 
Dataset Reference:
This section outlines where and how to request data from internet sources.
I'd like to have a repository of links for datasets for future reference.
API notes should be structured in API request examples, with options explained.
The end state of both methods should be an initial dataframe pre-editing.
-->
II.   [Dataset Reference             ](#dataset-reference)
1.    [Links to Datasets             ](#links-to-datasets)
1.    [REST APIs                     ](#rest-apis)

<!-- 
Advanced Web Scraping:
This is the rebel approach to data; not downloading it or registering for APIs.
Three main methods: pd.read_html, requests/beautifulsoup, selenium/beautifulsoup
I should use different examples for each, and incorporate REGEX usage.
The end state of all methods should be an initial dataframe pre-editing.
-->
III.  [Advanced Web Scraping         ](#advanced-web-scraping)
1.    [Read-HTML                     ](#read-html)
1.    [Requests                      ](#requests)
1.    [Selenium                      ](#selenium)

<!-- 
Building a Database:
After data is acquired, a good option is storing it in a local database.
SQLite and PostgreSQL are popular options for local DB work and should be shown.
Both sections should be structured as an example with DB design tips throughout.
The end state of both explanations should be a "SELECT *"-style return (to DF).
-->
IV.   [Building a Database           ](#building-a-database)
1.    [SQLite                        ](#sqlite)
1.    [PostgreSQL                    ](#postgresql)

<!-- 
Database Usage Mastery:
Querying a database is just as important as establishing one.
Each database format has its own syntax/peculiarities which should be explained.
Query differences should be demo'd thoroughly on a common dataset, if possible.
The end state should be a dataframe that matches across query formats.
-->
V.    [Database Usage Mastery        ](#database-usage-mastery)
1.    [SQL and Variants              ](#sql-and-variants)
1.    [Elasticsearch                 ](#elasticsearch)
1.    [Spark                         ](#spark)

<!-- 
Feature Transformation:
Once a dataframe is established, data cleaning and engineering begins.
There are a variety of goals for this work, but goals share common methods.
Topics: Data structure normalization, cell work, string/number vectorization
- Normalization: melt/dummies, merge/join/concat, nulls/imputation
- Cell work: masks (incl. REGEX), loc, fast find, fast sort, apply/applymap
- String work: str methods, REGEX capture
- Number work: calculations, cut/bins, scaling
Other data structures like linked lists and hash tables can be useful too.
Explanations here shouldn't go any further than feature engineering.
-->
VI.   [Feature Transformation        ](#feature-transformation)
1.    [Dataframe Normalization       ](#dataframe-normalization)
1.    [Fixing Dataframes at Speed    ](#fixing-dataframes-at-speed)
1.    [Feature Engineering           ](#feature-engineering)
1.    [Speedy Data Structures        ](#speedy-data-structures)

<!-- 
Algorithmic Clustering:
Engineered features can go through clustering to establish new features.
The number of clusters is determined through three main methods:
- Domain Knowledge (three classes)
- Elbow Method (compare inertias for a range of cluster numbers)
- PCA (find clusters and "explainer" features using signal-noise ratio)
Popular clustering methods: K-Means, Hierarchical, and DBSCAN.
-->
VII.  [Algorithmic Clustering        ](#algorithmic-clustering)
1.    [Selecting Number of Clusters  ](#selecting-number-of-clusters)
1.    [Clustering Methods            ](#clustering-methods)
1.    [Cluster Analysis              ](#cluster-analysis)

<!--
Natural Language Processing:
String-type fields can be normalized to identify trends in words.
This is largely pipelined via tokenization and stem/lemmatization.
The results of NLP can be used to identify keywords and sentiment.
NLP's "bag of words" works nicely in conjunction with classification.
-->
VIII. [Natural Language Processing   ](#natural-language-processing)
1.    [Normalizing String Features   ](#normalizing-string-features)
1.    [Keywords and Sentiment        ](#keywords-and-sentiment)
1.    [NLP for Prediction            ](#nlp-for-prediction)

<!-- 
Insight Delivery:
Delivery of findings is key to project success.
Hypothesis testing and statistical analysis is complex, but it can be pipelined.
Good visualizations speak for themselves and you can template them for reuse.
Jupyter notebooks are optimal for report delivery and should be mastered.
-->
IX.   [Insight Delivery              ](#insight-delivery)
1.    [Statistical Analysis          ](#statistical-analysis)
1.    [Visualizations                ](#visualizations)
1.    [Magic in Jupyter              ](#magic-in-jupyter)

<!-- 
Classification:
Predicting outcomes and states of unseen data using trained models.
Features are chosen for modeling via chi2 tests, t-tests, SelectKBest/RFE
Training data includes "the answers" and can be resampled.
Model evaluation is important and done in two stages: validate and test.
-->
X.    [Classification                ](#classification)
1.    [Features for Classification   ](#features-for-classification)
1.    [Training Classifiers          ](#training-classifiers)
1.    [Evaluating Classifiers        ](#evaluating-classifiers)

<!-- 
Regression:
Predicting a numerical value for unseen data using trained models.
Features are chosen for modeling via correlation tests, t-tests, SelectKBest/RFE
Training data includes "the answers"; all data (incl. unseen) should be scaled.
Model evaluation is important and done in two stages: validate and test.
-->
XI.   [Regression                    ](#regression)
1.    [Features for Regression       ](#features-for-regression)
1.    [Training Regressors           ](#training-regressors)
1.    [Evaluating Regressors         ](#evaluating-regressors)

<!-- 
Time Series:
Understanding previous trends and their anomalies to do various things.
You can calculate several metrics for time series data; monthly/weekly/daily/...
Generally, you're tracking one numerical feature over a time axis with plots.
Modeling varies from using past data with adjustment to actual trainable models.
-->
XII.  [Time Series                   ](#time-series)
1.    [Metrics of Time Series        ](#metrics-of-time-series)
1.    [Outcome Plotting              ](#outcome-plotting)
1.    [Time Series Modeling          ](#time-series-modeling)

<!-- 
Anomaly Detection:
Finding outliers in data as the goal.
Metrics are the main way of determining anomalies.
Getting to the number for a metric can be simple or fairly complicated.
Baselining a dataset to find anomalies in unseen data requires a careful hand.
-->
XIII. [Anomaly Detection             ](#anomaly-detection)
1.    [Anomalic Metrics              ](#anomalic-metrics)
1.    [Getting to the Numbers        ](#getting-to-the-numbers)
1.    [Baselines and Deviation       ](#baselines-and-deviation)

<!-- 
Neural Networks:
When you don't have the capacity to do regular ML, you use neural networks.
Neural networks have special setup, so instructions would be nice to have.
Neural Networks are especially great for image and audio classification.
Deep learning leverages multiple neural networks; I might explain it, IDK yet.
-->
XIV.  [Neural Networks               ](#neural-networks)
1.    [Establishing a Neural Network ](#establishing-a-neural-network)
1.    [Image Classification          ](#image-classification)
1.    [Deep Learning                 ](#deep-learning)

<!-- 
Model Deployment:
Once a model is trained and evaluated, we can deploy it.
A Flask application is fine if you just need model I/O and basic UI.
You can use Django if your application needs a wide range of functionality.
Docker, Kubernetes, and Kafka have handling considerations that should be noted.
-->
XV.   [Model Deployment              ](#model-deployment)
1.    [Building a Flask App          ](#building-a-flask-app)
1.    [Building a Django App         ](#building-a-django-app)
1.    [Deploying the Model           ](#deploying-the-model)

<!-- 
Project Management:
It's important to note how projects work from a management perspective.
Project planning is vital to project success and can't be overestimated.
There are a lot of common project management frameworks and interpretations.
-->
XVI.  [Project Management            ](#project-management)
1.    [Planning a Project            ](#planning-a-project)
1.    [Selecting the Framework       ](#selecting-the-framework)

<!-- 
Tools and Languages:
Some environments require specific tools and programming languages.
Excel is a monster with its wide variety of functions.
PowerBI and Tableau may be the main tools used by a team and should be known.
R is an alternative to Python and used especially in academia (use is waning).
C++ pointer manipulation is very fast, so C++ might play a role in development.
-->
XVII. [Tools and Languages           ](#tools-and-languages)
1.    [Excel and Google Sheets       ](#excel-and-google-sheets)
1.    [PowerBI                       ](#powerbi)
1.    [Tableau                       ](#tableau)
1.    [R                             ](#r)
1.    [C++                           ](#c)

<br>

<br>







<!-- 
#######                                                                 
#       #    # #    # # #####   ####  #    # #    # ###### #    # ##### 
#       ##   # #    # # #    # #    # ##   # ##  ## #      ##   #   #   
#####   # #  # #    # # #    # #    # # #  # # ## # #####  # #  #   #   
#       #  # # #    # # #####  #    # #  # # #    # #      #  # #   #   
#       #   ##  #  #  # #   #  #    # #   ## #    # #      #   ##   #   
####### #    #   ##   # #    #  ####  #    # #    # ###### #    #   #   
                                                                        
#     #                           #     #                      
##   ## ###### #####   ##         #  #  #  ####  #####  #    # 
# # # # #        #    #  #        #  #  # #    # #    # #   #  
#  #  # #####    #   #    # ##### #  #  # #    # #    # ####   
#     # #        #   ######       #  #  # #    # #####  #  #   
#     # #        #   #    #       #  #  # #    # #   #  #   #  
#     # ######   #   #    #        ## ##   ####  #    # #    #  
-->

# Environment Meta-Work

## Environment Setup

## Git Setup

## Git Work

[[Return to Top]](#table-of-contents)







<!-- 
######                                          
#     #   ##   #####   ##    ####  ###### ##### 
#     #  #  #    #    #  #  #      #        #   
#     # #    #   #   #    #  ####  #####    #   
#     # ######   #   ######      # #        #   
#     # #    #   #   #    # #    # #        #   
######  #    #   #   #    #  ####  ######   #   
                                                
######                                                          
#     # ###### ###### ###### #####  ###### #    #  ####  ###### 
#     # #      #      #      #    # #      ##   # #    # #      
######  #####  #####  #####  #    # #####  # #  # #      #####  
#   #   #      #      #      #####  #      #  # # #      #      
#    #  #      #      #      #   #  #      #   ## #    # #      
#     # ###### #      ###### #    # ###### #    #  ####  ###### 
-->

# Dataset Reference

## Links to Datasets

## REST APIs

[[Return to Top]](#table-of-contents)







<!-- 
   #                                                     
  # #   #####  #    #   ##   #    #  ####  ###### #####  
 #   #  #    # #    #  #  #  ##   # #    # #      #    # 
#     # #    # #    # #    # # #  # #      #####  #    # 
####### #    # #    # ###### #  # # #      #      #    # 
#     # #    #  #  #  #    # #   ## #    # #      #    # 
#     # #####    ##   #    # #    #  ####  ###### #####  
                                                         
#     #                   #####                                              
#  #  # ###### #####     #     #  ####  #####    ##   #####  # #    #  ####  
#  #  # #      #    #    #       #    # #    #  #  #  #    # # ##   # #    # 
#  #  # #####  #####      #####  #      #    # #    # #    # # # #  # #      
#  #  # #      #    #          # #      #####  ###### #####  # #  # # #  ### 
#  #  # #      #    #    #     # #    # #   #  #    # #      # #   ## #    # 
 ## ##  ###### #####      #####   ####  #    # #    # #      # #    #  ####  
-->

# Advanced Web Scraping

## Read-HTML

## Requests

## Selenium

[[Return to Top]](#table-of-contents)







<!-- 
######                                                   
#     # #    # # #      #####  # #    #  ####       ##   
#     # #    # # #      #    # # ##   # #    #     #  #  
######  #    # # #      #    # # # #  # #         #    # 
#     # #    # # #      #    # # #  # # #  ###    ###### 
#     # #    # # #      #    # # #   ## #    #    #    # 
######   ####  # ###### #####  # #    #  ####     #    # 
                                                         
######                                                  
#     #   ##   #####   ##   #####    ##    ####  ###### 
#     #  #  #    #    #  #  #    #  #  #  #      #      
#     # #    #   #   #    # #####  #    #  ####  #####  
#     # ######   #   ###### #    # ######      # #      
#     # #    #   #   #    # #    # #    # #    # #      
######  #    #   #   #    # #####  #    #  ####  ###### 
-->

# Building a Database

## SQLite

## PostgreSQL

[[Return to Top]](#table-of-contents)







<!-- 
######                                                     #     #               
#     #   ##   #####   ##   #####    ##    ####  ######    #     #  ####  ###### 
#     #  #  #    #    #  #  #    #  #  #  #      #         #     # #      #      
#     # #    #   #   #    # #####  #    #  ####  #####     #     #  ####  #####  
#     # ######   #   ###### #    # ######      # #         #     #      # #      
#     # #    #   #   #    # #    # #    # #    # #         #     # #    # #      
######  #    #   #   #    # #####  #    #  ####  ######     #####   ####  ###### 
                                                                                 
#     #                                         
##   ##   ##    ####  ##### ###### #####  #   # 
# # # #  #  #  #        #   #      #    #  # #  
#  #  # #    #  ####    #   #####  #    #   #   
#     # ######      #   #   #      #####    #   
#     # #    # #    #   #   #      #   #    #   
#     # #    #  ####    #   ###### #    #   #   
                                                
-->

# Database Usage Mastery

## SQL and Variants

## Elasticsearch

## Spark

[[Return to Top]](#table-of-contents)







<!-- 
#######                                                                         
   #    #####    ##   #    #  ####  ######  ####  #####  #    # # #    #  ####  
   #    #    #  #  #  ##   # #      #      #    # #    # ##  ## # ##   # #    # 
   #    #    # #    # # #  #  ####  #####  #    # #    # # ## # # # #  # #      
   #    #####  ###### #  # #      # #      #    # #####  #    # # #  # # #  ### 
   #    #   #  #    # #   ## #    # #      #    # #   #  #    # # #   ## #    # 
   #    #    # #    # #    #  ####  #       ####  #    # #    # # #    #  ####  
                                                                                
#######                                                 
#       ######   ##   ##### #    # #####  ######  ####  
#       #       #  #    #   #    # #    # #      #      
#####   #####  #    #   #   #    # #    # #####   ####  
#       #      ######   #   #    # #####  #           # 
#       #      #    #   #   #    # #   #  #      #    # 
#       ###### #    #   #    ####  #    # ######  ####  
-->

# Feature Transformation

## Dataframe Normalization

## Fixing Dataframes at Speed

## Feature Engineering

## Speedy Data Structures

[[Return to Top]](#table-of-contents)







<!-- 
   #                                                               
  # #   #       ####   ####  #####  # ##### #    # #    # #  ####  
 #   #  #      #    # #    # #    # #   #   #    # ##  ## # #    # 
#     # #      #      #    # #    # #   #   ###### # ## # # #      
####### #      #  ### #    # #####  #   #   #    # #    # # #      
#     # #      #    # #    # #   #  #   #   #    # #    # # #    # 
#     # ######  ####   ####  #    # #   #   #    # #    # #  ####  
                                                                   
 #####                                                           
#     # #      #    #  ####  ##### ###### #####  # #    #  ####  
#       #      #    # #        #   #      #    # # ##   # #    # 
#       #      #    #  ####    #   #####  #    # # # #  # #      
#       #      #    #      #   #   #      #####  # #  # # #  ### 
#     # #      #    # #    #   #   #      #   #  # #   ## #    # 
 #####  ######  ####   ####    #   ###### #    # # #    #  ####  
-->

# Algorithmic Clustering

## Selecting Number of Clusters

## Clustering Methods

## Cluster Analysis

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                          
##    #   ##   ##### #    # #####    ##   #      
# #   #  #  #    #   #    # #    #  #  #  #      
#  #  # #    #   #   #    # #    # #    # #      
#   # # ######   #   #    # #####  ###### #      
#    ## #    #   #   #    # #   #  #    # #      
#     # #    #   #    ####  #    # #    # ###### 
                                                 
#                                                        
#         ##   #    #  ####  #    #   ##    ####  ###### 
#        #  #  ##   # #    # #    #  #  #  #    # #      
#       #    # # #  # #      #    # #    # #      #####  
#       ###### #  # # #  ### #    # ###### #  ### #      
#       #    # #   ## #    # #    # #    # #    # #      
####### #    # #    #  ####   ####  #    #  ####  ###### 
                                                         
######                                                            
#     # #####   ####   ####  ######  ####   ####  # #    #  ####  
#     # #    # #    # #    # #      #      #      # ##   # #    # 
######  #    # #    # #      #####   ####   ####  # # #  # #      
#       #####  #    # #      #           #      # # #  # # #  ### 
#       #   #  #    # #    # #      #    # #    # # #   ## #    # 
#       #    #  ####   ####  ######  ####   ####  # #    #  ####  
-->

# Natural Language Processing

## Normalizing String Features

## Keywords and Sentiment

## NLP for Prediction

[[Return to Top]](#table-of-contents)







<!-- 
###                                     
 #  #    #  ####  #  ####  #    # ##### 
 #  ##   # #      # #    # #    #   #   
 #  # #  #  ####  # #      ######   #   
 #  #  # #      # # #  ### #    #   #   
 #  #   ## #    # # #    # #    #   #   
### #    #  ####  #  ####  #    #   #   
                                        
######                                             
#     # ###### #      # #    # ###### #####  #   # 
#     # #      #      # #    # #      #    #  # #  
#     # #####  #      # #    # #####  #    #   #   
#     # #      #      # #    # #      #####    #   
#     # #      #      #  #  #  #      #   #    #   
######  ###### ###### #   ##   ###### #    #   #   
-->

# Insight Delivery

## Statistical Analysis

## Visualizations

## Magic in Jupyter

[[Return to Top]](#table-of-contents)







<!-- 
 #####                                                                             
#     # #        ##    ####   ####  # ###### #  ####    ##   ##### #  ####  #    # 
#       #       #  #  #      #      # #      # #    #  #  #    #   # #    # ##   # 
#       #      #    #  ####   ####  # #####  # #      #    #   #   # #    # # #  # 
#       #      ######      #      # # #      # #      ######   #   # #    # #  # # 
#     # #      #    # #    # #    # # #      # #    # #    #   #   # #    # #   ## 
 #####  ###### #    #  ####   ####  # #      #  ####  #    #   #   #  ####  #    # 
-->

# Classification

## Features for Classification

## Training Classifiers

## Evaluating Classifiers

[[Return to Top]](#table-of-contents)







<!-- 
######                                                            
#     # ######  ####  #####  ######  ####   ####  #  ####  #    # 
#     # #      #    # #    # #      #      #      # #    # ##   # 
######  #####  #      #    # #####   ####   ####  # #    # # #  # 
#   #   #      #  ### #####  #           #      # # #    # #  # # 
#    #  #      #    # #   #  #      #    # #    # # #    # #   ## 
#     # ######  ####  #    # ######  ####   ####  #  ####  #    # 
-->

# Regression

## Features for Regression

## Training Regressors

## Evaluating Regressors

[[Return to Top]](#table-of-contents)







<!-- 
#######                     #####                                
   #    # #    # ######    #     # ###### #####  # ######  ####  
   #    # ##  ## #         #       #      #    # # #      #      
   #    # # ## # #####      #####  #####  #    # # #####   ####  
   #    # #    # #               # #      #####  # #           # 
   #    # #    # #         #     # #      #   #  # #      #    # 
   #    # #    # ######     #####  ###### #    # # ######  ####  
-->

# Time Series

## Metrics of Time Series

## Outcome Plotting

## Time Series Modeling

[[Return to Top]](#table-of-contents)







<!-- 
   #                                             
  # #   #    #  ####  #    #   ##   #      #   # 
 #   #  ##   # #    # ##  ##  #  #  #       # #  
#     # # #  # #    # # ## # #    # #        #   
####### #  # # #    # #    # ###### #        #   
#     # #   ## #    # #    # #    # #        #   
#     # #    #  ####  #    # #    # ######   #   
                                                 
######                                                   
#     # ###### ##### ######  ####  ##### #  ####  #    # 
#     # #        #   #      #    #   #   # #    # ##   # 
#     # #####    #   #####  #        #   # #    # # #  # 
#     # #        #   #      #        #   # #    # #  # # 
#     # #        #   #      #    #   #   # #    # #   ## 
######  ######   #   ######  ####    #   #  ####  #    # 
-->

# Anomaly Detection

## Anomalic Metrics

## Getting to the Numbers

## Baselines and Deviation

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                    
##    # ###### #    # #####    ##   #      
# #   # #      #    # #    #  #  #  #      
#  #  # #####  #    # #    # #    # #      
#   # # #      #    # #####  ###### #      
#    ## #      #    # #   #  #    # #      
#     # ######  ####  #    # #    # ###### 
                                           
#     #                                                 
##    # ###### ##### #    #  ####  #####  #    #  ####  
# #   # #        #   #    # #    # #    # #   #  #      
#  #  # #####    #   #    # #    # #    # ####    ####  
#   # # #        #   # ## # #    # #####  #  #        # 
#    ## #        #   ##  ## #    # #   #  #   #  #    # 
#     # ######   #   #    #  ####  #    # #    #  ####  
-->

# Neural Networks

## Establishing a Neural Network

## Image Classification

## Deep Learning

[[Return to Top]](#table-of-contents)







<!-- 
#     #                             
##   ##  ####  #####  ###### #      
# # # # #    # #    # #      #      
#  #  # #    # #    # #####  #      
#     # #    # #    # #      #      
#     # #    # #    # #      #      
#     #  ####  #####  ###### ###### 
                                    
######                                                               
#     # ###### #####  #       ####  #   # #    # ###### #    # ##### 
#     # #      #    # #      #    #  # #  ##  ## #      ##   #   #   
#     # #####  #    # #      #    #   #   # ## # #####  # #  #   #   
#     # #      #####  #      #    #   #   #    # #      #  # #   #   
#     # #      #      #      #    #   #   #    # #      #   ##   #   
######  ###### #      ######  ####    #   #    # ###### #    #   #   
-->

# Model Deployment

## Building a Flask App

## Building a Django App

## Deploying the Model

[[Return to Top]](#table-of-contents)







<!-- 
######                                           
#     # #####   ####       # ######  ####  ##### 
#     # #    # #    #      # #      #    #   #   
######  #    # #    #      # #####  #        #   
#       #####  #    #      # #      #        #   
#       #   #  #    # #    # #      #    #   #   
#       #    #  ####   ####  ######  ####    #   
                                                 
#     #                                                               
##   ##   ##   #    #   ##    ####  ###### #    # ###### #    # ##### 
# # # #  #  #  ##   #  #  #  #    # #      ##  ## #      ##   #   #   
#  #  # #    # # #  # #    # #      #####  # ## # #####  # #  #   #   
#     # ###### #  # # ###### #  ### #      #    # #      #  # #   #   
#     # #    # #   ## #    # #    # #      #    # #      #   ##   #   
#     # #    # #    # #    #  ####  ###### #    # ###### #    #   #   
-->

# Project Management

## Planning a Project

## Selecting the Framework

[[Return to Top]](#table-of-contents)







<!-- 
#######                                                     
   #     ####   ####  #       ####       ##   #    # #####  
   #    #    # #    # #      #          #  #  ##   # #    # 
   #    #    # #    # #       ####     #    # # #  # #    # 
   #    #    # #    # #           #    ###### #  # # #    # 
   #    #    # #    # #      #    #    #    # #   ## #    # 
   #     ####   ####  ######  ####     #    # #    # #####  
                                                            
#                                                               
#         ##   #    #  ####  #    #   ##    ####  ######  ####  
#        #  #  ##   # #    # #    #  #  #  #    # #      #      
#       #    # # #  # #      #    # #    # #      #####   ####  
#       ###### #  # # #  ### #    # ###### #  ### #           # 
#       #    # #   ## #    # #    # #    # #    # #      #    # 
####### #    # #    #  ####   ####  #    #  ####  ######  ####  
-->

# Tools and Languages

## Excel and Google Sheets

## PowerBI

## Tableau

## R

## C++

[[Return to Top]](#table-of-contents)