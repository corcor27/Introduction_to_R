---
title: "Practical session"
teaching: 10
exercises: 120
questions:
- "Can you apply the theory to some practical problems?"
objectives:
- "Able to inspect data"
- "Able to create a function"
- "Able to subset data"
- "Able to manipulate data"
- "Able to manipulate flow control"
- "Able to plot simple plots"

keypoints:
- "Solving problems with R and RStudio will improve your skills and confidence"
---
### Set up a new project.
Create a new project and new script. Add a data folder to the project and place the gapminder_data.csv in the data folder. Load the gapminder_data.csv into R. Load the ggplot2 library into your script.

### Inspect the data.

It is important to get an understanding of what is contained in a dataset before you start working with it.

Find:
1. The number of records in the data set.
2. The number of attributes for a record.
3. The column names.
4. The data type of each attribute
5. What are the values for the first 10 records. 
6. What are the values for the last record in the dataset.


### Correct these common subsetting errors.

Please review these tasks and examine the provided code intended to solve them. Be aware, the supplied code contains errors. Can you correct them? Hint: If you are uncertain, attempt to run the code provided and consider any error messages or output it generates.

1. Aim: Extract observations collected for the year 1957

```
gapminder[gapminder$year = 1957,] # incorrect
```
{: .language-r}

2. Aim: Extract all columns except 1 through to 4

```
gapminder[,-1:4] #incorrect
```
{: .language-r}

3. Aim: Extract the rows where the life expectancy is longer the 80 years

```
gapminder[gapminder$lifeExp > 80] #incorrect
```
{: .language-r}

4. Aim: Extract the first row, and the fourth and fifth columns (continent and lifeExp).

```
gapminder[1, 4, 5] #incorrect
```
{: .language-r}

5. Aim: Extract rows that contain information for the years 2002 and 2007 (advanced)

```
gapminder[gapminder$year == 2002 | 2007,] #incorrect
```
{: .language-r}

### More subsetting

1. Why does 

```
gapminder[1:20]
```
{: .language-r}

return an error?

2. Create a new data.frame called gapminder_small that only contains rows 1 through 9 and 19 through 23. You can do this in one or two steps?

3. Selecting elements of a vector that match any of a list of components is a very common data analysis task. For example, the gapminder data set contains country and continent variables, but no information between these two scales. Suppose we want to pull out information from southeast Asia. How do we set up an operation to produce a logical vector that is TRUE for all of the countries in southeast Asia and FALSE otherwise? For this question we would consider Myanmar, Thailand, Cambodia, Vietnam, and Laos as SE Asia. (advanced)

Hint: ?unique() may be helpful here.


### Include flow control

1. Use an **if()** statement to print a suitable message reporting whether there are any records from 2002 in the gapminder dataset.

Hint: It is not essential but you might find ?any() helpful.

2. Modify your code to remove hardcoded variables so that you can provide any year to be checked.

3. Now modify your code so you can check two years at the same time.

### Create a function 

Define a function that calculates and returns the Gross Domestic Product of a nation (GDP * POP) from the data available in the dataset.

Now modify your function so that it returns the GDP as a new column on the data set.

Now modify your function so that if given a country **or** a year it returns just the data for this selection (e.g., You could specify 'Australia' and get back all years for Australia, you could specify '2007' and get all countries in 2007, or you could specify 'Australia' in '2007' and just receive the data for Australia in 2007).


### Add defensive programming

What happens if we pass unexpected values into your function? (Try putting numeric values in as a country or logical value in as a year)

Add some additional checks into your function to make sure that the correct arguments are being passed in. Hint: you could check out ?is.numeric, ?is.character, and ?stopifnot().

### Manipulating data and simple plots

1. Make a new column in the gapminder data frame that contains population in units of millions of people.

2. On a single graph, plot population, in millions, against year, for all countries. Do not worry about identifying which country is which.

3. Repeat the exercise, graphing only for China, India, and Indonesia. Again, do not worry about which is which.

### More plotting

1. Using **ggplot2**, plot a scatter plot of **GDP** against **life expectancy**.

2. Now modify the plot to show how **life expectancy** has changed over **time**.

3. Now colour code to the points to show **continent**.

2. Scatter plot might not be the best option for showing change over time. Change it to a **line plot**. Hint: you probably want to consider a new argument **'group'**.

### Recap & reflect

Consider the material we have covered today: 
* Are all concepts clear?
* Are you confident you could apply them to your data?
* Are there any other tools you feel you need?
* What section did you find the most difficult?
* What content may you need more support with?







