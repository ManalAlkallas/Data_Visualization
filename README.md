# Visualization

### - There are two main reasons for creating visuals using data:

  - **Exploratory analysis** is done when you are searching for insights. These visualizations don't need to be perfect. You are using plots to find insights, but they don't need to be aesthetically appealing. You are the consumer of these plots, and you need to be able to find the answer to your questions from these plots.


  - **Explanatory analysis** is done when you are providing your results for others. These visualizations need to provide you the emphasis necessary to convey your message. They should be accurate, insightful, and visually appealing.

### -The five steps of the data analysis process:
  1. Extract - Obtain the data from a spreadsheet, SQL, the web, etc.
  2. Clean - Here we could use exploratory visuals.
  3. Explore - Here we use exploratory visuals.
  4. Analyze - Here we might use either exploratory or explanatory visuals.
  5. Share - Here is where explanatory visuals live.
  
 ### - **Python Data Visualization Libraries** 
  1. **[Matplotlib](https://matplotlib.org/)**: a versatile library for visualizations, but it can take some code effort to put together common visualizations.
  2. **[Seaborn](https://seaborn.pydata.org/)**: built on top of matplotlib, adds a number of functions to make common statistical visualizations easier to generate.
  3. **[pandas](https://pandas.pydata.org/)**: while this library includes some convenient methods for visualizing data that hook into matplotlib, we'll mainly be using it for its main purpose as a general tool for working with data.
  All together, these libraries will allow you to visualize data in a balance of productivity and flexibility, for both exploratory as well as explanatory analyses.

# Design of Visualizations
The important aspects regarding the design of visualizations:

## The Four Levels of Measurement
In order to choose an appropriate plot type or method of analysis for your data, you need to understand the types of data you have. One common method divides the data into four levels of measurement:

- **Qualitative or categorical types** (non-numeric types)
 1. **Nominal data**: pure labels without inherent order (no label is intrinsically greater or less than any other), Ex. movie Genre "Action, Comedy,.." or countries "Chine, USA, Germany.."
 2. **Ordinal data**: labels with an intrinsic order or ranking (comparison operations can be made between values, but the magnitude of differences are not be well-defined) Ex. Letter Grades: A > B > C OR Ranking 1<sup>st</sup> > 2<sup>nd</sup>  > 3<sup>rd</sup> 
- **Quantitative or numeric types**
Quantitative data take numerical values that allow for mathmetical operations
 3. **Interval data**: numeric values where absolute differences are meaningful (addition and subtraction operations can be made) Ex, Years or Tempreature
 4. **Ratio data**: numeric values where relative differences are meaningful (multiplication and division operations can be made)</br>
 
 ![data-type](data-type.png)

 - All quantitative-type variables also come in one of two varieties: **discrete** and **continuous**.
    - **Discrete** quantitative variables can only take on a specific set values at some maximum level of precision.
    - **Continuous** quantitative variables can (hypothetically) take on values to any level of precision.
  
Distinguishing between continuous and discrete can be a little tricky – a rule of thumb is if there are few levels, and values can't be subdivided into further units, then it's discrete. Otherwise, it's continuous. If you have a scale that can only take natural number values between 1 and 5, that's discrete. A quantity that can be measured to two digits, e.g. 2.72, is best characterized as continuous, since we might hypothetically be able to measure to even more digits, e.g. 2.718. A tricky case like test scores measured between 0 and 100 can only be divided down to single integers, making it initially seem discrete. But since there are so many values, such a feature is usually considered as continuous.</br>


```
When exploring your data, the most important thing to consider first is 
whether your data is qualitative or quantitative, discrete or continuous.

```

## Visual Encodings
Experts and researchers have determined the types of visual patterns that allow humans to best understand certain information. In general, humans are able to best understand data encoded with **positional changes** (differences in x- and y- position) and **length changes** (differences in box heights). </br>

Alternatively, humans struggle with understanding data encoded with **color hue changes** and **area changes**</br>

**Chart junk** refers to all visual elements in charts and graphs that are not necessary to comprehend the information represented on the graph or that distract the viewer from this information.

- Examples of chart junk you saw in this video include:
  - Heavy grid lines
  - Unnecessary text
  - Pictures surrounding the visual
  - Shading or 3d components
  - Ornamented chart axes

The **data-ink ratio**, credited to Edward Tufte, is directly related to the idea of chart junk. The more of the ink in your visual that is related to conveying the message in the data, the better.

```
Limiting chart junk increases the data-ink ratio.
```

## Design Integrity
It is key that when you build plots you maintain integrity for the underlying data.</br>

One of the main ways discussed here for looking at data integrity was with the **lie factor**. Lie factor depicts the degree to which a visualization distorts or misrepresents the data values being plotted. The lie factor is the relative change shown in the graphic divided by the actual relative change in the data. Ideally, the lie factor should be 1: any other value means that there is some mismatch in the ratio of depicted change to actual change.

```

Any lie factor different than 1 suggests that a visual is distorting the data. 
When the factor is greater than 1, we are making an effect larger than it actually is 
and factors less than 1 are hiding the magnitude of an effect.

```
Flowing Data: [How to Spot Visualization Lies](https://flowingdata.com/2017/02/09/how-to-spot-visualization-lies/) </br>

## Using Color
Color can both help and hurt a data visualization. Three tips for using color effectively.
  - Before adding color to a visualization, start with black and white.
  - When using color, use less intense colors - not all the colors of the rainbow, which is the default in many software applications.
  - Color for communication. Use color to highlight your message and separate groups of interest. Don't add color just to have color in your visualization.

# Exploration of Data
## Univariate visualizations:
Exploration starts with univariate visualizations to identify trends in distribution and outliers in **single variables**. </br>

```
Bar charts for qualitatuve variabes
Histograms for quantitive variables
```
### Bar charts 
[Bar Chart Practice](Bar_Chart_Practice.ipynb)  

### Pie Charts
A **pie chart** is a common univariate plot type that is used to depict relative frequencies for levels of a categorical variable. Frequencies in a pie chart are depicted as wedges drawn on a circle: the larger the angle or area, the more common the categorical value taken.
- Unfortunately, pie charts are a fairly limited plot type in the range of scenarios where they can be used, and it is easy for chart makers to try and spice up pie charts in a way that makes them more difficult to read. If you want to use a pie chart, try to follow certain guidelines:
  - Make sure that your interest is in relative frequencies. Areas should represent parts of a whole, rather than measurements on a second variable (unless that second variable can logically be summed up into some whole).
  - Limit the number of slices plotted. A pie chart works best with two or three slices, though it's also possible to plot with four or five slices as long as the wedge sizes can be distinguished. If you have a lot of categories, or categories that have small proportional representation, consider grouping them together so that fewer wedges are plotted, or use an 'Other' category to handle them.
  - Plot the data systematically. One typical method of plotting a pie chart is to start from the top of the circle, then plot each categorical level clockwise from most frequent to least frequent. If you have three categories and are interested in the comparison of two of them, a common plotting method is to place the two categories of interest on either side of the 12 o'clock direction, with the third category filling in the remaining space at the bottom.
  
If these guidelines cannot be met, then you should probably make use of a bar chart instead. A bar chart is a safer choice in general. The bar heights are more precisely interpreted than areas or angles, and a bar chart can be displayed more compactly than a pie chart. There's also more flexibility with a bar chart for plotting variables with a lot of levels, like plotting the bars horizontally.

You can create a pie chart with matplotlib's pie function. This function requires that the data be in a summarized form: the primary argument to the function will be the wedge sizes.
```
# code for the pie chart seen above
sorted_counts = df['cat_var'].value_counts()
plt.pie(sorted_counts, labels = sorted_counts.index, startangle = 90,
        counterclock = False);
plt.axis('square')

```
To follow the guidelines in the bullet points above, I include the "startangle = 90" and "counterclock = False" arguments to start the first slice at vertically upwards, and will plot the sorted counts in a clockwise fashion. The axis function call and 'square' argument makes it so that the scaling of the plot is equal on both the x- and y-axes. Without this call, the pie could end up looking oval-shaped, rather than a circle.

### Additional Variation
A sister plot to the pie chart is the **donut plot**. It's just like a pie chart, except that there's a hole in the center of the plot. Perceptually, there's not much difference between a donut plot and a pie chart, and donut plots should be used with the same guidelines as a pie chart. Aesthetics might be one of the reasons why you would choose one or the other. For instance, you might see statistics reported in the hole of a donut plot to better make use of available space.

To create a donut plot, you can add a "wedgeprops" argument to the pie function call. By default, the radius of the pie (circle) is 1; setting the wedges' width property to less than 1 removes coloring from the center of the circle.

```
sorted_counts = df['cat_var'].value_counts()
plt.pie(sorted_counts, labels = sorted_counts.index, startangle = 90,
        counterclock = False, wedgeprops = {'width' : 0.4});
plt.axis('square')

```

### Histograms
A histogram is used to plot the distribution of a numeric variable. It's the quantitative version of the bar chart. However, rather than plot one bar for each unique numeric value, values are grouped into continuous bins, and one bar for each bin is plotted depicting the number. For instance, using the default settings for matplotlib's ```hist``` function:

```

plt.hist(data = df, x = 'num_var')

```
By default, the ```hist``` function divides the data into 10 bins, based on the range of values taken. In almost every case, we will want to change these settings.

[Histogram Chart Practice](Histogram_Practice.ipynb)  


## Bivariate visualizations
Bivariate visualizations follow, to show relationships between variables in the data. 

## Multivariate visualization
Multivariate visualization techniques are presented to identify complex relationships between three or more variables at the same time.

# Explanatory Visualizations (Lesson 6)
This lesson describes considerations that should be made when moving from exploratory data analysis to explanatory analysis. When polishing visualizations to present to others, you will need to consider what findings you want to focus on and how to use visualization techniques to highlight your main story. This lesson also provides tips for presentation of results and how to iterate on your presentations.

#  Visualization Case Study (Lesson 7)
In this lesson, you will bring together everything from the previous lessons in an example case study. You will be presented with a dataset and perform an exploratory analysis. You will then take findings from that analysis and polish them up for presentation as explanatory visualizations.
