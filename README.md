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

Problem: US Flight delays ⇒ affecting consumers nationwide

Objective: Develop a predictive model that can anticipate flight delays (>15 mins).

## Dataset
![alt text](https://github.com/Shuo-Wang-UCBerkeley/2024-spring-assignment-W266-NLP_Final_Project/blob/main/Images/Dataset.png)
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