---
title: "Practical session"
teaching: 10
exercises: 120
questions:
- "Q1"
objectives:
- "Applying theory to practical problems"

keypoints:
- "Solving problems with R and RStudio will improve your skills and confidence"
---


## Set up a new project.

Create a new project and new script. Add a data folder to the project and place the gapminder_data.csv in the data folder. Load the gapminder_data.csv into R.


### Inspect the data.

Find:
1. The number of records in the data set.
2. The number of attributes for a record.
3. The column names.
4. The data type of each attribute 
5. What are the values for the last record in the dataset.

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


### Include flow control

1. Use an **if()** statement to print a suitable message reporting whether there are any records from 2002 in the gapminder dataset.

Hint: It is not essential but you might find ?any() helpful.






