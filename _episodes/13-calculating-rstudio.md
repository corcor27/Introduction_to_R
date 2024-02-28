---
title: "Calculating in RStudio"
teaching: 5
exercises: 5
questions:
- "How do we process mathmatical operations in RStudio?"
objectives:
- "Become familiar with mathmatical operators and in-built functions in RStudio."
- "Become confident using the console to run mathmatical operations."
- "Understand the order of operations."
keypoints:
- "***PEDMAS***"
- "Use in-built functions, you don't need to reinvent the wheel."
---

### Dipping our toes
We have covered some relatively dry theory so let’s take some small steps and start interacting with R. From the console we can start exploring calculation. Write in the following commands:

```
10 – 5 #(subtraction) 
```
{: .language-r}

```
5
```
{: .output}



```
10 + 5 #(addition) 
```
{: .language-r}

```
15
```
{: .output}



```
10 * 5 #(multiplication) 
```
{: .language-r}
```
50
```
{: .output}



```
10 / 5 #(division) 
```
{: .language-r}

```
2
```
{: .output}



```
5 ^ 2 #(exponentiation) 
```
{: .language-r}
```
25
```
{: .output}



```
10 %% 3 #(modulus)  
```
{: .language-r}
```
1
```
{: .output}


### Order of operations

> ## Question: Before you enter the next calculation, take a second and consider what answer would you be expecting?
```
6 + 9 / 3 
```
{: .language-r}
{: .challenge }


```
9
```
{: .output}


If the answer was not what you were expecting you will need to become clear on order of operations in R. 

 
### Remember **PE(DM)(AS)** 

* **P**arentheses 

* **E**xponentiation 

* **D**ivision/**M**ultiplication\*  

* **A**ddition/**S**ubtraction\*  

\* Operators with same precedent are calculated left to right. 

 
This tells you what order mathematical operations will be performed and ensures consistency during evaluation.  

To make this concept clearer, try: 

```
(6 + 9) / 3 
```
{: .language-r}

```
5
```
{: .output}

Using brackets we have manipulated the order of operations to perform the addition before the division. Be conscious of how you structure your mathematical operations to ensure the desired results but also readability of your code. 

### Mathmatical Functions

Base R provides you with a range of built in mathematical functions. If you need a fairly common operation there is a good chance it already exists. Let's look at a few examples, try:

```
sqrt(9) 
```
{: .language-r}
```
3
```
{: .output}

```
abs(-5) 
```
{: .language-r}
```
5
```
{: .output}

```
round(3.4) 
```
{: .language-r}
```
3
```
{: .output}


There are a whole range of built-in functions that are available. You can check the help reference or perform a google search to find a definitive list.

