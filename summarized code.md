# Introduction to Data Visualization with Seaborn : 

<h2> Importing the Essential Libraries </h2> : 
  
```  
# Importing the course packages
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Importing the course datasets
country_data = pd.read_csv('datasets/countries-of-the-world.csv', decimal=",")
mpg = pd.read_csv('datasets/mpg.csv')
student_data = pd.read_csv('datasets/student-alcohol-consumption.csv', index_col=0)
survey = pd.read_csv('datasets/young-people-survey-responses.csv', index_col=0)
  
 ```
 
 
 <h2> **Creating subplots with col and row </h2> 
 
 
 INSTRUCTIONS : 
 
<br> Modify the code to use relplot() instead of scatterplot()
<br> Modify the code to create one scatter plot for each level of the variable "study_time", arranged in columns.
<br> Adapt your code to create one scatter plot for each level of a student's weekly study time, this time arranged in rows.
  
 CODE : 
 
 
 ```
 
 # Change this scatter plot to arrange the plots in rows instead of columns
sns.relplot(x="absences", y="G3", 
            data=student_data,
            kind="scatter", 
            col="study_time")

# Show plot
plt.show()
 
 ```
 OUTPUT :
 ![image](https://github.com/Darshan0902/Visualizing-Two-Quantitative-Variables/assets/77969007/0c033865-9c6d-4d02-b51f-aba31056e495)


<h2> In Vertical format and arranging plot in rows instead of columns : </h2> :

```
# Change this scatter plot to arrange the plots in rows instead of columns
sns.relplot(x="absences", y="G3", 
            data=student_data,
            kind="scatter", 
            row="study_time")

# Show plot
plt.show()

```

OUTPUT : 
![image](https://github.com/Darshan0902/Visualizing-Two-Quantitative-Variables/assets/77969007/8b27e26b-ca84-4e02-82dc-73efa6487a0f)



<h2> Creating two-factor subplots </h2> 

Use relplot() to create a scatter plot with "G1" on the x-axis and "G3" on the y-axis, using the student_data DataFrame.

```

# Adjust to add subplots based on school support
sns.relplot(x="G1", y="G3", 
            data=student_data,
            kind="scatter",col )

# Show plot
plt.show()

```


<h2> Create column subplots based on whether the student received support from the school ("schoolsup"), ordered so that "yes" comes before "no". </h2> 



```

# Adjust to add subplots based on school support
sns.relplot(x="G1", y="G3", 
            data=student_data,
            kind="scatter",col="schoolsup",col_order=["yes","no"] )

# Show plot
plt.show()

```

<h2> Create column subplots based on whether the student received support from the school ("schoolsup"), ordered so that "yes" comes before "no". </h2> 



```

# Adjust further to add subplots based on family support
sns.relplot(x="G1", y="G3", 
            data=student_data,
            kind="scatter", 
            col="schoolsup",
            col_order=["yes", "no"],
            row="famsup",row_order=["yes","no"])

# Show plot
plt.show()

```


<h2> 
Changing the size of scatter plot points </h2> 


Use relplot() and the mpg DataFrame to create a scatter plot with "horsepower" on the x-axis and "mpg" on the y-axis. Vary the size of the points by the number of cylinders in the car ("cylinders").


```

# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create scatter plot of horsepower vs. mpg
sns.relplot(x="horsepower", y="mpg", 
            data=mpg, kind="scatter", 
            size="cylinders")

# Show plot
plt.show()

```
<h2> Changing the size of scatter plot points </h2> 

To make this plot easier to read, use hue to vary the color of the points by the number of cylinders in the car ("cylinders").

```
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create scatter plot of horsepower vs. mpg
sns.relplot(x="horsepower", y="mpg", 
            data=mpg, kind="scatter", 
            size="cylinders",hue="cylinders")

# Show plot
plt.show()

```
<h2> 
Changing the style of scatter plot points </h2> 

Use relplot() and the mpg DataFrame to create a scatter plot with "acceleration" on the x-axis and "mpg" on the y-axis. Vary the style and color of the plot points by country of origin ("origin").


```

# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create a scatter plot of acceleration vs. mpg
sns.relplot(x="acceleration",y="mpg",data=mpg , kind = "scatter",hue="origin",style="origin")



# Show plot
plt.show()

```

<h2> Interpreting line plots </h2> 

Use relplot() and the mpg DataFrame to create a line plot with "model_year" on the x-axis and "mpg" on the y-axis.
Exercise Exercise Interpreting line plots In this exercise, we'll continue to explore Seaborn's mpg dataset, which contains one row per car model and includes information such as the year the car was made, its fuel efficiency (measured in "miles per gallon" or "M.P.G"), and its country of origin (USA, Europe, or Japan).

How has the average miles per gallon achieved by these cars changed over time? Let's use line plots to find out!

Instructions 2/2 50 XP 2 Question Which of the following is NOT a correct interpretation of this line plot?

Possible Answers

The average miles per gallon has generally increased over time.

The distribution of miles per gallon is smaller in 1973 compared to 1977.

The 95% confidence interval for average miles per gallon in 1970 is approximately 16 - 19.5 miles per gallon.

This plot assumes that our data is a random sample of all cars in the US, Europe, and Japan.



<h2> Visualizing standard deviation with line plots </h2> 


Change the plot so the shaded area shows the standard deviation instead of the confidence interval for the mean.



```

# Make the shaded area show the standard deviation
sns.relplot(x="model_year", y="mpg",data=mpg, kind="line",ci="sd")

# Show plot
plt.show()

```
<h2> Plotting subgroups in line plots </h2> 

Use relplot() and the mpg DataFrame to create a line plot with "model_year" on the x-axis and "horsepower" on the y-axis. Turn off the confidence intervals on the plot.


```

# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Change to create subgroups for country of origin
sns.relplot(x="model_year", y="horsepower", 
            data=mpg, kind="line", 
            ci=None)

# Show plot
plt.show()

```

<h2> Plotting subgroups in line plots </h2> : 

```



```

