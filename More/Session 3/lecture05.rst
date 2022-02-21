Lecture 5
=========

Let's start out easy by visualizing some data.

.. raw:: html

   <iframe src="_static/visualization.html" width="700px" height="500px"></iframe>

Here are some examples of visualizing the Titanic data sets:

`https://medium.com/datadriveninvestor/data-visualization-5b1dc260c91a <https://medium.com/datadriveninvestor/data-visualization-5b1dc260c91a>`_

`http://www.eamonfleming.com/projects/titanic.html <http://www.eamonfleming.com/projects/titanic.html>`_

.. note:: **Assignment 5**

    Read `5 Quick and Easy Data Visualizations in Python with Code <https://towardsdatascience.com/5-quick-and-easy-data-visualizations-in-python-with-code-a2284bae952f>`_.

    Try to run the scripts in a Jupyter notebook and play around with the scripts.


plot() kind - 11 Types of plot can be created
---------------------------------------------

- "area" is for area graphs - where area between axis and the line is shaded - helps compare quantities over time
- "bar" is for vertical bar charts. These are for categorical data to compare against 1 other variable, can compound bars in groups
- "barh" is for horizontal bar charts. As above but can be useful if category names are long or there are many of them
- "box" is for box plots. Sometimes called a 'Box and whisker plot' - show min/max median and interquartile range - shows similar data to a histogram
- "hexbin" is for hexbin plots. A clever way to handle scatter plots with large numbers of data points
- "hist" is for histograms. Used for quantitative data - superficially similar to a bar chart but continuous and box widths can be different
- "kde" is for kernel density estimate charts. Helps to see the shape of noisy data that follows a non-standard distribution - the kernel value is key
- "density" is an alias for "kde". If the kernel value changes so does the shape of the distribution - needs to be selected carefully
- "line" is for line graphs. Shows changes in continuous data (usually over time)
- "pie" is for 2D pie charts. Shows proportions of a sample of categories
- "scatter" is for scatter plots. Show relationships between continuous variables when one or both are independent and correlation between them
