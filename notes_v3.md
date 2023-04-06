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
I.    [Environment Meta-Work         ]
1.    [Strategy/Advice               ]
1.    [Environment Setup             ]
1.    [Git Setup                     ]
1.    [Git Work                      ]

---
<!-- 
Dataset Reference:
This section outlines where and how to request data from internet sources.
I'd like to have a repository of links for datasets for future reference.
API notes should be structured in API request examples, with options explained.
The end state of both methods should be an initial dataframe pre-editing.
-->
II.   [Dataset Reference             ]
1.    [Links to Datasets             ]
1.    [REST APIs                     ]

---
<!-- 
Advanced Web Scraping:
This is the rebel approach to data; not downloading it or registering for APIs.
Three main methods: pd.read_html, requests/beautifulsoup, selenium/beautifulsoup
I should use different examples for each, and incorporate REGEX usage.
The end state of all methods should be an initial dataframe pre-editing.
-->
III.  [Advanced Web Scraping         ]
1.    [Read-HTML                     ]
1.    [Requests                      ]
1.    [Selenium                      ]

---
<!-- 
Building a Database:
After data is acquired, a good option is storing it in a local database.
SQLite and PostgreSQL are popular options for local DB work and should be shown.
Both sections should be structured as an example with DB design tips throughout.
The end state of both explanations should be a "SELECT *"-style return (to DF).
-->
IV.   [Building a Database           ]
1.    [SQLite                        ]
1.    [PostgreSQL                    ]

---
<!-- 
Database Usage Mastery:
Querying a database is just as important as establishing one.
Each database format has its own syntax/peculiarities which should be explained.
Query differences should be demo'd thoroughly on a common dataset, if possible.
The end state should be a dataframe that matches across query formats.
-->
V.    [Database Usage Mastery        ]
1.    [SQLite                        ]
1.    [PostgreSQL                    ]
1.    [MySQL                         ]
1.    [Elasticsearch                 ]
1.    [Spark                         ]

---
<!-- 
Feature Transformation:
Once a dataframe is established, data cleaning and engineering begins.
There are a variety of goals for this work, but goals share common methods.
Topics: Data structure normalization, cell work, string/number vectorization
- Normalization: melt/dummies, merge/join/concat, nulls/imputation
- Cell work: masks (incl. REGEX), loc, fast find, fast sort, apply/applymap
- String work: str methods, REGEX capture, NLP token/lemmatization/stem/BOW
- Number work: calculations, cut/bins, scaling
Explanations here shouldn't go any further than feature engineering.
-->
VI.   [Feature Transformation        ]
1.    [Data Normalization            ]
1.    [Masks: Cell-Wise Handling     ]
1.    [String Work                   ]
1.    [Number Work                   ]

---
<!-- 
Algorithmic Clustering:
Engineered features can go through clustering to establish new features.
Popular clustering methods: K-Means, Hierarchical, DBSCAN, and NLP.
-->
VII.  [Algorithmic Clustering        ]
1.    [Feature Evaluation: Clustering]
1.    [Algorithm Selection           ]
1.    [Cluster analysis              ]
1.    [See: Clustering work for WGU  ]

---
<!-- 
Classification:

-->
VIII. [Classification                ]
1.    [Feature Evaluation: Classification]
1.    [Model Training                ]
1.    [Model Evaluation              ]

---
<!-- 
Regression:

-->
IX.   [Regression                    ]
1.    [Feature Evaluation: Regression]
1.    [Model Training                ]
1.    [Model Evaluation              ]

---
<!-- 
Time Series:

-->
X.    [Time Series                   ]
1.    [Feature Evaluation: Time Series]
1.    [Algorithm Selection           ]
1.    [Model Evaluation              ]

---
<!-- 
Anomaly Detection:

-->
XI.   [Anomaly Detection             ]
1.    [Feature Evaluation: Anomaly Detection]
1.    [Algorithm Selection           ]
1.    [Result Evaluation             ]

---
<!-- 
Deep Learning:

-->
XII.  [Deep Learning                 ]
1.    [Deep Learning Design (neural nodes)]
1.    [Outcome Evaluation            ]

---
<!-- 
Insight Delivery:

-->
XIII. [Insight Delivery              ]
1.    [Statistical Analysis          ]
1.    [Deliverables                  ]
1.    [Jupyter Notebooks             ]
1.    [Excel/Google Sheets           ]
1.    [PowerBI                       ]
1.    [Tableau                       ]

---
<!-- 
Model Deployment:

-->
XIV.  [Model Deployment              ]
1.    [Building a Flask app          ]
1.    [Deploying to Docker           ]
1.    [Deploying to Kubernetes       ]
1.    [Deploying to Apache Kafka     ]

---
<!-- 
Project Management:

-->
XV.   [Project Management            ]
1.    [Stakeholder Interaction       ]
1.    [Storytelling                  ]
1.    [Project Management/SDLC       ]

---
<!-- 
Other Languages:

-->
XVI.  [Other Languages               ]
1.    [R                             ]
1.    [C++                           ]

<br>
<br>

# Environment Meta-Work

## Strategy/Advice

## Anaconda

## Git

<br>

# Dataset Reference

## Downloadables (Website links)

## APIs

<br>

# Advanced Web Scraping

## REGEX in web-scraping

## Page requests

## Webdriver (Selenium)

<br>

# Building a Database

## Good DB design

## SQLite

## PostgreSQL

<br>

# Database Usage Mastery

## SQLite

## MySQL

## Elasticsearch

## Spark

<br>

# Feature Transformation

## REGEX, slicing

## Apply, applymap

## Find/replace (optimized search), sort (optimized)

## Melting, one-hot encoding

## Merge, join, concat

## Amplification (external data structures)

## Scaling

## NLP tokenization/lemmatization/etc

<br>

# Algorithmic Clustering

## Feature Evaluation: Clustering

## Algorithm Selection

## Cluster analysis

## See: Clustering work for WGU

<br>

# Classification

## Feature Evaluation: Classification
### Statistics
### SelectKBest
### Recursive Feature Engineering

## Model Training
### Algorithm Selection
### Resampling (training)

## Model Evaluation
### Metrics
### Cross-Validation

<br>

# Regression

## Feature Evaluation: Regression
### Statistics

## Model Training
### Algorithm Selection

## Model Evaluation
### Metrics
### Cross-Validation

<br>

# Time Series
## Feature Evaluation: Time Series

## Algorithm Selection

## Model Evaluation

<br>

# Anomaly Detection

## Feature Evaluation: Anomaly Detection

## Algorithm Selection

## Result Evaluation

<br>

# Deep Learning

## Deep Learning Design (neural nodes)
### Vision/Video

## Outcome Evaluation

<br>

# Insight Delivery

## Statistical Analysis
### Metrics, Probability, Hypotheses

## Jupyter Notebooks
### Matplotlib/Seaborn/Plotly

## Excel/Google Sheets

## PowerBI

## Tableau

<br>

# Model Deployment

## Building a Flask app

## Deploying to Docker

## Deploying to Kubernetes

## Deploying to Apache Kafka

<br>

# Project Management

## Stakeholder Interaction

## Storytelling

## Project Management/SDLC

<br>

# Other Languages

## R

## C++