# Classification-of-Brazil-Forest-Fires-Dataset-using-Pandas
This project classifies forest fire occurrences in Brazil using the Brazil Forest Fires Dataset. It applies Pandas for data preprocessing, performs exploratory data analysis (EDA), and uses machine learning models to predict fire events. Models are evaluated using accuracy and other metrics.

#Objective
The goal is to predict whether a forest fire is likely to occur based on environmental factors. The project involves:

Data Cleaning: Handling missing values, encoding categorical variables, and scaling features.
EDA: Statistical and visualization techniques to understand feature relationships.
Classification Models: Machine learning models (e.g., Decision Trees, Random Forest, Logistic Regression).
Model Evaluation: Metrics such as accuracy, precision, recall, and F1-score.
#Technologies Used
Python: Core programming language.
Pandas: Data manipulation and preprocessing.
Scikit-learn: Machine learning model implementation.
Matplotlib & Seaborn: Data visualization.
Googletrans: For translating text (e.g., month names).
#Dataset Details
The dataset, obtained from Kaggle, includes:

year: Year of forest fire occurrence.
state: Brazilian state where the fire occurred.
month: Month of occurrence (in Portuguese).
number: Number of forest fires reported.
date: Specific date of the report.

#Preprocessing Steps
Handling Thousand Separators: Convert numbers like 2.588 to 2588.
Encoding and Translation: Translate Portuguese month names to English using googletrans.
Fixing CSV Encoding Issues: Addressed UnicodeDecodeError by saving the file with UTF-8 encoding.

#Visualizations
Bar Graph: Forest Fires Over the Months
This graph visualizes the total number of forest fires across months from 1998–2017.



#Installation and Setup
Clone the repository:
https://github.com/Mdsaad03/Classification-of-Brazil-Forest-Fires-Dataset-using-Pandas/edit/main/README.md
Install the required libraries:
pip install pandas matplotlib scikit-learn googletrans

Place the amazon.csv file in the working directory.

#Key Scripts
Data Preprocessing:
Group data by month and sum the number of fires.
Translate Portuguese month names to English.
Plotting:
Use matplotlib for bar chart visualization.

#Learnings
Dealing with inconsistent datasets (e.g., formatting issues).
Applying Python libraries for preprocessing, EDA, and visualization.
Translating text programmatically using googletrans.

#Conclusion
This project demonstrates the end-to-end process of analyzing a dataset. It encourages experimentation and exploration, offering numerous learning opportunities.

Download a dataset and start exploring!









