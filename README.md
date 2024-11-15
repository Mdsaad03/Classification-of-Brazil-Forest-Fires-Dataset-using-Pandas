# Classification-of-Brazil-Forest-Fires-Dataset-using-Pandas
This project classifies forest fire occurrences in Brazil using the Brazil Forest Fires Dataset. It applies Pandas for data preprocessing, performs exploratory analysis, and uses machine learning models to predict fire events. Models are evaluated using accuracy and other metrics.
HOW TO DO
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
Imports:
For this project, I set up a virtual environment using virtualenv. Check out this post for all the steps. We’re using three major libraries: pandas, matplotlib, googletrans.
!pip3 install the these packages (if you haven’t already) before importing them.
![image](https://github.com/user-attachments/assets/58f96309-e7c3-47b0-b53a-b0b4589d9075)

