---
title: "Variables and assignment"
author: "Colin Sauze, Ed Bennett, Jarno Rantaharju, Thomas Green"
teaching: 15
exercises: 5
questions:
 - "What can we store in variables?"
 - "What is good practice for variable naming?"
 - "What can I do with variables?"
objectives:
 - "Confident assigning variables"
 - "Understand different data types"
keypoints:
 - "When naming variables it's important be consistent and succinct"
 - "Output assignment has to be explicit to keep the result of an operation"
 - "Different data types can require different operations"
 - "R will make assumptions about data types unless you are explicit"
---

### What are variables and why do we want them?
We don’t just want RStudio to be our calculator. We want to be able to store and manipulate data in a meaningful way. We want to perform operations on data, possibly many times. It would be useful to have a clarity and context for the data we are using; ideally descriptive names to make our data more manageable.

### Data types 
R utilises different data types to efficiently store and manipulate different kinds of data. R is dynamical typed; this means that you do not need to specify a data type when you declare a variable. You can give the variable name and the data you want to store and let R worry about how it deals with that. We will look at the most common data types in R.
  
Data type | Example
------------ | -------------
Numeric | integers (0, 5, 102) & doubles (0.75, 5.17, 102.6)
Character | "Hello"
Logical | TRUE/FALSE
Factor | (small, medium, large)
  
>***Factor:***
> We are not going to explore factors in this section but we will introduce them.
> Factors are used to represent categorical data, which consists of a fixed number of distinct levels (categories).Factors are particularly useful for representing nominal (e.g., married, single, divorced) or ordinal data (e.g., small, medium, large).
  
### Defining variables
Let's go ahead and define some variables. Into the console type:  

```
x <- 10
```
{: .language-r}  

```
y = 5
```
{: .language-r}  


The variables x and y should now have populated your environment screen. We can inspect them, but they are relatively predictable. 

>## Syntax note
> ***Multiple ways to assign***  
>You may notice we used two different ways to define variables. The convention in R is to use ‘<-‘. In most other languages ‘=’ is the convention. They are interchangeable in R, but it is best practice to use ‘<-‘. From now on we will only use '<-' but be aware you might see '=' assignment  in other sources. 
{: .callout}

{% include figure.html max-width="100%" file="/fig/environmentVars.png" 
alt="RStudio environment pane showing newly declared variables" caption="Figure 1: RStudio environment pane showing newly declared variables" %}  



### Declare more variables:
Let's add a few other variables of different variable types, Try:

```
my_name <- "your name"
```
{: .language-r}

```
likes_rstudio <- TRUE
```
{: .language-r}
  

Now we have created some variables we can try refering to them in the console. Type:  

```
x + 5
```
{: .language-r}

```
15
```
{: .output}


> ## What does the environment say about variable x?
> You should notice that the variable 'x' has not changed it's value to 15.
{: .challenge}

Now try:
```
x <- x + 5
```
{: .language-r}

When you check the variable again in the environment tab you should now notice that it is 15. This is a key concept to recognise; we can perform an operation and the resulting output will be shown but unless we explicitly assign it the change will not be saved.

Now try:
```
sqrt(x)
```
{: .language-r}

```
3.872983
```
{: .output}

Again, you should notice that the variable x is unchanged in the environment pane. That is because R is (*in almost all cases*) **"pass by value"**. This means whatever changes made within the body of the function, stay inside the body of the function. The argument you pass into the function will be unmodified outside of the function.

## Variable naming

Variable naming is important but often overlooked by new programmers (and experienced programmers). It is not trivial to think of meaningful concise variable names. The first thing to understand is that R has some restrictions and rules for variable naming:  

 
* Variable names are cases sensitive (My_name is different to my_name).  

* They must start with a letter or a period. 

* They can consist of letters, numbers, periods, and underscores.  

* There are reserved words (e.g., ‘else’, ‘for’) that cannot be used for naming variables as they are already used by R for specific purposes.  

 
It may seem fussy but there are actually not that many enforced restrictions compared to the number of variable naming combinations. However, just because you can, doesn’t mean you should. There exist several naming conventions in the R community to help provide structure and guidance to variable naming. 

 

1. my_variable (underscore) 

2. myVariable (camel case) 

3. my.variable  (period)  

 

Although some may disagree with us, we believe for most users it does not matter which convention you pick. There are two key principles for variable naming, that we recommend, that should make your life easier: 

 

1. ***Consistency*** – pick a convention and stick with it. 

2. ***Succinctness*** - Keep variable names short, readable, and descriptive. 

 

For ***example***, if you wanted a variable name for a temperature reading taken in Aberystwyth: 


This: 

>min_temp_aber_C 


Is better than this: 

>temp 
 

Or this: 

>themininimumtemperaturerecordedfromaberystwythindegreescelcius 

 
Being consistent, aware of context, and conscious of your variable naming will make reading your code easier and decrease the risk of errors.   

### Working with variables

We have added numeric values together so now lets try combining characters. Try:

```
my_name <- my_name + "your surname"
```
{: .language-r}

```
Error in my_name + "your surname" : 
  non-numeric argument to binary operator
```
{: .output}

This error is telling us that we tried to use a binary operator (+) on a non-numeric argument (my_name + "your surname"). 

We know that we are dealing with characters, in R the '+' is an operator that does not work with characters. For characters we need to use the method paste(). Try:

```
my_name <- paste(my_name, "your surname") 
```
{: .language-r}

When you check the variable in the environment tab you should see that it is updated. It is important to realise that some operators and methods are data type specific.

>## Useful tool
>* ***class()*** and ***typeof()***  
>You can datatype information using class() (for generalised) and typeof() (for secific) about your variables.  
{: .callout}

```
class(x)
```
{: .language-r}

```
"numeric"
```
{: .output}

```
typeof(x)
```
{: .language-r}

```
"double"
```
{: .output}

We find that x is a double. Even though the value 5 is an integer, R stores it as a double to allow for flexibility in calculations. If we run the following lines:

```
a <- 5L
```
{: .language-r}
We can let R know at declaration that we want the value as an integer.

```
x <- as.integer(x)
```
{: .language-r}
We can cast the value to an integer using the R inbuilt function.

In the environment tab you should see that both variables now show as '5L'. If we try again:

```
class(x)
```
{: .language-r}

```
"numeric"
```
{: .output}

```
typeof(x)
```
{: .language-r}

```
"integer"
```

### Summary

Most of the time data types will not be of great concern to you. However, it is worth remembering that when you ask R to read and organise data, unless you are explicitly, you are asking it to make assumptions on the data types. Sometimes those assumptions can be wrong and could lead to unexpected outcomes. We will consider this in more detail later in the course. 

