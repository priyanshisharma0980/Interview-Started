### Why did you choose Python for this analysis?
Pandas simplifies data manipulation, 
NumPy handles numerical operations efficiently, and 
libraries like Seaborn and Matplotlib make visualization easy.

### data is imported in data frame
data = pd.read_csv("adult.csv",na_values=['?'])
data

### Know column names
data.info() - it will give me all the column names

### to replace ? value with NaN
df.replace('?', np.nan, inplace= True)

### inplace = TRUE meaning-
The operation modifies the original DataFrame 

### To check the null values in data
data.isnull().sum()

### to drop null values-
df.dropna(inplace=True)

### to drop nulll values from only specified columns-
df.dropna(subset=['workclass', 'occupation', 'native-country'], inplace=True)

### DEAL with missing data
1. Imputation methods involves replacing missing values with estimated values. We replace NaN values by fillna() of mean, mode and median

eg- df['Marks'].fillna(df['Marks'].mean())  
Works well with numerical data  

2.  Forward and Backward Fill

Forward and backward fill techniques are used to replace missing values by filling them with the nearest non-missing values from the same column.  
df['Marks'].fillna(method='ffill') - It replaces missing values with the last observed non-missing value in the column.  same method='bfill  


### to delete column
df.drop('fnlwgt', axis=1, inplace=True)

### This together will give sum of NaN in each column -
df.replace('?', np.nan, inplace= True)
df.isnull().sum()


### top 5 and last 5
data.head(5)
data.tail(5)

### to check total number of rows and columns
df.shape

### to check if data is categorical or numerical
df['column name'].unique

### if categorical data and I want to know value for each category
df['marital-status'].value_counts()

### To get mean std min 25%, 75%, 50%, max count
df.describe()
it will only show numerical valuesss

If we want to include ALL data
df.describe(include='all')

### We will compare values like MEAN and MEDIAN(50 percentile) and TOP
### AGE-
In Age column mean and media are almost same, meaning less outliers


### iloc performs selection by integer position loc Uses row and column names 


### OUTLIERS - 
data points that significantly deviate from the overall pattern or majority of a dataset, often appearing as exceptionally high or low values. 


### how you handled such large data 
Since the dataset was large, I avoided row-by-row processing. I worked on entire columns using Pandas functions, reduced data size by removing unused columns, and optimized data types to make 
the processing faster and more efficient. 
I used Pandas built-in functions for calculations and avoided creating too many temporary DataFrames, which helped the code run faster.


### Difference between list, tuple, and NumPy array?
Lists: Flexible, slower for numerical operations, hetrogeneous
Tuples: Immutable
NumPy arrays: Faster, memory-efficient, support vectorized operations, Homogeneous (stores elements of the same data type only)



### What is broadcasting in NumPy?
Broadcasting allows NumPy to perform operations on arrays of different shapes by automatically expanding dimensions without copying data.


### how to get data from jupyter notebook to powerBI

from powerbiclient import quickvisualise, dataset config, report



### to check for outliers
plt.boxplot(data["age"])
plt.show()










