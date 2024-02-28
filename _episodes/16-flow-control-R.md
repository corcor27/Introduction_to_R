---
title: "Flow control"
teaching: 25
exercises: 5
questions:
- "How do we get our code to react dynamically?"
- "How do we delegate repetative task and decisions?"
- "How do we make our software robust to a wider set of use cases?"
objectives:
- "Understand the role of flow control in managing the order of statement execution."
- "Understand the role and combination of logical and comparison operators"
keypoints:
- "Flow control is an important technique you need to learn to create useful software"
- "Whenever possible simplicity is the best option"
- "Plan & refactor"
---

Often, we want to perform different operations in our code based upon dynamic conditions. To explore this idea, we are going to pretend we have two sensors. The first representing a temperature, and the second representing if it there is rainfall. Our temperature is a numeric value, and our rainfall is a logical (Boolean). To declare those variables, type:

```
temp_reading <- 16 

rainfall <- TRUE 
```
{: .language-r}

Then place the following code into your ***script pane***: 

```
if (rainfall == TRUE){ 

  print("advise user to take umbrella") 

} 
```
{: .language-r}

{% include figure.html max-width="100%" file="/fig/ifflow1.png" 
alt="Flow diagrame for if condition" caption="Figure 1: Flow diagram for an *if* condition" %}


### Evaluating the order of operations
Run the script using the ‘run’ button on the top right of the pane (pay attention to where your cursor is in the script pane when you run the script). 

```
"advise user to take umbrella"
```
{: .output}

From observing the output in the console and from a brief inspection of the code, it should be evident that we are evaluating the variable rainfall. Specifically, we are checking for equivalence (**==**). If the outcome is of the check is valid then we perform any code within the brackets.


Now modify your code to look like this:

```
if (rainfall){ 

  print("advise user to take umbrella") 

}else{ 

  print("leave your umbrella at home") 

} 
```
Note: with logical variables, we don't have to check for equivalence (if (logical_variable) is if (TRUE/FALSE)).

{: .language-r}

{% include figure.html max-width="100%" file="/fig/ifflow2.png" 
alt="Flow diagrame for if condition" caption="Figure 2: Flow diagram for an if, else condition" %}

### Change the order
Now change the rainfall variable to ‘FALSE’ and run the script again.

```
rainfall <- FALSE

```
{: .language-r}

```
  "leave your umbrella at home"
```
{: .output}

Our code now reacts differently to different input values. You can combine ‘if’, ‘else if’, and ‘else’ statements to control the flow of your code.


### Conditional statements
* **‘if’** – used to execute a block of code if a condition is true. 

* **‘else if’** – extends an ‘if’ statement to only check this condition if the previous ‘if’ or ‘else if’ condition was resolved as false.  

* **‘else’** – extends an ‘if’ statement, will execute if none of the preceding ‘if’ conditions are true. 

### Comparison operators

We have encountered ‘==’, it is used to check for equivalence. Thare are other comparison operators available to us.

* ‘**<**’ Less than 

* ‘**<=**’ Less than or equal to 

* ‘**>**’ Greater than 

* ‘**>=**’ Greater than or equal to 

* ‘**==**’ equivalent 

* ‘**!=**’ not equivalent  

Intuitively you might think that some of these operators are going to work only for numeric values (i.e., how can "apple" < FALSE). We could try a few tests to get a feel for how it works:

```
TRUE == FALSE
```
{: .language-r}

```
FALSE
```
{: .output} 

As we would expect.

```
TRUE == TRUE
```
{: .language-r}

```
TRUE
```
{: .output} 

As we would expect.

```
"four" < "five"
```
{: .language-r}

```
FALSE
```
{: .output} 

R is clearly not comparing on the meaning of characters.
```
"five" < "six"
```
{: .language-r}

```
TRUE
```
{: .output} 

We are comparing alphabetically.

```
"apple" < FALSE

```
{: .language-r}

```
TRUE
```
{: .output} 

What is happening here? Why is "apple" less than FALSE?

R is attempting to interpret your request; therefore, it is coercing data types. Coercion follows a hierarchy where items can be converted from lower to higher but not higher to lower.  

* **Lowest**
* Logical: Logical values (TRUE or FALSE) are lowest in hierarchy. 
* Integer values. (True becomes 1, False becomes 0)
* Floating-point values. (5 becomes 5.0) 
* Character. The highest in hierarchy (TRUE becomes ‘TRUE’, 5.0 becomes “5.0”) 
* **Highest**

