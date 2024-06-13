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




