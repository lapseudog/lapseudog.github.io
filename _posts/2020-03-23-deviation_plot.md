---
layout: post
author: lapseudog
---

# How to make a deviation plot with Python
This post is inspired from the post on the “The DO Loop” blog ([https://blogs.sas.com/content/iml/2020/03/02/deviation-plot-baseline.html](https://blogs.sas.com/content/iml/2020/03/02/deviation-plot-baseline.html)). As I am learning Python I thought it was interesting to learn how to make charts using the matplotlib library.

# Extracting the data from SAS
First thing I slightly adjusted the sas script to use a different date format: From the classic to SAS Date. to the format Date yymmdd10. Then exporting the results as a csv and using that as a starting point in Python.

# Data Preparation in Python 
As the data is quite simple only numpy is used.
```python
ndata = np.genfromtxt("c:\\Users\\Eric\\Downloads\\Series.csv", delimiter=",", dtype=['datetime64[s]', 'float64'], names=['Date', 'y'], skip_header = 1 )

references = np.full(ndata['Date'].shape, np.nanmedian(ndata['y']) ) # set a reference point as the median 

lows = np.fmin(references, ndata['y']) # the lower end of the line

highs = np.fmax(references, ndata['y']) # the higher end of the line

colors = np.where(highs > references, 'darkorange', 'royalblue') 
```

To make the output slightly different, I choose a different reference value: the median.

The point of interest is that in SAS the “min” function handles the missing values by propagating the missing values only when both arguments are missing. In numpy the min function propagates the missing values; I could only find the fmin (and fmax) function that worked as in SAS. 

# Chart preparation
I used the common Matplotlib, other libraries would probably work as well. 
```python
fig, ax = plt.subplots(figsize=(16,6)) # elongated horizontal

ax.vlines(ndata['Date'], lows, highs, colors= colors) # the lines from low to high , with a specific color

locator = mdates.AutoDateLocator(minticks=2) # to minimise the number of ticks marks

formatter = mdates.ConciseDateFormatter(locator)

ax.xaxis.set_major_locator(locator)

ax.xaxis.set_major_formatter(formatter)

plt.ylabel("Blood Glucose (mg/dL)") 

title = "Deviation from Reference Value (" + str(references.item(1)) + ")\n Morning Fasting Blood Glucose"

plt.title(title)

plt.show()
```

Here the point of interests are:

*   To use the vlines
*   To choose how the ticks should be placed. The ConciseDateFormatter was selected but if a more careful analysis is needed then another formatter and locator should be used. 

The resulting chart is shown below:
![deviation plot](/assets/deviation-plot-01.png)
