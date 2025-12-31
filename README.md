
# 💳 Credit Card Transactions – Data Cleaning Project
📌 Project Overview:

This project focuses on cleaning and preparing a credit card transactions dataset obtained from Kaggle (“Comprehensive Credit Card Transactions”).
The raw dataset contains customer details, transaction dates, amounts, merchant information, and spending categories.
Since the raw data contains inconsistent formats, missing values, and incorrect data types, this project focuses entirely on data cleaning and preparation using Python and pandas.  
The final cleaned dataset is ready for:  
-Exploratory Data Analysis (EDA)   
-Data visualization (Tableau / Power BI)

📂 Dataset Information  
Source: Kaggle – Comprehensive Credit Card Transactions  
Link:https://www.kaggle.com/datasets/rajatsurana979/comprehensive-credit-card-transactions-dataset  
Rows: ~13,000 transactions  
Columns: 9  
Format: CSV       
Note: Raw dataset is not included in this repository.    

🎯 Project Objective:  
The main objective of this project is to:  
-Clean a real-world–like credit card transactions dataset sourced from Kaggle  
-Handle missing and invalid values properly  
-Fix date format issues  
-Preserve original data using a backup copy  
-Prepare a reliable dataset for analysis

🛠️ Tools Used  
-Python  
-Pandas  
-Jupyter Notebook

🔄 Data Cleaning Process:

1️⃣ Loading the Dataset and Creating a Backup  
The dataset was loaded using pandas.  
Before making any changes, a backup copy of the original dataset was created.  
df_raw = df.copy()  
This ensures the original data is always preserved and allows changes to be undone if needed.

2️⃣ Initial Data Inspection  
The dataset was inspected to understand:  
Column names  
Data types  
Missing values  
Overall dataset size     
This step helped identify which columns required cleaning.

3️⃣ Standardizing Column Names  
To improve readability and consistency:  
All column names were converted to lowercase  
Leading and trailing spaces were removed  
Spaces were replaced with underscores  
This makes the dataset easier to use in Python, SQL, and visualization tools.  

4️⃣ Handling Missing Values  
Different strategies were used based on column importance:  
Gender column:  
Missing values were filled with "Unknown" because gender is a categorical attribute.  
Critical columns (transaction date, merchant name, category):  
Rows with missing values in these columns were removed because they are essential for transaction analysis.

5️⃣ Fix Date Format Issues  
The date and birthdate columns were stored as text.  
-First Attempt  
I tried converting them normally using pandas:
pd.to_datetime(df['date'], errors='coerce')  
This caused some values to turn into NaT because the dataset uses day-month-year format.  
-Final Solution  
To fix this, I clearly told pandas that the day comes first:  
df['date'] = pd.to_datetime(df['date'], errors='coerce', dayfirst=True)
This correctly converted the dates.  
Any remaining invalid dates were removed.

6️⃣ Converting Data Types  
Date columns were converted to proper datetime format  
Numeric columns such as transaction amount were validated to ensure they contain numeric values  
This ensures correct calculations and time-based analysis.

7️⃣ Validating Transaction Amounts
The transaction amount column was checked to ensure:  
No non-numeric values  
No zero or negative transaction amounts.  
Invalid records were removed to maintain data quality.

8️⃣ Removing Duplicate Records  
Duplicate rows were identified and removed to avoid:  
Double-counting transactions  
Incorrect analytical results

9️⃣ Cleaning Text Columns  
Text columns such as:  
Customer name  
Surname  
Merchant name  
Category  
were cleaned by:  
Removing extra spaces  
Standardizing formatting  
This improves consistency across the dataset.

🔟 Feature Engineering  
Additional columns were created to support analysis:  
Transaction year  
Transaction month  
Day of the week  
Customer age at the time of transaction  
Unrealistic age values were filtered out to keep the data logical.

✅ Final Validation  
Final checks were performed to confirm:  
Correct data types  
Logical numeric ranges  
No unexpected missing values  
The dataset is now fully analysis-ready.


📁 Project Structure  
-cleaned_credit_card_transactions.csv- Final cleaned dataset
-creditcard_transactions.ipynb- jupyter notebook where it contains all the data cleaning code  
-README.md – Project overview, workflow, and execution instructions

▶️ How to Run This Project  
Download or clone this repository.  
Make sure Python and Jupyter Notebook are installed.  
Install pandas if needed:  
pip install pandas  
Open Jupyter Notebook or JupyterLab.  
Open creditcard_transactions.ipynb.  
Run all cells from top to bottom.  
The cleaned file cleaned_credit_card_transactions.csv will be created.

🧠 Key Learnings  
Importance of keeping a raw backup of data  
Handling missing values based on business logic  
Correct use of data types  
Writing clean and reusable pandas code  
Preparing real-world data for analysis


🚀 Next Steps  
Perform exploratory data analysis  
Study spending patterns  
Create visual dashboards using (Tableau/PowerBI)  
Use SQL for further analysis

🙏 Acknowledgements

Data for this project was sourced from Kaggle

Author:  
Puja Madhuri K  
Aspiring Data Analyst  
GitHub:https://github.com/pujamadhuri/Pandas_CreditCard_DataCleaning
