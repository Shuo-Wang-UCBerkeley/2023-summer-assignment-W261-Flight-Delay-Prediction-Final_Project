# Final Project: Flight Delay Prediction

UC Berkeley MIDS Program 

Shuo Wang, A Adam Saleh, Liang Li, Qian Qiao

Summer 2023

- [Final Project: Flight Delay Prediction](#flight-delay-prediction)
  - [Project Overview](#project-overview)
  - [Dataset](#dataset)
  - [Models](#models)
  - [Experienment Results](#experienment-results)
  - [Model Evaluation and Metrics Summary](#model-evaluation-and-metrics-summary)
  - [Future Work](#future-work)
  - [Helpful Information](#helpful-information)
    - [Environment](#environment)
    - [Transformer Version](#transformer-version)

## Project Overview

Problem: US Flight delays ⇒ affecting consumers nationwide and impacting operational costs for airline and airports

Objective: Develop a predictive model that can anticipate flight delays (>15 mins).

## Dataset
![alt text](https://github.com/Shuo-Wang-UCBerkeley/2024-spring-assignment-W266-NLP_Final_Project/blob/main/Images/Dataset.png)

There are four datasets used for this project. 
- (1) The first dataset (**Flights Data**) is for flights originating and landing from/to US Domestic airports from 2015 to 2021. 
- (2) The second dataset (Weather Data) is for weather information from 2015 to 2021. 
- (3) The third dataset (Station Data) is for the weather stations, which contains location and proximity information to help identify the closest weather station to any airport in the first dataset. 
- (4) The fourth dataset (Airport Code Data) is for IATA airport code, a three-letter code that is used in passenger reservation, ticketing, and baggage-handling systems. 

the last dataset helps to connect airport to stations and, subsequently, to weather data. the last two tables are relatively smaller tables with tens of thousands of rows. the flight table is expected to be joined with other three tables to obtain useful weather related features pertinenet to each of the flight records.
Data dictionary: https://www.transtats.bts.gov/Fields.asp?gnoyr_VQ=FGJ
There are joined tables (OTPW) using data from all previously mentioned data tables (Airline, weather, sation & AITA). OTPW tables for different time periods are also provided. These consist of 3m, 6m, 1yr and the complete dataset (2015-2019). The total size of the three month OTPW dataset is 1,500,620,247 bytes, with 1,401,363 rows and 216 columns. The total size of the 2015-2019 OTPW dataset is 6,525,616,408 bytes, with 31,673,119 rows and 214 columns.
## Models
- Baseline Models
    - CountVectorizer - Complement Naive Bayes (CNB)
    - CountVectorizer - Multinomial Naive Bayes (MNB)
    - TfidfVectorizer - CNB
    - TfidfVectorizer - MNB
- Transformer Models
    - BART
    - BERT
    - BERT+CNN
    - DistilBERT
    - DistilBERT+CNN
    - ALBERT
    - RoBERTa
    - Bidirectional_GRU
- Models
    - Deep Averaging Network (DAN)
        - DAN-Static
        - DAN_Retrain_word2vec
        - DAN-REtrain_uniform
    - Weighted Averaging Networks (WANs)
    - Logestic Regression
    - CNN
        - CNN-non_Retrain
        - CNN-Retrain
    - RNN
        - RNN-non_Retrain
        - RNN-Retrain
    - CNN_RNN
        - CNN_RNN-non_Retrain
        - CNN_RNN-Retrain
## Experienment Results
![alt text](https://github.com/Shuo-Wang-UCBerkeley/2024-spring-assignment-W266-NLP_Final_Project/blob/main/Images/Experiment_Results.png)

## Model Evaluation and Metrics Summary
![alt text](https://github.com/Shuo-Wang-UCBerkeley/2024-spring-assignment-W266-NLP_Final_Project/blob/main/Images/Model_Evaluation_Metrics_Summary_1.png)
![alt text](https://github.com/Shuo-Wang-UCBerkeley/2024-spring-assignment-W266-NLP_Final_Project/blob/main/Images/Model_Evaluation_Metrics_Summary_2.png)

## Future Work
1. Multi-Class Text Classification. 

    The current data is highly imbalanced, a potential solution is to build a two-step models.  

2. Parallel Computing Technique

    Utilizing parallel computing technique to work for the advanced NLP algorithms, including RoBERTa-LONG, T5, and XLNET. These 3 models resulted in Resource Exhausted Errors with the limited GPU capacity in Google Colab.

![alt text](https://github.com/Shuo-Wang-UCBerkeley/2024-spring-assignment-W266-NLP_Final_Project/blob/main/Images/Label_Frequency.png)

## Helpful Information
### Environment
A series of notebooks and scripts are run on Google Colaboratory Pro using GPU environment.
### Transformer Version
Hugging Face updated the Transformers library, to run our code (like BERT) we need to revert to an earlier version of the Transformers library.

!pip install -q transformers==4.37.2

[Back-To-Top](#final-project-Text-Classification-on-Toxic-Comments)