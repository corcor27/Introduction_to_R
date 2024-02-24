---
title: "Variables and assignment"
author: "Colin Sauze, Ed Bennett, Jarno Rantaharju, Thomas Green"
teaching: 15
exercises: 10
questions:
 - "Where can I store my data?"
 - "What is the difference between scratch and home filestore?"
 - "How to use filesystems in job scripts."
objectives:
 - "Understand the difference between home and scratch directories"
keypoints:
 - "The home directory is the default place to store data."
 - "The scratch directory is a larger space for temporary files."
 - "On Hawk in Cardiff home is backed up but is also a slower disk."
 - "Quotas on home are much smaller than scratch."
---


# What are variables and why do we want them?

### Moving on from calculation
we don’t just want RStudio to be our calculator. We want to be able to store and manipulate data in a meaningful way. We want to perform operations on data, possibly many times. It would be useful to have a clarity and context for the data we are using; ideally descriptive names to make our data more manageable.

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

Now we have created variables we can now refer to them in the console. Type:

```
x + 5
```
{: .input}

```
15
```
{: .output}





# Exercises

> ## Using the `df` command. 
> 1. Login to a login node
> 2. Run the command `df -h`.
> 3. How much space does /scratch have left?
> 4. If you had to run a large job requiring 10TB of scratch space, would there be enough space for it?
{: .challenge}


