# Classification-of-Brazil-Forest-Fires-Dataset-using-Pandas
This project classifies forest fire occurrences in Brazil using the Brazil Forest Fires Dataset. It applies Pandas for data preprocessing, performs exploratory data analysis (EDA), and uses machine learning models to predict fire events. Models are evaluated using accuracy and other metrics.

# Objective
The goal is to predict whether a forest fire is likely to occur based on environmental factors. The project involves:

Data Cleaning: Handling missing values, encoding categorical variables, and scaling features.
EDA: Statistical and visualization techniques to understand feature relationships.
Classification Models: Machine learning models (e.g., Decision Trees, Random Forest, Logistic Regression).
Model Evaluation: Metrics such as accuracy, precision, recall, and F1-score.
# Technologies Used
Python: Core programming language.
Pandas: Data manipulation and preprocessing.
Scikit-learn: Machine learning model implementation.
Matplotlib & Seaborn: Data visualization.
Googletrans: For translating text (e.g., month names).
# Dataset Details
The dataset, obtained from Kaggle, includes:

year: Year of forest fire occurrence.
state: Brazilian state where the fire occurred.
month: Month of occurrence (in Portuguese).
number: Number of forest fires reported.
date: Specific date of the report.

# Preprocessing Steps
Handling Thousand Separators: Convert numbers like 2.588 to 2588.
Encoding and Translation: Translate Portuguese month names to English using googletrans.
Fixing CSV Encoding Issues: Addressed UnicodeDecodeError by saving the file with UTF-8 encoding.

# Visualizations
Bar Graph: Forest Fires Over the Months
This graph visualizes the total number of forest fires across months from 1998–2017.


Install the required libraries:
pip install pandas matplotlib scikit-learn googletrans

Place the amazon.csv file in the working directory.

# Key Scripts
Data Preprocessing:
Group data by month and sum the number of fires.
Translate Portuguese month names to English.
Plotting:
Use matplotlib for bar chart visualization.

# Learnings
Dealing with inconsistent datasets (e.g., formatting issues).
Applying Python libraries for preprocessing, EDA, and visualization.
Translating text programmatically using googletrans.

# Conclusion
This project demonstrates the end-to-end process of analyzing a dataset. It encourages experimentation and exploration, offering numerous learning opportunities.

Download a dataset and start exploring!


# TUTORIAL
Imports:
For this project, I set up a virtual environment using virtualenv. Check out this post for all the steps. We’re using three major libraries: pandas, matplotlib, googletrans.
!pip3 install the these packages (if you haven’t already) before importing them.

![image](https://github.com/user-attachments/assets/37cdde64-23dc-4556-a2b2-d9282dc388ce)


Read the data:
Before reading date place your amazon.csv[provided] in your directory

![image](https://github.com/user-attachments/assets/3d2f2725-258d-4659-b931-a69b2bbed0e7)

df = pd.read_csv("amazon.csv", thousands = '.')

![image](https://github.com/user-attachments/assets/7e18b7b8-e7ea-4a3c-a04b-040dabc49203)

View the data:

![image](https://github.com/user-attachments/assets/a6cb63db-e2aa-416c-b2b1-b02bee109eab)

![image](https://github.com/user-attachments/assets/3e6ea402-38da-4f85-ae8b-76c3d8ff570b)

Break the dataset into smaller subsets:
The first thought I had was to visualise the number of forest fires over the years, over the months. You need to be able to identify smaller pieces of the bigger picture.

Let’s drop rows from the dataset that aren’t contributing to the number of forest fires. So, any row with number column value as 0, must be dropped. We first convert the 0s to NaN and then drop rows with NaN in the specific column number.

![image](https://github.com/user-attachments/assets/b8d5a1fe-85cb-48c2-b037-ebc6692090c0)

Creating subset of data:

forest_fire_per_month = df2.groupby('month')['number'].sum() : grouping the data by month and summing the numbers. The output is a pandas series.

print(forest_fire_per_month) : we notice the result is in alphabetical order. To get it back to the monthly order, we use the reindex property of dataframes :

![image](https://github.com/user-attachments/assets/f3b4ec80-c22c-4939-aa58-58d361c80b3b)

![image](https://github.com/user-attachments/assets/6ca5467c-bbfb-40d9-9873-f188e0da566f)



This doesn’t look right. That’s because month is being considered as the index of the dataframe.
To set a default index:![image](https://github.com/user-attachments/assets/460e0599-2147-45da-905e-fc8004bdd10e)

forest_fire_per_month.reset_index(level=0, inplace=True)

forest_fire_per_month.head()

![image](https://github.com/user-attachments/assets/1f031049-1cc1-4d4a-9af3-7556ec86cf2b)

Enter googletrans:
googletrans is a python library that implements Google Translate API. I tested it out on months_unique.
CODE:
translator = Translator() #create an object of Translator 
for month in months_unique: 
    detected = translator.detect(month)     
    translated = translator.translate(month)     
    print(detected)     
    print(translated)     
    print("...")

![image](https://github.com/user-attachments/assets/b941e53c-b79b-46d6-9df6-473cb9f7faca)

![image](https://github.com/user-attachments/assets/2b7e6e0f-fed3-49c1-a303-08d3e03ce190)

Member variables of the returned Translator() object:

1.src — source language (default: auto)
2.de2st — destination language (default: en)
3.origin — original text
4.text — translated text
5.pronunciation — pronunciation
These variables can be individually accessed using the . operator.

Example: translated.text will output the translated English text.

We use an instance of Translator to translate the month column in forest_fire_per_month to English.
CODE2:
translator2 = Translator() 
for i, m in enumerate(forest_fire_per_month['month']):
    translated = translator2.translate(m)  
    month1 = translated.text    
    forest_fire_per_month.at[i, 'month'] = month1

    ![image](https://github.com/user-attachments/assets/9b623a4b-46c1-4911-a569-718cdb829c3d)

The enumerate() function assigns an index to each item in an iterable object that can be used to reference the item later.
The enumerate() function in Python is commonly used instead of the for loop. That’s because enumerate() can iterate over the index of an item, as well as the item itself.

print(forest_fire_per_month)

![image](https://github.com/user-attachments/assets/4df8e33a-311f-4dd5-a943-2ed2d6047d8a)

It worked on all but one case!


The plot:
Let’s bar graph it.

CODE:
import matplotlib.pyplot as plt

plt.figure(figsize=(25, 15))  
plt.bar(
    forest_fire_per_month['month'],
    forest_fire_per_month['number'], 
    color = (0.5, 0.1, 0.5, 0.6))  # create the bar chart
plt.suptitle('Amazon Forest Fires Over the Months', fontsize=20)
plt.title('Using Data from Years 1998 - 2017', fontsize=20)

plt.xlabel('Month', fontsize=20)
plt.ylabel('Number of Forest Fires', fontsize=20)
for i, num in enumerate(forest_fire_per_month['number']):
    plt.text(
        i,
        num + 10000,
        num,
        ha='center',
        fontsize=15)   

plt.setp(plt.gca().get_xticklabels(),
         rotation=45,
         horizontalalignment='right',
         fontsize=20)
plt.setp(plt.gca().get_yticklabels(), fontsize=20)
plt.show()

![image](https://github.com/user-attachments/assets/354a6921-5a04-4f6b-b319-f6276b6d9dc0)

This is a very small documentation of what can be done with this dataset. You only need to start. And the process is full of learning new things.

So, just download a random dataset and get going!










