---
title: "Seeking help"
teaching: 5
exercises: 0
questions:
- "Where can I find help?"
objectives:
- "Learn how to use the in-built RStudio help pane"
- "Know where to look for answers and how to ask the right questions"
keypoints:
- "You will get stuck at some point, needing help is a case of when not if."
- "Help is available put is is important you have done your due diligence and are asking for help in the correct places and in the correct format."
---

## What do I do when I need help?

It is inevitable, at some point you will need help. For most people it is impossible to remember every facet of the R language. As such, you will often need to familiarise yourself with the functionality of some aspect of the R language. The help panel built into RStudio is an excellent starting resource.  

Head to the console, we will request some help about a function we used in the pre-worksheet. Type:

```
? getwd()
```
{: .language-r}

>***Note:*** You may have notice that RStudio is attempting to autocomplete your commands.
> This can be very useful and efficient but can also lead to you running the wrong commands if you are not paying attention.  

{% include figure.html max-width="100%" file="/fig/helpwithfunctions.png" 
alt="Help pane showing getwd() function" caption="Figure 1: Your help pane should now contain this information" %}
  
### Help output

Each function help page is broken down into these sections:  
* **Description:** An extended description of what the function does.
* **Usage:** The arguments of the function and their default values (which can be changed).
* **Arguments:** An explanation of the data each argument is expecting.
* **Details:** Any important details to be aware of.
* **Value:** The data the function returns.
* **See Also:** Any related functions you might find useful.
* **Examples:** Some examples for how to use the function.  

Different functions might have different sections, but these are the core set.  

All this information may seem slightly overwhelming now, as you get more familiar with functions you will find this help more useful.

You can also use the help for other aspects, like operators. Write into the console:

```
? '+'
```
{: .language-r}

It seems unlikely that you will need help with a plus operator but there are a whole range of operators that we will encounter that may be less obvious to you.

### External help

If you have encountered a problem, often your question has already been answered on Stack Overflow. You can search using the [r] tag. If you can’t find the answer you may want to ask your own, first make sure you have read:

[How to ask a good question](https://www.stackoverflow.com/help/how-to-ask)

Here are a few useful functions to provide the details you may need for asking your question.  

Dput will give you an easy to copy and paste output for your data objects.
```
dput(yourvariable)
```
{: .language-r}

SessionInfo will print out your version of R and packages that are currently loaded. 
```
sessionInfo() 
```
{: .language-r}


Here we provide some external links providing useful references and cheat sheets for new users of R. Without context they may seem a little daunting but as your knowledge and confidence grows they will become useful references.

[R help refrences](https://www.statmethods.net/)  

[R beginner's cheat sheets](https://www.datacamp.com/cheat-sheet/getting-started-r)

