---
title: "Plotting in R with ggplot2"
teaching: 10
exercises: 5
questions:
- "How do I create plots?"
- "How do I use data sets to populate my plot?"
objectives:
- "Understand how plots are formed syntactically in ggplot2."
- "Can create plots from data sets."

keypoints:
- "Plotting is useful tool for understanding our data it is not just for results visualisation"
---

Plotting our data is one of the best ways to intuitively explore it, and the various relationships between variables. There is a base plotting system in R. But we will be using the ggplot2 package because it is more effective for creating publication-quality graphics. Ggplot2 is built on the grammar of graphics, the idea that any plot can be built from the same set of 3 components: a data set, mapping aesthetics, and graphical layers.

1.	**Data sets** are the data that you provide.
2.	**Mapping aesthetics** are what connect the data to the graphics. They tell ggplot2 how to use your data to influence how the graph looks (e.g., changing what is plotted on the X or Y axis).
3.	**Layers** are the actual graphical output from ggplot2. Layers determine what kinds of plot are shown (scatterplot, histogram, etc.), the coordinate system used (rectangular, polar, others), and other important aspects of the plot. The idea of layers of graphics may be familiar to you if you have used image editing programs like Photoshop, Illustrator, or Inkscape.


Let’s use the iris data set to generate an example using ggplot2. In your script panel make sure you have:

```
library(ggplot2)
```
{: .language.r}


```
ggplot(data = df_iris, mapping = aes(x = PetalLengthCm, y = PetalWidthCm)) +
	geom_point()

```
{: .language.r}


There is a fair amount to unpack here so we will take it section by section. 
1.	*data = df_iris* : is the data we are providing.
2.	*Mapping = aes(x = ‘variable on x’, y = ‘variable on y’)* : is the variables we want plotted and on which axis.
3.	*+ Geom_point’* : is the relationship we want between x and y, in this case a scatter plot.

There are many different type of plots, if you need a specific kind of plot a good place to start is the super helpful cheat sheet on ggplot2. To explore all the different options you can go here:


[Data visualization cheat sheet](https://www.rstudio.org/links/data_visualization_cheat_sheet)


