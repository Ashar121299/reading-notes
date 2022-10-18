## 10 minutes to pandas

we can import pandas library as :

_*import pandas as pd*_

### Object creation

Creating a Series by passing a list of values, letting pandas create a default integer index:
s = pd.Series([1, 3, 5, np.nan, 6, 8])

### Viewing data
use _*DataFrame.head()*_ and _*DataFrame.tail()*_ to view the top and bottom rows of the frame respectively

### Selection

#### Getting

1. Selecting a single column called A, which yields a Series, equivalent to df.A //df["A"]

2.Selecting via [] (__getitem__), which slices the rows //df[0:3]


#### Selection by label

1. using DataFrame.loc() or DataFrame.at().For getting a cross section using a label. //df.loc[dates[0]]
 
2.can Selecting on a multi-axis by label. //df.loc[:, ["A", "B"]]

3.Showing label slicing, //df.loc["20130102":"20130104", ["A", "B"]]

4.both endpoints are included. // df.loc["20130102", ["A", "B"]]

5.getting a scalar value. //df.loc[dates[0], "A"]

6.getting fast access to a scalar (equivalent to the prior method).//df.at[dates[0], "A"]

#### Selection by position

1. Select via the position of the passed integers //df.iloc[3]
 
2. By integer slices, acting similar to NumPy/Python. //df.iloc[3:5, 0:2]

3.By lists of integer position locations, similar to the NumPy/Python style. //df.iloc[[1, 2, 4], [0, 2]]

4. For slicing rows explicitly. //df.iloc[1:3, :]

5.For slicing columns explicitly. //df.iloc[:, 1:3]

6.getting a value explicitly. //df.iloc[1, 1]

7.For getting fast access to a scalar (equivalent to the prior method). //df.iat[1, 1]


#### Boolean indexing

1. single column’s values to select data. //df[df["A"] > 0]

2. Selecting values from a DataFrame where a boolean condition is met. //df[df > 0]

3.Using the isin() method for filtering

#### Setting

1. Setting a new column automatically aligns the data by the indexes. //s1 = pd.Series([1, 2, 3, 4, 5, 6], index=pd.date_range("20130102", periods=6))

2.Setting values by label. //df.at[dates[0], "A"] = 0

3.Setting values by position.//df.iat[0, 1] = 0

4.Setting by assigning with a NumPy array.//df.loc[:, "D"] = np.array([5] * len(df))

### Missing data

_*pandas primarily uses the value np.nan to represent missing data. It is by default not included in computations.*_

### Operations

Operations in general exclude missing data.

#### Stats

Performing a descriptive statistic.//df.mean().

#### Apply

DataFrame.apply() applies a user defined function to the data.//df.apply(np.cumsum).

#### String Methods

Series is equipped with a set of string processing methods in the str attribute that make it easy to operate on each element of the array, 
as in the code snippet below. Note that pattern-matching in str generally uses regular expressions by default (and in some cases always uses them)

### Merge

#### concat 

pandas provides various facilities for easily combining together Series and DataFrame objects with various kinds of set logic for the indexes
and relational algebra functionality in the case of join / merge-type operations.


Concatenating pandas objects together along an axis with concat()://df = pd.DataFrame(np.random.randn(10, 4))

#### join 

merge() enables SQL style join types along specific columns.

### Grouping

By “group by” we are referring to a process involving one or more of the following steps:

Splitting the data into groups based on some criteria

Applying a function to each group independently

Combining the results into a data structure


### Reshaping
1.Stack
The stack() method “compresses” a level in the DataFrame’s columns.

2.Pivot tables
pivot_table() pivots a DataFrame specifying the values, index and columns.


### Categoricals

pandas can include categorical data in a DataFrame:

1.Converting the raw grades to a categorical data type.

2.Rename the categories to more meaningful names.

3.Reorder the categories and simultaneously add the missing categories (methods under Series.cat() return a new Series by default).

4.Sorting is per order in the categories, not lexical order.

5.Grouping by a categorical column also shows empty categories.


### Plotting 

We use the standard convention for referencing the matplotlib API: 

import matplotlib.pyplot as plt
plt.close("all")

The plt.close method is used to close a figure window

### Importing and exporting data

#### CSV

1. Writing to a csv file: using DataFrame.to_csv()
df.to_csv("foo.csv")

2. Reading from a csv file: using read_csv()
pd.read_csv("foo.csv")

#### HDF5

1.Writing to a HDF5 Store using DataFrame.to_hdf():
df.to_hdf("foo.h5", "df")

2.Reading from a HDF5 Store using read_hdf():
pd.read_hdf("foo.h5", "df")

#### Excel

1.Writing to an excel file using DataFrame.to_excel():
df.to_excel("foo.xlsx", sheet_name="Sheet1")

2.Reading from an excel file using read_excel():
pd.read_excel("foo.xlsx", "Sheet1", index_col=None, na_values=["NA"]) 
