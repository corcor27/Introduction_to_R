---
title: "Manipulating data frames"
teaching: 20
exercises: 10
questions:
- "How do I access the data stored in data frames?"
objectives:
- "Understand the fundemetnals of addressing data frames."
keypoints:
- "The complexity of the process is related to the complexity of the conditions for retrieving the data you want. "
---

## Datasets

In R, there are several built-in datasets and many more available in various packages. To access any of these datasets, you can simply use:

```
iris
``` 
{: .language.r}

```
Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
1            5.1         3.5          1.4         0.2     setosa
2            4.9         3.0          1.4         0.2     setosa
...
149          6.2         3.4          5.4         2.3  virginica
150          5.9         3.0          5.1         1.8  virginica
```
{: .output}

Additionally, you can use the data() function to load any built-in dataset into your R session.

```
data(iris)
``` 
{: .language.r}

You will now be able to view the iris dataset in your environment pane (selecting it will open it as a file in your script pane).

We first want to explore what high-level information RStudio can give us about the iris dataset.

```
str(iris)
``` 
{: .language.r}

``` 
'data.frame':	150 obs. of  5 variables:
 $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
 $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
 $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
 $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
 $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...
```
{: .output}

From the output, you can see that the iris dataset has 150 observations and 5 variables. The variables include numeric variables (Sepal.Length, Sepal.Width, Petal.Length, Petal.Width) and a factor variable (Species). The factor variable Species has three levels: "setosa", "versicolor", and "virginica". Additionally, it shows the first few observations of the dataset.

```
summary(iris)
``` 
{: .language.r}

``` 
Sepal.Length    Sepal.Width     Petal.Length    Petal.Width          Species  
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100   setosa    :50  
 1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300   versicolor:50  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300   virginica :50  
 Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199                  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800                  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500
```
{: .output}

The summary() function in this case, provides:

* Minimum: The minimum value of the variable.
* 1st Quartile (Q1): The value below which 25% of the data fall.
* Median (Q2): The middle value of the variable, where 50% of the data fall below and 50% fall above.
* Mean: The average value of the variable.
* 3rd Quartile (Q3): The value below which 75% of the data fall.
* Maximum: The maximum value of the variable.
* The frequency count of each level for a factor.

```
dim(iris)
``` 
{: .language.r}

``` 
150 5
```
{: .output}

The dim() fuctions provides the dimensions of the dataset. 150 rows, 5 columns.

Next we can look at the data in more detail. Type but do not press enter:

```
iris$
``` 
{: .language.r}

You should see an autocomplete option panel for every column name in the dataset. Select one and press enter. This will show you all the content from this column.

There are several subtly different ways to call variables, observations, and elements from data frames. Try all of these:

```
iris [3]
``` 
{: .language.r}

Returns a dataframe with just column 3.

```
iris [[3]]
``` 
{: .language.r}

Returns the contents of column 3.

```
iris$Sepal.Length
``` 
{: .language.r}

Returns the contents of column 3. ($ operator is used to extract variables)

```
iris [3, 3]
``` 
{: .language.r}

The syntax iris \[row_index, column_index\]. So this returns the item in the 3rd row and in the 3rd column.

```
iris [, r]
``` 
{: .language.r}

Returns the contents of column 3.

```
iris [3, ]
``` 
{: .language.r}

Returns the contents of row 3.

Be clear that calling columns will be return vectors and calling rows will return lists.

### Adding and removing columns and rows

***Add column***  
We know that columns are vectors so we can generate a new vector and add it to our dataset:
```
num_petals <- rep(4, 150) # we are assuming all the flowers have four petals for the sake of this example 
``` 
{: .language.r} 
```
iris <- cbind(iris, num_petals)
``` 
{: .language.r} 

>Note:  
>If you try and inspect the data in output in the console you may get a warning that you have reached your max.print and rows have been omitted. 
>You can change this if you wish using:

```
options(max.print = n) # n being the number of elements to print
``` 
{: .language.r} 

***Remove column***

To remove the column, we want to provide the index of the column we want to remove (you can think of it as we are asking for all the columns, minus the specified column.)
```
iris <- iris[,-6] # remove the pointless column we just added
``` 
{: .language.r} 


***Add row***  
Remember, rows are lists, so we need to generate a new list that matches our dataset. 
```
new_row <- list(5.4, 3.2, 4.9, 1.9, "setosa")
``` 
{: .language.r} 

```
iris <- rbind(iris, new_row)
``` 
{: .language.r} 


***Remove row***  
Removing rows is very similar to removing columns:

```
iris <- iris[-151,]
``` 
{: .language.r} 

Note: If you have added multiple new rows, you can also pass in a vector of rows to be removed (e.g., iris[-c(151:153),])

### Subsetting data frames
Now we will consider more complicated selections of the data. We have seen that we can pass a vector into the index selection of our data frame (e.g., -c(151:153) ). We can use what we know about vectors to make some interesting selections:

```
iris[c(1,2,1,3,1,4)]
``` 
{: .language.r} 

``` 
		Sepal.Length Sepal.Width Sepal.Length.1 Petal.Length Sepal.Length.2 Petal.Width
1            5.1         3.5            5.1          1.4            5.1         0.2
2            4.9         3.0            4.9          1.4            4.9         0.2
...
```
{: .output}


```
iris[2:4]
``` 
{: .language.r} 

``` 
		Sepal.Width Petal.Length Petal.Width
1           3.5          1.4         0.2
2           3.0          1.4         0.2
...
```
{: .output}

```
iris[-(2:4)]
``` 
{: .language.r} 

``` 
	Sepal.Length    Species
1            5.1     setosa
2            4.9     setosa
...
```
{: .output}

Note that we are not using ‘iris <-‘ before our commands so we are not changing the original structure. We could be creating subsets of our data if we were assigning it to a new variable (e.g., subset_iris <- iris\[2:4\]).

### Subsetting by name

We have been selecting by index up until this point. However, indexes can change if we manipulate a data frame. Column names will not change. Try:

```
iris[c("Sepal.Length","Sepal.Width")]
```
{: .language.r} 

Using names to index requires us to use a different syntax than indexing with numbers (think back to data types and their operations, Sepal.Length":"Sepal.Width does not make sense). If we combine that with our understanding of how logical operators worked, we have the building blocks for how we are going to address a data frame using column names.

To provide some clarity, type:

```
iris[c(FALSE, TRUE, FALSE, TRUE, TRUE, FALSE)]
```
{: .language.r} 

``` 
    Sepal.Width Petal.Width    Species
1           3.5         0.2     setosa
2           3.0         0.2     setosa
...
```
{: .output}


This is indexing with logical operators. We can use a new operator that we have not looked at yet **'%in%'**. This operator is used to check if elements in one vector are present in another vector. It returns a logical vector indicating whether each element of the first vector is found in the second vector. 

```
iris[, ! names(iris) %in% c(“Sepal.Length”, "Sepal.Width")] # notice the negation
```
{: .language.r} 

``` 
    Petal.Length Petal.Width    Species
1            1.4         0.2     setosa
2            1.4         0.2     setosa
...
```
{: .output}

With this we will get all columns not in the list.

### Many more options

The complexity of subsetting data is going to depend on the task at hand. The scope of this session does not allow us to explore all eventualities but should give you a base understanding of how to effectively subset your data. There are also packages designed specifically for manipulating data frames (e.g.,plyr, dplyr and tidyr). Allthough it is possible to achieve similar results using base R functions, these packages provide a more efficient and convenient way to work with data, especially for tasks involving data manipulation, summarization, and reshaping. 