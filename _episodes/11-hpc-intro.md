---
title: "RStudio Layout, navigating the IDE"
teaching: 15
exercises: 5
questions:
- "How is RStudio layed out?"
objectives:
- "Be familair with the panes contained with RStudio"
- "Be confident creating a new project and new script files"  
keypoints:
- "R and RStudio are not the same thing. RStudio is an IDE that provides you with a convinient way to manage R projects and R is the underlying language that enables RStudio."
- "You will not learn everything about RStudio in a day, there are a huge number of tools available to you in RStudio. The more time you commit to exploring and practicing the more you will achieve."
---

## Starting a new project:
Let us start by exploring the major features of we will use for this course in RStudio. Our first aim is to become more familiar with the interface. Start by generate a new project (name it **‘my_first_r_project’**). Next, open a new script file (name it **'my_first_r_script’**). 

{% include figure.html max-width="100%" file="/fig/rstudioIDE.png" 
alt="RStudio pane layout on first initialisation" caption="Figure 1: RStudio layout you should expect to see (OS and version dependant)" %}

## Menu Bar
The Menu bar controls some of the major actions available in RStudio. The most common are creating, saving and loading projects and scripts. If you look through the drop-down menus you will notice that many procedures have shortcuts allocated. The more familiar you get with RStudio the more you will start to take advantage of these shortcuts and possibly create or remap your own shortcuts. 

>## Bottom left
>## Console
>This is the console pane. It should be prepopulated with text detailing things the version of R you are currently using, among other things. The console is your primary interface with the R programming language. You will use it often for inputting prompts and displaying outputs.  
{: .callout}

>## Top left
>You should see the script pane in this location. It provides a powerful and user-friendly environment for writing, editing, and managing R code and other documents. You can write commands into the script pane and run them by placing your cursor at the beginning of the line and press the run button.
{: .callout}

> ## Question: Why do we need the console and the script pane when they do similar things?
> Although there is some overlap between the two, when we look closer, we will find there are different capabilities of both
> panes. To clarify the situation using a kitchen analogy; imagine the console is your kitchen worktop, you could try out 
>different techniques, or perform specific tasks. Your script pane is akin to a recipe book, a place to create a collection of 
>work that you want to perform time and time again.  
{: .challenge }

## How these two panes influence your workflow options: 

Much of your initial learning time in R will be spent in the R interactive console. This is where you can test out lines of code and it can be a useful environment to try out ideas. This way of working is successful when conducting small task and initially starting off. It can quickly become inefficient for large tasks with more complex structure. Writing scripts will allow you to better manage the workflow of more complicated projects. Storing your code in scripts allows for easier maintenance, collaboration, and code clarity.

>## Top Right
>## Environment
>The environment pane provides a convenient way to inspect, manage, and interact with the objects and variables in your R environment. This view should help give you an insight into your data and allow you to interact with it more efficiently.
>## History
>The History pane in RStudio provides a convenient way to review and manage your command history. It has a button that pushes a selected command into your script pane that you may find handy.
{: .callout}

>## Bottom Right 
>## Files
>The files pane in RStudio provides a straightforward way to navigate and manage files and directories within your project. 
>## Plots
>The plots pane in RStudio is used to interact with graphical output from your R code. You can visualise, explore, manage, and export data plots.
>## Help
>Serves as a valuable resource for learning about R programming, exploring package functionality, troubleshooting issues, and finding answers to your questions. 
{: .callout}

>## Important to explore
>Clearly there are many more features to RStudio we have not covered in this brief introduction. If you continue to use RStudio you will encounter tools that you will find particularly useful for your specific needs. 
{: .challenge }
{% include links.md %}
