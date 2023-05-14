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
