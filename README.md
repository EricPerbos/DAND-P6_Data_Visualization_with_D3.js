# Data Visualization and D3.js - Data Analyst Nanodegree (Udacity) avec "#"

[Tesla Motors in Europe: a visualization of quarterly sales figures](https://bl.ocks.org/EricPerbos/raw/3c11acdcc679694bd6ba6c822dbdc0ef)

## Summary
Tesla Motors is a North American car company that designs, manufactures and sells electric vehicles all over the world (Wikipedia).

Providing an explicit picture of its European sales though one chart is intricate as countries vary widely in terms of absolute sales (from 25 to 2500 in a quarter), making a bar chart inadequate as one leading country will "dwarf" smaller ones in scale.

After initial research, we opted for circle's area as representation of sales.</br>After feedback, we added a small bar chart to show the "Sales per million of habitants" to show the local performance of each country marketwise.


## Design
Bar/column and line charts are useful to compare sales over time between several regions of similar size. But if you have more than five regions or the min-max values are disparate (ex: factor 1 to 10), they become overloaded and difficult to read.

In this project, we strongly exceed those limits with  12 countries with min-max values of 2 (Finland Q4-2013) and 2,086 (Norway Q1-2014).</br>Here's an exemple of column chart which demonstrate the issue.
<a href="http://tinypic.com?ref=2n0k8s2" target="_blank"><img src="http://i63.tinypic.com/2n0k8s2.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

We researched through different business publications and found circle size to be a better option, although with one potential pitfall due to the formula used to calculate its size or more accurately its area = Pi * r².</br>For example, a data value of 4 will create a circle with an area 16π.</br>A data value of 5 will create a circle with an area of 25π.

</br>This was brought to our attention during Udacity Data Visualization class, <b>Lesson 8.23 "How to lie with circles"</b> and the article [False Visualizations: When Journalists Get Data Viz Wrong](http://www.huffingtonpost.com/randy-krum/false-visualizations-when_b_5736106.html).</br>We followed the same principle by using <b>d3.scale.sqrt()</b> to get the square root of data values to determine the radius of each circle.


## First draft and feedback

<a href="http://tinypic.com?ref=2rxzeyo" target="_blank"><img src="http://i65.tinypic.com/2rxzeyo.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

<b>Feedback by Tesla shareholder #1:</b> "It's a nice visualization but why do you choose so many different colors so light on white background ? Also the name of countries on the right is counterintuitive"

<b>Change #1:</b> I switched the names to the right and opted for a dual color based on Tesla Motors website.


## Second draft and feedback

<a href="http://tinypic.com?ref=2poyu7l" target="_blank"><img src="http://i67.tinypic.com/2poyu7l.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

<b>Feedback by Tesla shareholder #2:</b> "The use of different diameter circles to signify volume is pretty clear (...) </br>Thinking about it a bit more, I think the strength of this dot graph is to show much more data points at the same time without losing track of which data point represents a certain country (...)</br>Also it seems the biggest sales are not located in largest countries, could you indicate the population size maybe ?"

<b>Change #2:</b> I added a small bar chart on the right, first with percentage of population vs. total population.</br>Then I reaslised that there was no direct connection between the two, Sales on one side, Population on the other.</br> So I computed a ratio "Sales per 1 million habitant" and changed the ranking order from alphabetical to Sales_per_1M_Hab, decreasing.


## Third draft and feedback

<a href="http://tinypic.com?ref=10mr4zm" target="_blank"><img src="http://i68.tinypic.com/10mr4zm.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

<b>Feedback by Tesla shareholder #3:</b>"I think that the circles are an effective use of real estate given how many countries are listed and the marked differences in sales in each. </br> If one were to compare Norway's sales to Italy, the real estate used on the graph by Norway would push Italy off the page.</br>The circles, in my mind's eye, are essentially looking at the bar graph from above. The bigger the bar, the closer it is to me, and larger and easier to see.

I like how at the end, Eric does use the bar chart to show sales per million inhabitants. It provides a nice juxtaposition of the bar graph in relation to the circles.

Overall I found the graphic very informative and useful to show how government incentives and changes affect Tesla sales in Europe (see Denmark)."




