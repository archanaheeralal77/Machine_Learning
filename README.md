**Python Code for Simple Linear Regression**

import pandas as pd

from pandas import *

data = pd.read_csv("Advertising.csv") 

data

<img width="341" alt="Screenshot 2024-06-13 at 4 38 15 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/66a0487a-4159-4a0b-ad6b-de0325361591">

# As There is a col which has blank name so it is not important so we can remove

data = pd.read_csv("Advertising.csv", index_col=0) 

data

<img width="288" alt="Screenshot 2024-06-13 at 4 41 59 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/37c3bf4e-ae84-47c3-aa03-77e8c6682688">

data.head()

<img width="264" alt="Screenshot 2024-06-13 at 4 42 57 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/fdb2eb6b-62d3-4875-b77d-a63fd7040cb3">

data

<img width="288" alt="Screenshot 2024-06-13 at 4 43 47 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/4f1535a3-8618-4885-b690-21bdf274d33c">

#Import libraries for plotting

import seaborn as sns 
%matplotlib inline

# pairplot your data x&y

sns.pairplot(data,x_vars=['TV','Radio','Newspaper'], y_vars='Sales')


<img width="614" alt="Screenshot 2024-06-13 at 4 45 28 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/609e6623-051a-41a3-ad9d-2610446dd388">

# Extract the features in to x

features_cols = ['TV', 'Radio', 'Newspaper']

#### x = data[['TV', 'Radio', 'Newspaper']] this will have the same resuld
# and they both mean same. so either 1 can be used in python code.

x= data[features_cols]

x

<img width="232" alt="Screenshot 2024-06-13 at 4 46 42 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/98eebfa9-2d7a-4c93-b232-8be1fa9ecad6">


x.head()

<img width="224" alt="Screenshot 2024-06-13 at 4 47 57 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/2d1b9d3e-e9bb-4561-a7c3-e8fb8270194a">


# extract the result/response/dependent variable into y

y = data['Sales']


y 

<img width="338" alt="Screenshot 2024-06-13 at 4 48 54 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/b3ca4bb3-56d0-41ed-a45c-2f22c47bf833">

y.head()

<img width="248" alt="Screenshot 2024-06-13 at 4 49 39 PM" src="https://github.com/archanaheeralal77/Machine_Learning/assets/127080874/cc33adeb-7c1c-4474-bccc-623a8d93a743">

# import libraries to split data into test and train data

from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(x,y,random_state=1) print(x_train.shape)

(150, 3)

print(y_train.shape) 

(150,)

print(x_test.shape) 

(50, 3)

print(y_test.shape) 

(50,)

### Now perform linear regression, so to do that import libraries

from sklearn.linear_model import LinearRegression

lr = LinearRegression() 

lr.fit(x_train, y_train)

▾ LinearRegression i ? LinearRegression()

print(lr.intercept_) 

2.87696662231793

print(lr.coef_)

[0.04656457 0.17915812 0.00345046]



