---
title: "Variables and assignment"
author: "Colin Sauze, Ed Bennett, Jarno Rantaharju, Thomas Green"
teaching: 15
exercises: 10
questions:
 - "What can we store in variables?"
 - "What is good practice for variable naming?"
 - "What can I do with variables?"
objectives:
 - "Confident assigning variables"
 - "Understand different data types"
keypoints:
 - "Variable naming is important be consistent and succinct"
 - "Output assignment has to be explicit to keep the result of an operation"
 - "Different data types can require different operations"
 - "R will make assumptions about data types unless you are explicit"
---


# What are variables and why do we want them?

### Moving on from calculation
we don’t just want RStudio to be our calculator. We want to be able to store and manipulate data in a meaningful way. We want to perform operations on data, possibly many times. It would be useful to have a clarity and context for the data we are using; ideally descriptive names to make our data more manageable.

### Data types 
R utilises different data types to efficiently store and manipulate different kinds of data. We will look at the most common data types in R.

Data type | Example
------------ | -------------
Numeric | 5.4
Character | "Hello"
Logical | TRUE/FALSE
Factor | small, medium, large

>Context: R is dynamical typed; this means that you do not need to specify a data type when you declare a variable. That means you can give the variable name and the data you want to store and let R worry about how it deals with that.  

We can define some variables. Into the console type:

```
x <- 10
```
{: .input}

```
y = 5
```
{: .input}


The variables x and y should now have populated your environment screen. We can inspect them, but they are relatively predictable. You may notice we used two different ways to define variables. The convention in R is to use ‘<-‘. In most other languages ‘=’ is the convention. They are interchangeable in R but it is best practice to use ‘<-‘.

{% include figure.html max-width="100%" file="/fig/environmentVars.png" 
alt="RStudio environment pane showing newly declared variables" caption="Figure 1: RStudio environment pane showing newly declared variables" %}

Try:

```
my_name <- "your name"
```
{: .input}

```
likes_rstudo <- TRUE
```
{: .input}


Now we have created variables we can now refer to them in the console. Type:

```
x + 5
```
{: .input}

```
15
```
{: .output}


> ## What does the environment say about variable x?
> You should notice that the variable has not changed it's value to 15.
{: .challenge}

Now try:
```
x <- x + 5
```
{: .input}

When you check the variable again in the environment tab you should now notice that it is 15. This is a key concept to recognise; we can perform an operation and the resulting output will be shown but unless we explicitly assign it the change will not be saved.

## Variable naming

Variable naming is important but often overlooked by new programmers (and experienced programmers). It is not trivial to think of meaningful concise variable names. The first thing to understand is that R has some restrictions and rules for variable naming:  

 
* Variable names are cases sensitive.  

* They must start with a letter or a period. 

* They can consist of letters, numbers, periods, and underscores.  

* There are reserved words (e.g., ‘else’, ‘for’) that cannot be used for naming variables as they are already used by R for specific purposes.  

 
It may seem fussy but in the grand scheme there are not that many enforce restrictions compared to the possible combinations of what you can name a variable. However, just because you can doesn’t mean you should. There exist several naming conventions in the R community to help provide structure to variable naming. 

 

1. my_variable (underscore) 

2. myVariable (camel case) 

3. my.variable  (period)  

 

Although some may disagree with us, we believe for most users it does not matter which convention you pick. There are two key principles for variable naming that we recommend that should make your life easier: 

 

1. Consistency – pick a convention and stick with it. 

2. Succinctness - Keep variable names short, readable, and descriptive. 

 

For example, if you wanted a variable name for a temperature reading taken at Aberystwyth: 


This: 

>min_temp_aber_C 


Is better than this: 

>temp 
 

Or this: 

>themininimumtemperaturerecordedfromaberystwythindegreescelcius 

 
Being consistent, aware of context, and conscious of your variable naming will make reading your code easier and decrease the risk of mistakes.   

### Working with variables

Try:

```
my_name <- my_name + "your surname"
```
{: .input}

```
Error in my_name + "your surname" : 
  non-numeric argument to binary operator
```
{: .output}

What this error is telling you is that you tried to use a binary operator (+) on a non-numeric argument (my_name + "your surname"). 

We know that we are dealing with characters and in R '+' is an operator that runs on numeric variables. In the case of characters we need to use the method paste(). Try:

```
my_name <- paste(my_name, "your surname") 
```
{: .input}

When you check the variable in the environment tab you should see that it is updated. 

>## Useful tool
>* ***class()*** and ***typeof()***  
>You can datatype information using class() (for generalised) and typeof() (for secific) about your variables.  
{: .callout}

```
class()
```
{: .input}

```

```
{: .output}

```
typeof()
```
{: .input}

```

```
{: .output}

### Summary

Most of the time data types will not be of great concern to you. However, it is worth remembering that when you ask R to read and organise data it is making assumptions on the data types. Sometimes those assumptions can be wrong and could lead to unexpected outcomes. We will consider this in more detail later in the course. 

