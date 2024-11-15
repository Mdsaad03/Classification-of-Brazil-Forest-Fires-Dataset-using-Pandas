# Classification-of-Brazil-Forest-Fires-Dataset-using-Pandas
This project classifies forest fire occurrences in Brazil using the Brazil Forest Fires Dataset. It applies Pandas for data preprocessing, performs exploratory analysis, and uses machine learning models to predict fire events. Models are evaluated using accuracy and other metrics.
Objective
The goal is to predict whether a forest fire is likely to occur based on environmental factors. The project involves:

Data Cleaning: Preprocessing the dataset by handling missing values, encoding categorical variables, and scaling features.
Exploratory Data Analysis (EDA): Using statistical and visualization techniques to understand feature relationships.
Classification Models: Implementing machine learning models (e.g., Decision Trees, Random Forest, Logistic Regression) to classify fire occurrences.
Model Evaluation: Assessing model performance using metrics such as accuracy, precision, recall, and F1-score.

Technologies Used
Python: Core programming language.
Pandas: Data manipulation and preprocessing.
Scikit-learn: Machine learning model implementation and evaluation.
Matplotlib & Seaborn: Data visualization.



I got a hold of a dataset (from Kaggle) of forest fires in Brazil, which houses the largest rainforest on Earth — Amazon. I didn’t want to be picky and so this dataset was a complete random choice.
About the data:
year is the year when the forest fire happened;
state is the Brazilian state;
month is the month when the forest fire happened;
number is the number of forest fires reported;
date is the date when the forest fire was reported

Going through the csv file (amazon.csv), you notice that some numbers are in decimal. 2.588 numbers of forest fires doesn't make sense. That's because the decimal is how thousands are formatted. So, 2.588 means 2588 forest fires. This can easily be accounted for when reading the csv file.
You’ll also notice that the month column is in Portuguese. There's an upcoming fix for that too.
When I imported the file for the first time after downloading it, I got an error: UnicodeDecodeError: 'utf-8' codec can't decode byte in position : invalid continuation byte. To fix it, I opened the csv in Sublime Text and: Save with Encoding -> UTF-8. However, this caused errors in the date column. So, I simply opened up the original csv and exported it as csv. Weird but it worked.