We are comparing "apple" < "FALSE" alphabetically. Try:

```
"zoo" < FALSE
```
{: .language-r}

```
FALSE
```
{: .output} 

Now the word is alphabetically greater than "FALSE" we should see FALSE as the response.

>## Question
> ***Why do we care about "apple" < FALSE ?***  
>We are never going to want to compare “apple” to FALSE, that is not the issue. The issue at hand is that if you have made a mistake and you are comparing the wrong variables you may not get an error. You will just be getting unexpected behaviour from your software which can be very difficult to catch. We will look more at coercion and data types when we deal with manipulating data sets. 
{: .callout}

Declare a new variable:

```
storm <- TRUE 
```
{: .language-r}

Replace the code in your script with this: 

 
```
if (storm == TRUE){ 

  print("stay at home") 

}else if (temp_reading < 10){ 

  print("take a coat") 

  if (rainfall){ 

    print("and take an umbrella") 

  }else{ 

    print("and leave your umbrella at home") 

  } 

}else{ 

  print("leave your coat") 

  if (rainfall){ 

    print("and take an umbrella") 

  }else{ 

    print("and leave your umbrella at home") 

  } 

} 
```
{: .language-r}

{% include figure.html max-width="100%" file="/fig/ifflow3.png" 
alt="Flow diagrame for if condition" caption="Figure 3: Flow diagram for an if, else if, else condition" %}

### Keeping things clear
We now have our old conditional statements inside a new conditional statement. This is referred to as **‘nested’**. If your code becomes overly nested it can impact readability and maintainability. It is good practice to keep your workflow as simple as possible, this can be made easier by spending time on design and regular refactoring.

> Note: 
> Refactoring is the process of restructuring code, not to change the functionality but to improve factors like readability, maintainability, efficiency. 

Now you have three variables **storm, temp_reading** and **rainfall**. You can modify the values and see how this changes the order statements are executed in a program.

>## Question
> ***What do you think might be probomatic about this example?***   
>There a several concerns that you may have. The ones I want to draw your attention to are
1. No defensive programming – What happens if we ‘accidently’ switch temp_reading and storm variables?
2. Hardcoded variables – Should a user preference be hard coded, what implications might this have? 
3. Redundancy - When we have repetition in code it can lead to problems with updating (e.g., if we want to make a chanje we must edit code in multiple places, this could easily introduce errors).
{: .callout}

We will look at these issue in more detail and consider ways to fix them as we go through more examples.

### Logical operators

Logical operators can be used to combine multiple comparison operators (e.g., if x < y and if x > z).

The most common are   

* AND ‘&&’ 

* OR ‘\|\|’ 

* NOT ‘!’ (negation)  

Let's try an example, add a new variable and add this new code to your script: 

```
day = "sunday"
```
{: .language-r}

 
```
if (storm == TRUE && (day == "saturday" || day == "sunday")){ #a storm won't stop me from working mon-fri
    print("stay at home") 
}else{
    print("go to work")
}
```
{: .language-r}

{% include links.md %}

This may look more complicated, but we are stringing the conditionals we already considered with logical operators (i.e., IF storm is true AND the day is (Saturday OR Sunday)).

>## Question
> ***What do you think the consequence of removing the brackets will be?***  
>Hint: Change storm <- FALSE, day <- "sunday".  
>What happens?  
>What should happen?
{: .callout}  

> You need to ensure that you are explicit with the conditional operations by using brackets, this will allow you to combine without encountering unwanted behaviour.

We have covered a brief introduction to the basic building blocks of flow control. Hopefully you have grasped, with the few tools we have considered, that you can develop sophisticated flow control. There are more tools to consider to be fully competent on all aspects of flow control. However, they fall outside of the scope of this course.    

We have included a source to provide a starting point for you to explore advanced flow control if you wish to (e.g., switch statements, loops etc.): 

[Starting point for advanced flow control](https://adv-r.hadley.nz/control-flow.html )

*Note: If you have coding experience you may have used loops before. In R loops can be problematic due to performance issue with memory allocation on large datasets. It is not a beginner-friendly topic; this in part, is why we have excluded them from this introduction to workflow.*   