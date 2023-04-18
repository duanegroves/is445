---
name: BigFoot Field Organization Research Report FA22 - Visualizations
tools: [Python, HTML, vega-lite, Altair, Pandas]
image: assets/pngs/bigfoot-visualizations.png
description: This is a "showcase" project that uses vega-lite for interactive viz!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# BigFoot Field Organization Research Report FA22 - Visualizations

## Visualization 1 (Meant to be the actual assignment - does not work with Altair)

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_visualization_p1.json" style="width: 100%"></vegachart>

After doing a geomteric visualization for this data in my [Homework 9](https://starboard.gg/duanegroves/INFO_445_Homework9-nsPtqwW), I knew I really wanted to take another stab at it and utilize lessons from my previous experience. In the old visualization I was attempting to show the different reports by location with some indication of another feild. What that feild ended up being at the time was the recorded humidity as the color of points on a projection of the United States of America. However, after I created the visualization it was hard to extract as much information as I wanted to; it seemed like a lot of the points where in the same place and the darkest color on the color scale would just overshadow the rest. So my idea was to change scope a little to better be able to highlight what I wanted to see, as I did not necessarily care about the exact pinpoint location. What I decided I wanted to do was to plot the map by state where I could click on a state and get more granular detail about another feild. That is I wanted to plot a geometric map of the United States where each state is colored by its frequency of reports - how many reports it had - and be able to click on it to get more details like a dashboard. The additional details I went with for this runthrough was the season of the reports though it could be anything once I figured out how to do the right visualization's filtering by state.

This took a lot of time to figure out and was my first step into insanity with this homework assignment. What I would learn is that as much as D3.js is tedious, I hate high-level labraries as you are confined within the constrants of what the developers allow you to do and how they want you to do it. Without any granularity in what I could do I struggled on this for hours. From figuring out how to combine my Bigfoot data with their geojson dataset for the United States to color by state (after an hour of scrolling through their dataset I understood that in one part of the dataset they where seperating out the states by an id which I then had to map to each state), to figuring out how to click on an individual state and then pass whatever state that is to the second linked visualization (After hours of toiling around I realized the default use of params as we had in class generates a vgsid that then is passed to the second visualization can be used simply if the two datasets are the same. However, the data required to make the two visualizations were distinct in my case, so I had to use a custom vgsid. Yet you can't really access the vgsid itself so I had to create an object that would be updated with feilds that I would be able to access in the second function). Long story short high-level visualizations libraries are nice if you are doing something simple and standard (or know every detail of the library), however, if not it is horrible.

Oh in addition, the second part of my insanity is that the map part of the visualization is impossible to do with Altair and their ".from_json" or ".from_dict". I did not spend as much time on this problem as my others since by this time I felt a little defeated by everything, however I tried to follow their errors and fix stuff up as much as I could but had no luck at all. It is something with the decoding and not liking the colors on my map. This error is not shown in the .from_json as it doesn't say anything in the error log until the end throwing a decoding error, but in the .from_dict the error log it does point to the color object which by all that I can imagine is fine. For at least it works in Vega-Lite itself. This error and another error that I will talk about in Visualization 2 brings to me think this is another high-level library built upon vega-lite's already high level library in which Altair decodes stuff down into Vega-lite with their own certain rules which **BLOODY INFIRIATES ME**.

Never-the-less, in the visualization itself the variable that I am using to color on the map is frequency as I still wanted to visualize where the reports are happening and I am using this color scheme mostly because it is the default but also because I find it appealing to my eyes. The color is a qualitative type so as long as it is a gradient it is fine. Then for the part of the visualization by season I am doing a vertical barchart because that is what I personally like and this entails a x axes of ordinal season and an y axes of quantitative by frequency/count.

Resources Used:

- https://stackoverflow.com/questions/62272376/vega-lite-map-not-showing-up-with-no-error
- https://vega.github.io/editor/#/examples/vega/heatmap

## Visualization 2 (Meant to be the actual assignment - does not work with Altair)

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_visualization_p2.json" style="width: 100%"></vegachart>

While I was reading all the documentation there on Vega-lite for the first visualization I came across an interesting visualization they had in their documentation where they had several scatter plots beside eachother where you could interact with one to highlight the same points on the rest of the scatter plots. I thought this was a very interesting idea to try to find patterns across column/properties of the dataset. This is because not only can one see patterns in the data by just plotting the various scatter plots in the different ways, but also because by highlighting a section of the data one can see patterns across similar types of rows. I found this super interesting and fun to mess around with. Though unfortunately because I wanted to plot all possible combinations (except for temperature) and kill everyone's computers it does take a noticable amount of time to do this. I may create a smaller subset of this visualization to be easier to play around with.

In addition, though this scatter plot was able to map (unlike the map) with .from_json, I am unable to save it from what I believe is Altair's decoding methods. If I try to save it the code states an "Invalid specification" error saying that my repeat property requires a nested property, repeat.layer. Though this is not required by Vega-lite at all if I oblige and add repeat.layer to be the classification (as it just makes the classification as a layer seemingly changing nothing), it states another "Invalid specification" error where repeat.layer is unexpected. I am caught in a constant loop, and quite frankly given all the errors with everything I gave up.

Never-the-less, I chose a scatter plot for this visualization due to its versitiility as I wanted to keep all of the plot consistent as deviation would take away from the ability to recongize patterns. In addition, I made the choice to only choose quantitative columns as other this type of visualization aids them the most. I thought about adding ordinal columns as well, however, they were less interesting and I already had enough plots listed xD. As for the color it was because ILL and they were a nice default color. Though the red can possibly be thought of hard to see be hard to see, it is actually because they are not really there. There are very few class C reports.

Resources Used:

- https://vega.github.io/vega-lite-v2/docs/selection.html

## Additional Visualizations

In case that my first two visualizations won't be accepted due to them being impossible to create with Altair, the following two will just be so I can assure I meet requirements of the assignment.

### Visualization 3 (Altair Created)

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_visualization_p3.json" style="width: 100%"></vegachart>

This visualization was initially meant to be the same as visualization 2, however, containing 2 graphs and created purely with Altair function. After looking at the documentaion for Altair I saw an example plot that was similar to visualization 2 and thought I would give it a shot as it might help me understand how Altair abstracts or utilizes Vega-lite. Though I was able to create this visualization using just Altair and Python (as you will be able to see in the notebook), I was unable to extract it due to Altairs .save() function not supporting the use of a selection inside a color property of the chart. So in order to export it I had to leave our the grey-ing out of the feilds not selected. In addition, when I took it the use of the selector in the color property it stated that alt.Chart.data was a required property in the decoding which I have not even seen used before. So I just kept it down to one graph.

Never-the-less, all of the design choices for this visualization are shared with Visualization 2 and I chose to just focus on the relationship between cloud coverage and percipitation probability as I thought there would be a correlation. Both the x and y parameters in the dataset are numerical so I quantitative. In addition in terms of the colors I once again chose the default coloring because I like our school colors and I chose to color the classification feild.

Resources Used:

- https://altair-viz.github.io/altair-viz-v4/user_guide/interactions.html#conditions-making-the-chart-respond

### Visualization 4 (Altair Created with Interaction)

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_visualization_p4.json" style="width: 100%"></vegachart>

Because I was unable to get any interactivity working with an Altair Created Visualization I really needed to get one working on this one. When I created my plot for homework 9 I where I plotted all the report locations on a map of the United States of America I thought it would be interesting if I could implement a tooltip with it so I knew what I was hovering. When I saw an example of this being done in the Altair documentation I really wanted to revisit the homework 9 visualization and try it out. So this graph is demonstrating the location of all the Bigfoot Reportings in the US and has a tooltip which tells you some information about the report being hovered. Colored by classification this was more for consistency at this point.

In terms of transformations I filter out all reports where longitudea nd latitude where not valid. This was because they were all being placed in the top left hand corner of the plot. I used pandas to remove these, however, there still seems to be points in the corner of the plot and I am not sure why. Using purely Vega-lite as in Homework 9 this was not a problem, and I have looked at the points that are being plotted there. They state they are in states and have alright longitude and latitude values. I could go manually and remove them all, however, that would take time and I don't know what is causing it. I feel like it is another thing of Altair being broken. I would possibly spend more time on this however, I am irritated by this assignment and due time is almost here.

In terms of reused code from Homework 9 there was not really any except the concepts gained from doing the assignment.

Resources Used:

- https://altair-viz.github.io/altair-viz-v4/gallery/us_state_capitals.html
- https://altair-viz.github.io/altair-viz-v4/gallery/one_dot_per_zipcode.html

<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_bcubcg_fall2022/blob/main/data/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/duanegroves/is445/blob/main/python_notebooks/bigfoot_visualizations.ipynb" text="The Analysis" %}
</div>
