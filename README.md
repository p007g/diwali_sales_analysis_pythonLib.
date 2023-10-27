# Python_Diwali_Sales_Analysis
Python project for beginners- Analyze Diwali sales data to improve customer experience and sales

Step by Step process------

#1 - We have imported all python libraries we need such as numpy, pandas, matplotlib and seaborn.
*********
import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt # visualizing data
%matplotlib inline
import seaborn as sns

#2 - We read or extract the Diwali_Sales_Analysis csv data into the interpreter.
**********
df = pd.read_csv('Diwali Sales Data.csv', encoding= 'unicode_escape')

#3 ----- Now the process begin for Data Cleaning-----

    @1-- See and read the data structure, pattern, types of columns etc. by using such following commands-->
    ********df.shape, 
    ********df.head(), 
    ********df.info() etc.

    @2-- we have to delete unrelated/blank columns from the data.
    ********df.drop(['Status', 'unnamed1'], axis=1, inplace=True)

    @3-- check for null values for all columns and delete it
    *******pd.isnull(df).sum()
    *******df.dropna(inplace=True)

    @4-- change and observe the data type-amount columns-from float to int.
    *******df['Amount'] = df['Amount'].astype('int')

    @5-- when to describe the data-it generates mean, sum, max, min and other numeric function
    *******df.describe()

    @6-- describing for specific columns
    ********df[['Age', 'Orders', 'Amount']].describe()

#4 ----- Process of Data Visualization-----

    @1-- Plotting a graph between nos. of gender
    ******ax = sns.countplot(x = 'Gender', data = df)
            for bars in ax.containers:
            ax.bar_label(bars)