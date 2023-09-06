# Statistics-with-R-lab3
Introduction Simple Linear Regression in R studio
Tasks
 Use Rmarkdown and make clear and readable files. Do this:
o Work on the Lab 3.R script file first and get all the correct code working first before
using R markdown – only paste into Rmd after you have completed the lab.
o Once you are happy with the final Rmd documents knit tasks 1-6 into html – then wait!
o Use the separate rmd file for Task 7 – run in RStudio. There are three settings for the
widget – make a screen print for each – include these in your Lab 3 rmd document under
Task 7 – you can use ![](png){ width=70% } where png is the name of your picture file.
 Task 1
o Download from CANVAS the zipped data files, “Dataxls”
o Unzip the contents into a directory on your desktop (call it LAB3)
o Download the file “lab3.r”
o Place this file with the others in LAB3.
o Start Rstudio
o Open “lab3.r” from within Rstudio.
o Go to the “session” menu within Rstudio and “set working directory” to where the source
files are located.
o Copy and paste the working directory by issuing the command getwd():
 Task 2
o Find the file “SPRUCE.xls” inside LAB3
o Open it in Excel
o Save As type CSV(comma delimited) “*.csv”
o Use read.table() to read the data into R (or any other method available), this
function will already be available within the script lab3.r which you have opened in
Rstudio.
o Obtain the first six lines of the data using “head()”
o Make a new file for your code in RStudio editor, call it “mylab3.R” and place in it all the
code you need to answer the tasks of this lab (copy and paste from lab3.R).
 Task 3
o The SPRUCE data set is described in MS 10.52, pages 478 and 479. This data set has two
variables, Height = Height of Spruce trees in m (this is what we want to predict) and
BHDiameter = Breast height Diameter in cm. The idea is that breast height diameter is an
easy measurement to make whereas the height of the trees is much more difficult. We
want to see if there is a relationship between the two variables that enables us to predict
Height from Diameter.
o Make a scatter plot of the data (y axis will be the Height).
 Make sure it has a heading
 Y axis is labelled
 X axis is labelled
 Points are filled blue, use pch=21 and bg=”Blue”
 The points are 1.2Xs the default character size (use cex=1.2)
 The y and x axes are adjusted to include 0 and 1.1*max(y), and 0 and
1.1*max(x) respectively
o Does there appear to be a straight line relationship?
o Load the library s20x and make a lowess smoother scatter plot using
trendscatter() (try a few values of f, f=0.5,0.6,0.7) record all three plots, use
layout().
o We will assume (this may in fact be a bad assumption) a straight line relationship, use lm
and make a linear model object, call it spruce.lm
o Make a new scatter plot and add the least squares regression line to the points -
abline(spruce.lm) – record the plot.
o Comment on the graph, is a straight line appropriate? Consider the smoother curve also.
 Task 4
o Divide the graphical interface into 4 equal areas, use layout.show(4) and record the
picture.
 In the first square, plot the scatter plot and fitted line.
 In the second square plot the same with the residual line segments (deviations
about the fitted line). (RSS=residual sum of squares)
 In the third square plot the mean of Y versus X i.e. mean of Height vs
BHDiameter, with the fitted line and deviations of the fitted line from the mean
height added. (MSS=model sum of squares)
 In the fourth square plot the mean of Height versus BHDiameter and show the
total deviation line segments 𝑦 = 𝑦. (TSS=total sum of squares)
In brief reproduce the plot below for the SPRUCE data set.
 Calculate TSS, MSS and RSS
 Calculate 𝑀𝑆𝑆
𝑇𝑆𝑆 , and interpret it!
 Does TSS=MSS+RSS?
 Task 5
o Summarize spruce.lm paste it here.
o What is the value of the slope?
o What is the value of the intercept?
o Write down the equation of the fitted line.
o Predict the Height of spruce when the Diameter is 15, 18 and 20cm (use
predict())
 Task 6
o Use appropriate code using the ggplot2 package to make a plot of Height Vs
Diameter with shading lines and legend as shown below:
 Task 7
o Now that you have made the ggplot of Task 6 we will take our presentation one step
further by making an interactive document.
o Open the file Task 7.rmd in R markdown.
o There are a number of controls that will create input for your dynamic plot.
o Using the example given in Task 7.rmd create a shiny interactive document that has a
selectInput() widget function with choices
 One straight simple linear regression line that estimates the trend (see blue line
above)
 Points alone
 Points joined with line segments
o Run your document and for each selection of your control (widget) take a picture using
PrtScr – save in your working directory.
o Place in your rmd document using ![](filename){ width=70% }
