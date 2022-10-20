
# Basics

## Importing from a CSV  

```python
import pandas as pd

# import the data from the .csv file into a pandas dataframe
quakes = pd.read_csv("depress_dataset.tsv", sep='\t')
# Print out the first 5 rows of the dataset
print(quakes.head(5))
```
![](../out1.png)

## Using the df.info() function
The df.info() function shows the columns, the number of non-null values for each column, the datatypes for each column, and the memory usage for the dataframe.

```python
print(quakes.info())
```
![](../out2.png)

## Dealing with NA values   
For this section, we will work with a new dataset.   

```python
print(df.info())
```
![](../out3.png)

There are several ways to deal with NA values. One way is to simply ignore all rows that contain NA's. This is done using the df.dropna() function. Without the inplace argument, it returns a new dataframe. With the inplace argument, it modifies the existing dataframe.

```python
df.dropna()
print(df.info(inplace=True))
```
![](../out4.png)

We can also replace empty values with another value (one we come up with, or a computed value). The code below fills all na values in the "Calories" column with the mean value of all the calories (ignoring na's). 

```python
x = df["Calories"].mean()
df["Calories"].fillna(x, inplace=True)
print(df.info())
```

![](../out5.png)


<style>
   img{
       width: 350px;
   }
</style>




