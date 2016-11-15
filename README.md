# Data Visualization and D3.js - Data Analyst Nanodegree (Udacity) avec "#"

[Tesla Motors in Europe: a visualization of quarterly sales figures](https://bl.ocks.org/EricPerbos/raw/3c11acdcc679694bd6ba6c822dbdc0ef)

## Summary
Tesla Motors is a North American car company that designs, manufactures and sells electric vehicles all over the world (Wikipedia).

Providing an explicit picture of its European sales though one chart is intricate as countries vary widely in terms of absolute sales (from 25 to 2500 in a quarter), making a bar chart inadequate as one leading country will "dwarf" smaller ones in scale.

After initial research, we opted for circle's area as representation of sales.

After feedback, we added a small bar chart to show the "Sales per million of habitants" to show the local performance of each country marketwise.

## Design
Bar/column and line charts are useful to compare sales over time between several regions of similar size. But if you have more than five regions or the min-max values are disparate (ex: factor 1 to 10), they become overloaded and difficult to read.

In this project, we strongly exceed those limits with  12 countries with min-max values of 2 (Finland Q4-2013) and 2,086 (Norway Q1-2014). Here's an exemple of column chart which demonstrate the issue.

<a href="http://tinypic.com?ref=2v8pn9u" target="_blank">
<img src="http://i68.tinypic.com/2v8pn9u.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

We researched through different business publications and found circle size to be a better option, although with one potential pitfall due to the formula used to calculate its size or more accurately its area = Pi * r².

This was brought to our attention during Udacity Data Visualization class, Lesson 8.23 "How to lie with circles" and the article [False Visualizations: When Journalists Get Data Viz Wrong](http://www.huffingtonpost.com/randy-krum/false-visualizations-when_b_5736106.html).

We followed the same principle by using <b>d3.scale.sqrt()</b> to get the square root of data values to determine the radius of each circle.




