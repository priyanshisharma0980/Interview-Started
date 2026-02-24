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
Broadcasting in NumPy is the ability of NumPy to perform arithmetic operations on arrays of different shapes and sizes without explicitly replicating the data.




### how to get data from jupyter notebook to powerBI

from powerbiclient import quickvisualise, dataset config, report



### to check for outliers
plt.boxplot(data["age"])
plt.show()

### IQR
Q3 - Q1
Inter Quartile range
Used to show the spread of data and identifying outliers
Also called whisker plot because has upper and lower whisker
Upper whisker - (Q3 + 1.5 * IQR). 
Lower whisker - (Q1 - 1.5 * IQR). 

The middle line in box plot is - Median


### NUMPY functions
Numpy.array
np.zeros((3,4)) #Create an array of zeros
np.save('my_array' , a)
np.subtract()
np.transpose()
>>>h.resize((2,6)) #Return a new arraywith shape(2,6)
>>> np.append(h,g) #Append items to an array
>>> np.insert(a,1,5)  #Insert items in an array
>>> np.delete(a,[1])  #Delete items from an array
np.linspace() - generate an array of evenly spaced values between two specified numbers.


### 10. What are some common data types supported by NumPy?
int
float
complex
bool
object
datetime

### How can you concatenate two NumPy arrays vertically?
We can use vstack OR
array= np.concatenate((array1, array2), axis=0)

### Convert a multidimensional array to 1D array.
one_dimensional_array = multidimensional_array.flatten()


### How can you identify outliers in a NumPy array?
import numpy as np

arr = np.array([10, 12, 12, 13, 12, 11, 300, 14, 13, 12])

# Calculate Q1 (25th percentile) and Q3 (75th percentile)
Q1 = np.percentile(arr, 25)
Q3 = np.percentile(arr, 75)
IQR = Q3 - Q1
Define bounds
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
Identify outliers
outliers = arr[(arr < lower_bound) | (arr > upper_bound)]

print("Outliers:", outliers)




































