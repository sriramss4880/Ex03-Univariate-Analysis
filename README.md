# Ex03-Univariate-Analysis
# Aim:
To read the given data and perform the univariate analysis with different types of plots.

# Explanation:
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

# Algorithm:
# Step 1:
Read the given data.

# Step 2:
Get the information about the data.

# Step 3:
Remove the null values from the data.

# Step 4:
Mention the datatypes from the data.

# Step 5:
Count the values from the data.

# Step 6:
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program:

Name : G.TEJASWINI
Reg no : 212222230157

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df=pd.read_csv("/content/iris (1).csv")

df.nunique()
```

<img width="80" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/62991833-a8c7-475b-b183-238b7813cd69">

```
df.head()
```

<img width="267" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/759b4aa5-f438-4246-a188-b6695267025f">

```
df.tail()
```
<img width="272" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/ea53ca8f-2e31-456e-961a-50d221b26876">

```
df.iloc[:,4].value_counts()
```
<img width="116" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/a3020eca-4180-449d-b6c2-e2c67d12c0ba">

```
for i in range(0,df.shape[1]):
  print("-----------",df.columns[i],"------------")
  print(df.iloc[:,i].value_counts())
  print("---------------------------------------")
```
<img width="169" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/8d85e5de-da76-425e-9215-64d44eabfc53">
<img width="175" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/7ff41a1e-dbe7-49f4-bae1-d231806e977c">
<img width="175" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/09c05bae-c232-4af7-a318-3459037a3f7c">
<img width="186" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/85cd79df-04a6-4896-8832-211fded9e194">

```
sns.countplot(x='species',data=df)
```
<img width="297" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/1dd544a8-c22f-40d5-b663-19b7c6d27b24">

```
dfv=df.loc[df['species']=='virginica']

plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'*')
plt.xlabel('sepal length')
plt.show()
##plt.plot(df_setosa['sepal_length'],np.zeros_like(df_setosa['sepal_length']),'o')
```
<img width="225" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/011bc3e2-773f-4ea1-92a9-ff2a041b6253">

```
dfs=df.loc[df['species']=='setosa']
dfc=df.loc[df['species']=='versicolor']

plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
```
<img width="222" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/48c2b7c0-8e49-4033-b7dd-d385c9ef5532">

```
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
plt.xlabel('petal_length')
plt.show()
```
<img width="223" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/62be360e-b61c-4746-aeab-2e672bd5cfae">

```
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'+')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'-')
plt.xlabel('SEPALLENGTH')
plt.show()
```
<img width="219" alt="image" src="https://github.com/TejaswiniGugananthan/Ex03-Univariate-Analysis/assets/121222763/88fb091c-9617-466f-af3a-c91b087d3c00">

# Result:
The given datasets are read and outliers are detected and are removed using IQR and z-score methods.
