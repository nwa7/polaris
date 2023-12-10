# Website Fingerprinting
Website fingerprinting is a technique for identifying websites visited by users on anonymous networks, such as the Tor network. 
It involves analyzing network traffic patterns to infer specific websites a user is accessing.

## Overview
This project aims to analyze web traffic data from both monitored and non-monitored websites. 

## Dataset
The project uses data from the following two sources
1. mon_standard.pkl
- This file contains data from 'monitored' websites
- Class count: 95
- Instance count: 19,000
2. unmon_standard10.pkl
- This file contains data from 'unmonitored' websites
- Instance count: 10,000

## Scenarios
### Closed-world
In this scenario, the model is trained solely on the monitored traffic dataset.
The objective is to build a classification model that categorizes the 95 classes of web traffic based on learned patterns and features from the known network behavior.

### Open World Scenario
In this scenario, the model is trained using data from both the monitored and unmonitored traffic dataset.
Two types of classifications were carried out
1. Binary Classification
- The objective is to build a classification model that determines whether the web traffic trace corresponds to a monitored or unmonitored website.
2. Multiclass Classification
- The objective is to build a classification model that categorizes the 95 classes of monitored websites as well as an additional class of unmonitored websites.

## Repository Contents
1. **Data Folder**

Contains the datasets used for training, validation, and testing. This folder includes:
- **'X1.pkl'**: a pickle file containing the sequence of packet timestamps for each monitored instance
- **'X2.pkl'**: a pickle file containing the sequence of packet timestamps for each monitored instance
- **'y.pkl'**: a pickle file containing the classes corresponding to each monitored instance 
- **'X1_unmonitored.pkl'**: a pickle file containing the sequence of packet timestamps for each unmonitored instance
- **'X2_unmonitored.pkl'**:: a pickle file containing the sequence of packet timestamps for each unmonitored instance

2. **'feature_selection.ipynb'**
- Generates the subset of features that returns the best accuracy

3. **'closed_world.ipynb'**
- Classification for the closed-world scenario
- Models used: Decision Tree, Random Forest, K-NN

4. **'binary_classification.ipynb'**
- Classification for the open-world binary scenario
- Models used: SVM, Logistic Regression, Random Forest, Gradient Boosting

5. **'multiclass_classification.ipynb'**
- Classification for the open-world multiclass scenario
- Models used: Decision Tree, Random Forest, K-NN

For all notebooks: 
```
with open('/content/drive/My Drive/Machine Learning Project/CODES/X1.pkl', 'rb') as file:
    X1 = pickle.load(file)
```
Replace all file paths accordingly to where your 'Data' folder is stored
