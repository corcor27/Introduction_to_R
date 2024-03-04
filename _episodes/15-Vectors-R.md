---
title: "Vectors and vectorisation"
teaching: 15
exercises: 5
questions:
- "How do we mange many variables efficiently?"
objectives:
- "Be able to declare, manipulate, and address vectors."
- "Understand the process and role of vectorisation."
keypoints:
- "Vectors can only hold a single data type"
- "Vectorisation allows us to apply operations to all the variables in a vector"
- "Vectors can be indexed by multiple methods to retrieve/manipulate the specific information you desire"
---

### What happens when we have to deal with multiple variables?

It may have occurred to you that dealing with variables individually is going to be less and less efficient as our data size set gets significantly larger. We are going to explore how we can store and organise our data in some useful ways.

### Vectors 

Vectors are a one-dimensional group of items, they must be all the same data type. We can declare a vector like this:

```
temperatures <- c(23.5, 20.6, 15.8, 22.0) 
```
{: .language-r}

The c() function combines the items you provide it into a vector. You may want to learn more by typing “?c”.  

You can also create vectors using ‘rep()’, ‘seq()’, or ‘:’. Now try: 

```
num_range <- 1:10 
```
{: .language-r}

```
num_rep <- rep(1, 10) 
```
{: .language-r}

```
num_sequence <- seq(0,1, by =0.1)
```
{: .language-r}

Congratulations we now have four vectors, explore them in the environment tab. Are they what you were expecting?


Can you determine how each one works?
1. ‘rep()’
2. ‘:’ 
3. ‘seq()

You can always look them up using the help pane if you are not sure.

### Addressing and manipulating vectors

Once created, it is possible we may want to modify the variables in our vector.

You can address positions in the vector using the syntax **'vector\[index\]'**, for example:

```
temperatures[1]
```
{: .language-r}

```
23.5
```
{: .output}

Note: Indexing starts at 1 in R (this is unlike most other languages where indexing starts at 0).

If we want to change what is at that index we can type:

```
temperatures[1] <- 20.5
```
{: .language-r}

```
temperatures[1]
```
{: .language-r}

```
20.5
```
{: .output}

We can access the last item in the vector using:

```
temperatures[length(temperatures)]
```
{: .language-r}
```
22.0
```
{: .output}

We can exclude items by using:
```
temperatures[-3] 
```
{: .language-r}


```
23.5 20.6 22.0
```
{: .output}

### Vectorisation

We tried out some in-built mathematical functions on our variables earlier in the course. Lets try some on our vectors:

```
mean(temperatures) 
```
{: .language-r}


```
20.475
```
{: .output}


```
sum(temperatures) 
```
{: .language-r}


```
81.9
```
{: .output}


```
min(temperatures) 
```
{: .language-r}


```
15.8
```
{: .output}


```
max(temperatures) 
```
{: .language-r}


```
23.5
```
{: .output}


```
round(temperatures) 
```
{: .language-r}


```
24 21 16 22
```
{: .output}


This is by no means a definitive list of in-built functions for vectors, there are many more available (you can use one of the external help links or a google search to find ones that are relevant to your task).

Notice that we did not have to explicitly ask for each calculation on each variable to be performed. R allows us to apply the same operations we can apply to a single variable to vectors directly. The assumption is that we want to apply the operation to each variable in the structure. This is called vectorization.

We may want to apply an operation that does not exist as an in-built function, Try: 

```
temperatures <- temperatures * 9/5 + 32 
```
{: .language-r}

We have explicitly told R to save the output back into the 'temperatures' vector. Use the environment pane to explore what we have created. All the temperatures have been converted from Celsius to Fahrenheit.

### Make changes but only to specific items.

Sometimes we may only want to change certain variables in a vector based on their value. 
**Example:** Find all the variables that are higher than 70 Fahrenheit and increase them by 10.  
First we need to find out which variables fit our requirement  
```
above_70 <- temperatures > 70 
```
{: .language-r}

```
TRUE FALSE FALSE  TRUE
```
{: .output}

This has created a logical vector that indicates if that index is above 70 using TRUE/FALSE. You can now use this vector to address the 'temperatures' vector, selecting only those elements. Try:

```
temperatures[above_70] <- temperatures[above_70] + 10 
```
{: .language-r} 

Check the results in your environment pane they should be modified. This is an example of how we can modify vectors but there are many different ways to address and manipulate vectors based on your required output.


