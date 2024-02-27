---
title: "Lists and Data frames"
teaching: 15
exercises: 5
questions:
- "What other data structures are there?"
objectives:
- "Understand the use of vectors, lists, and data frames."
keypoints:
- "Data frames are lists of vectors."
- "Data frames are the most common way of storing tabular data"

---

### Lists

We will take a brief look at lists. At first glance may seem very similar to vectors but we are going to cover some key differences. Lists can hold different data types they are not restricted to a single data type like vectors. They also can hold vectors. matrices, and even other lists which allows them to assume more complicated and hierarchical structures than vectors. Try out: 

```
list_example <- list(1, “hello”, TRUE) 
```
{: .language.R}

```
vector_example <- c(1, “hello”, TRUE) 
```
{: .language.R}

If we ouput both structures via the console:

```
list_example
```
{: .language.R}

```
1 "hello" TRUE
```
{: .output}
```
vector_example
```
{: .language.R}

```
"1" "hello" "TRUE"
```
{: .output}



> ## What is different about the ‘vector_example’ and the ‘list_example’?  
> We know that all variables in a vector must have the same type. If we remember the hierarchical order of coercion we know R will have to change variables to the highest variable type, in this case character. This is what we see in the vector_example.
{: .callout}

### Addressing lists

To access a specific element in a list you need to address with double brackets (e.g., “list_example\[\[1\]\]”). If you use single brackets, you will get access to a sub list that contains the element. 

```
list_example[[3]]
```
{: .language.R}

```
TRUE
```
{: .output}

```
list_example[3]
```
{: .language.R}

```
[[1]]
TRUE
```
{: .output}


### Data frames

Data frames are used to store and work with tabular data. They are a two-dimensional data structure where columns must contain the same data type but columns can hold differing data types from other columns (if you think this data structure sounds suspiciously like a list of vectors you are right). Data frames can be created in RStudio from the console but most commonly we are going to want to read them in from a source (e.g., csv file, excel spreadsheet, etc.).  

{% include figure.html max-width="100%" file="/fig/datastructure.png" 
alt="Variable, vector, list and dataframe visual representation" caption="Figure 1: Visual representation of how variable types are stored in the different data structures we have explored." %}




{% include links.md %}
