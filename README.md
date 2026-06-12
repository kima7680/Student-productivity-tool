# Student-productivity-tool
This project is an automation tool designed to streamline repetitive and inefficient tasks in academic environments.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

import requests
import io

# Loading the dataset from a public URL
url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv"
download = requests.get(url).content
iris = pd.read_csv(io.StringIO(download.decode('utf-8')))
X = iris.drop('species', axis = 1)   #iris데이터 셋에서 y값만 뺌.
y = (iris['species'] == 'virginica').astype(np.int16)  #iris species를     , 넘파이의 int16으로 바꿔줌.
print(y)     
