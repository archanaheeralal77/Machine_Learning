 Adv about:srcdoc
  import pandas as pd
from pandas import *
data = pd.read_csv("Advertising.csv") data
       ID
0 1 230.1
1 2 44.5 2 3 17.2 3 4 151.5 4 5 180.8
... ... ... 195 196 38.2 196 197 94.2 197 198 177.0 198 199 283.6 199 200 232.1
TV Radio Newspaper Sales
 37.8 69.2 22.1 39.3 45.1 10.4 45.9 69.3 9.3 41.3 58.5 18.5 10.8 58.4 12.9
... ... ... 3.7 13.8 7.6 4.9 8.1 9.7 9.3 6.4 12.8
42.0 66.2 25.5 8.6 8.7 13.4
200 rows × 5 columns
data = pd.read_csv("Advertising.csv", index_col=0) data
    1 of 6 13/06/24, 4:27 pm

 Adv about:srcdoc
 TV Radio Newspaper Sales ID
 1 2 3 4 5
... 196 197 198 199 200
230.1 37.8 44.5 39.3 17.2 45.9 151.5 41.3 180.8 10.8 ... ... 38.2 3.7 94.2 4.9 177.0 9.3 283.6 42.0 232.1 8.6
69.2 22.1 45.1 10.4 69.3 9.3 58.5 18.5 58.4 12.9 ... ... 13.8 7.6 8.1 9.7 6.4 12.8 66.2 25.5 8.7 13.4
200 rows × 4 columns
 data.head()
TV Radio Newspaper Sales
 ID 1 2 3 4 5
230.1 37.8 44.5 39.3 17.2 45.9 151.5 41.3 180.8 10.8
69.2 22.1 45.1 10.4 69.3 9.3 58.5 18.5 58.4 12.9
  data
 2 of 6 13/06/24, 4:27 pm

 Adv about:srcdoc
 TV Radio Newspaper Sales ID
 1 2 3 4 5
... 196 197 198 199 200
230.1 37.8 44.5 39.3 17.2 45.9 151.5 41.3 180.8 10.8 ... ... 38.2 3.7 94.2 4.9 177.0 9.3 283.6 42.0 232.1 8.6
69.2 22.1 45.1 10.4 69.3 9.3 58.5 18.5 58.4 12.9 ... ... 13.8 7.6 8.1 9.7 6.4 12.8 66.2 25.5 8.7 13.4
200 rows × 4 columns
   #Import libraries for plotting
import seaborn as sns %matplotlib inline
  # pairplot your data x&y
sns.pairplot(data,x_vars=['TV','Radio','Newspaper'], y_vars='Sales') <seaborn.axisgrid.PairGrid at 0x17d80a210>
     # Extract the features in to x
features_cols = ['TV', 'Radio', 'Newspaper']
#### x = data[['TV', 'Radio', 'Newspaper']] this will have the same resuld
# and they both mean same. so either 1 can be used in python code.
 3 of 6 13/06/24, 4:27 pm

 Adv about:srcdoc
  x= data[features_cols] x
TV Radio Newspaper ID
    1 2 3 4 5
... 196 197 198 199 200
230.1 37.8 69.2 44.5 39.3 45.1 17.2 45.9 69.3 151.5 41.3 58.5 180.8 10.8 58.4 ... ... ... 38.2 3.7 13.8 94.2 4.9 8.1 177.0 9.3 6.4 283.6 42.0 66.2 232.1 8.6 8.7
200 rows × 3 columns
x.head()
TV Radio Newspaper
  ID 1 2 3 4 5
y
230.1 37.8 69.2 44.5 39.3 45.1 17.2 45.9 69.3 151.5 41.3 58.5 180.8 10.8 58.4
    # extract the result/response/dependent variable into y
y = data['Sales']
   4 of 6 13/06/24, 4:27 pm

 Adv about:srcdoc
  ID
 1      22.1
 2      10.4
 3       9.3
 4      18.5
 5      12.9
        ...
 196     7.6
 197     9.7
 198    12.8
 199    25.5
 200    13.4
Name: Sales, Length: 200, dtype: float64 y.head()
 ID
 1    22.1
 2    10.4
 3     9.3
 4    18.5
 5    12.9
 Name: Sales, dtype: float64
x_train, x_test, y_train, y_test = train_test_split(x,y,random_state=1) print(x_train.shape)
(150, 3)
print(y_train.shape) (150,)
print(x_test.shape) (50, 3)
print(y_test.shape) (50,)
     # import libraries to split data into test and train data
from sklearn.model_selection import train_test_split
              ### Now perform linear regression, so to do that import libraries
from sklearn.linear_model import LinearRegression
 5 of 6 13/06/24, 4:27 pm

 Adv about:srcdoc
  lr = LinearRegression() lr.fit(x_train, y_train)
print(lr.intercept_) 2.87696662231793
print(lr.coef_)
[0.04656457 0.17915812 0.00345046]
    ▾ LinearRegression i ? LinearRegression()
       6 of 6 13/06/24, 4:27 pm
