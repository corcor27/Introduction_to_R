---
title: "Loading data into R"
teaching: 5
exercises: 5
questions:
- "How do I get my own data into RStudio?"
objectives:
- "Can load data files into RStudio."
keypoints:
- "Loading in the data is just the first step"
---

## Loading your data

Getting your data into R is the first step to you doing something interesting with it. Click the link below to download a new dataset.

[Download File](../fig/gapminder_data.csv)

Place it in a folder (name the folder ‘data’) and change the file permissions of the dataset to read only. The easiest way to achieve this is to find the document in your file management system, inspect its properties and apply read only. 

>Note: You can also do this through the terminal (in the console pane) using ‘attrib +r’ for windows or ‘chmod 444’ for linux/mac. 
>This is only recommended if you have prior experience working in the command line.

To load our file, in the console, type:

```
gapminder <- read.csv("data/gapminder_data.csv")
```
{: .language.r}


If you have problems with getting file paths to work, you can use:

```
file_path <- file.choose()
```
{: .language.r}

```
gapminder <- read.csv(file_path)
```
{: .language.r}

This function should open a file explorer window where you can select the file you want to open, and it will return you the file path. What format and size your data comes in will dictate how best to process and store it.

This is a simple introduction to getting your data into R. In some cases there will be significant complications (e.g., many files, large data size, unusual file format, etc.), in cases like this **dplyr** has tools to help.


