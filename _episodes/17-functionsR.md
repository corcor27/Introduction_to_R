---
title: "Functions"
teaching: 15
exercises: 5
questions:
- "How do I make my own functions?"
- "Why would I want to make my own functions?" 
objectives:
- "Understand function structure"
- "Know how to use the 'apply' family of functions"
keypoints:
- "Functions can help reduce redundancy and increase reusability in your code"
---

### Exploring functions

So far, we have been using in-built functions. For exmaple you type ‘sqrt()’ place your value (argument/parameters) into the function, some magic happens, and it returns an output. We will now start to the structure of functions and how we can create our own.  

### Function structure 

> my_function <- *function*(parameters) {     
> perform action  
> return value  
> }

### Function example

We can convert our previous calculation into a function. Open a new script file and type this in: 

```
celc_to_fahr<- function(celc) { #function name and the arguments we are passing in 
  fahr <- celc* 9/5 + 32 #the actions we are acting on our arguments 
  return(fahr) #what we are returning 
} 
```
{: .language-r}

Save this script as 'my_functions' and run the lines from the script pane.

Now we can convert Celsius to Fahrenheit in the console by typing:

```
celc_to_fahr(14) 
```
{: .language-r}

```
57.2
```
{: .output}

Go back to to the script my_first_script. At the top of the script place this line:

```
source("my_functions.R") 
```
{: .language-r}

We can now run this function from my_first_script.

```
celc_to_fahr(14) 
```
{: .language-r}

```
57.2
```
{: .output}

If you have generalised functions that you use often in different scripts. It is good practice to store them in a script file. You can then import them into any project that you need them for. This reduces rewriting and editing code, and reduces the chance of you introducting errors (e.g., typos, caluclation errors, etc.).

If we want to run this method on multiple variables, we can use the sapply() method. This method takes data and a function. It then applies the function to every variable from the data you provided. 

```
fahrenheit_temps <- sapply(temperatures,  celc_to_fahr) 
```
{: .language.r}

For more information on the common apply family functions, you can check: 

```
?sapply()  

?lapply() 

?apply() 
```
{: .language.r}

### But wait!  
You might be confused and thinking; the output:  
```
‘fahrenheit_temps’
``` 
looks like an identical output to 
```
temperatures <- temperatures * 9/5 + 32
```
that we processed earlier.  
Very well spotted, we have used a slightly redundant but very simple example to highlight the process. In the future you may want to create much more complicated functions that you want to apply to large datasets, this was just a toy example to show you how. 


