# MCA-labsheet-1
Lab Environment Setup, Python Libraries Installation, Jupyter Notebook &amp; Dataset Loading
# ==========================================
# MCA III Semester - Lab Sheet 01
# ==========================================


# Q1
import sys

print("Python Version:")
print(sys.version)


# Q2
# To be run in the terminal:
pip install notebook
jupyter notebook


# Q3
# To be run in the terminal:
pip install numpy

import numpy as np
print("NumPy Version:", np.__version__)


# Q4
# To be run in the terminal:
pip install pandas

import pandas as pd
print("Pandas Version:", pd.__version__)


# Q5
# To be run in the terminal:
pip install matplotlib

import matplotlib.pyplot as plt
x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 25, 30]
plt.plot(x, y, marker="o")
plt.title("Simple Line Plot")
plt.xlabel("X Values")
plt.ylabel("Y Values")
plt.show()


# Q6 
# To be run in the terminal:
pip install seaborn

import seaborn as sns
data = sns.load_dataset("tips")
sns.boxplot(x="day", y="total_bill", data=data)
plt.title("Total Bill on Different Days")
plt.show()


# Q7
# To be run in the terminal:
pip install scikit-learn

import sklearn
print("Scikit-learn Version:", sklearn.__version__)


# Q8
name = input("Enter your name: ")
print("Hello", name)
print("Welcome to Python Programming!")


# Q9
num1 = 10
num2 = 20
total = num1 + num2
print("First Number:", num1)
print("Second Number:", num2)
print("Sum =", total)


# Q10
# To be run in the terminal:

# Create virtual environment:
python -m venv myenv

# Activate on Windows:
myenv\Scripts\activate

# Install required libraries:
pip install numpy pandas matplotlib seaborn scikit-learn

# Check installed libraries:
pip list

# Deactivate virtual environment:
deactivate


# Q11
data = pd.read_csv("C:\\Users\\HP\\Downloads\\diabetes.csv")
print(data)


# Q12
print(data.head())


# Q13
print(data.tail())


# Q14
rows, columns = data.shape
print("Total Rows:", rows)
print("Total Columns:", columns)


# Q15
print(data.columns)


# Q16
print(data.dtypes)


# Q17
print(data.describe())


# Q18
data.info()


# Q19
print(data.isnull())


# Q20
print(data.isnull().sum())


# Q21
print(data["Insulin"].unique())


# Q22
print(data["Insulin"].value_counts())


# Q23
data = data.rename(columns={
    "BloodPressure": "Bp",
    "DiabetesPedigreeFunction": "DPF"
})
print(data.columns)


# Q24
result = data.loc[0:4, ["Bp", "Insulin"]]
print(result)


# Q25
result = data.iloc[0:5, 0:2]
print(result)


# Q26
filtered_data_1 = data[(data['Age']>30) & (data['Outcome'] ==1)]
print(filtered_data_1)


# Q27
sorted_data = data.sort_values(by="Age")
print(sorted_data)


# Q28
data = pd.read_csv("sample_data.csv")
data["Status"] = "Active"
print(data)


# Q29
data = pd.read_csv("sample_data.csv")
data = data.drop("Status", axis=1)
print(data)


# Q30
data = data.drop_duplicates()
print(data)


# Q31
data.to_csv("modified_data.csv", index=False)
print("Dataset saved successfully.")


# Q32
from sklearn.datasets import load_iris
iris = load_iris()
print("Feature Data:")
print(iris.data)
print("Target Data:")
print(iris.target)


# Q33
plt.hist(data["Age"], bins=5, edgecolor="black")
plt.title("Histogram of Age")
plt.xlabel("Age")
plt.ylabel("Frequency")
plt.show()


# Q34
plt.scatter(data["Age"], data["Bp"])
plt.title("Relationship between Age and Bp")
plt.xlabel("Age")
plt.ylabel("Bp")
plt.show()


# Q35
data = pd.read_csv("sample_data.csv")
correlation = data.select_dtypes(include="number").corr()
sns.heatmap(correlation, annot=True, cmap="coolwarm")
plt.title("Correlation Heatmap")
plt.show()
