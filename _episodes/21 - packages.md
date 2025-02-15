---
title: "Packages in R"
teaching: 5
exercises: 0
questions:
- "How do I install packages?"
- "How do I get help with packages?"
objectives:
- "Can install and load packages."
- "Understands how to find help with packages."
keypoints:
- "There are many packages with a wide range of features, becoming adept at utilising packages is key to getting the most out of R"
---

Packages extend the functionality of base R by providing additional functions, datasets, and tools for specific tasks or domains. It is important that you are conscious that there may be specific versions of the R language and package versions required to use multiple packages simultaneously (version compatibility). It is recommended that you keep packages up to date wherever possible as new versions normally include bug fixes, performance improvements and new features. We should have already installed all the packages that we need for this course based of the pre-worksheet. However, as a reminder:

```
install.packages(“package_name”)
```
{: .language.r}

Installation only needs to be done once no matter how many projects you start. To use the package in RStudio, you need to ensure that you type:

```
library(package_name) 
```
{: .language.r}

> Note:   
> This will need to be added to the beginning of every script that needs this package


### Help with packages

Many packages come with vignettes (tutorials and extended example documentation). Without any arguments, ‘vignette()’ will list all vignettes for all installed packages, ‘vignette(package=’package-name’)’ will list all available vignettes for ‘package-name’, and vignette(‘vignette-name’) will open the specified vignette. If a package doesn’t have any vignettes, you can usually find help by typing help(‘package-name’).

```
vignette("ggplot2")
```
{: .language.r}

For this course one of the most common packages that you will require is called "stats", which is a inbuilt library already available in R studio by default. Now have ago at loading in the package. 

```
library("stats) 
```
{: .language.r}

Now that you have the stats package loaded in, lets do some simple statistical analysis to find the median, mean and Inter-quartile Range  of a feature from the iris dataset. Firstly, as previously covered lets load in the iris dataset. 

```
iris
```
{: .language.r}

Now lets find the median of the feature Sepal length.

```
median(iris$Sepal.Length)
```
{: .language.r}
which gives us:

```
5.8
```
{: .output}

Next find the mode and mean for the same feature:

```
mean(iris$Sepal.Length)
IQR(iris$Sepal.Length)
```
{: .language.r}

which gives us:

```
5.843333
1.3
```
{: .output}

Here we have just done some simple statics on the iris dataset. In the actually course we will be doing some more complicated methods that involve statistical tests. Therefore, it might be a good idea to have a quick look at the online guide of functions that you could use. Please see: 
<mark> https://stat.ethz.ch/R-manual/R-devel/RHOME/library/stats/html/00Index.html
