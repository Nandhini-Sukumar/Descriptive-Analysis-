                                                                   # Descriptive-Analysis-
Descriptive Analysis or statistice is the first and important step after the cleaning process... This is the common steps to findout the features of the data present inside the dataset. In Descriptive Statistics, Measures of Central Tendency is the main concept inside of this topic it is having mean,median and mode. Mean which means Average of the data, Median is define the middle value of the dataset and finally mode it represent the repetation the value from the dataset. We can also see the important statistics basics varience,Standard Deviation,minimum and maximum using python.

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# This Dataset contains only the numerical values:

Data = pd.read_csv("C:/Users/SasiKumar/Documents/winequality_white.csv")
Data.head()

# Counts of column
_( This sum function is used to findout the counts of data from base on each column)

Data.sum().to_frame()

# Mean value for each column
_(Mean function is used to findout the average value)

Data.mean().to_frame()

# Median Value for each column

Data.median().to_frame()

# Mode Value for each column

Data.mode()

# Maximum value of the columns

Data.max().to_frame()

# Minimum value of each column

Data.min().to_frame()

# Findout the Range of the column

max(Data['quality']) - min(Data['quality'])

# Quantile function

Data.quantile(0.25)

# Describe Function

Data.describe()
