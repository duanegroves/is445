---
name: Ethnic Diversity at UIUC - Visualizations
tools: [HTML, vega-lite]
image: assets/pngs/bigfoot-visualizations.png
description: This visualization project takes a look at Ethnic Diveristy at UIUC. More specifically where students originate from primarily internationally, but also domestically for context.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Ethnic Diversity at UIUC - Visualizations

#### Creator: Duane Samsuri Groves

This is a series of data visualizations used for my Final Project as part of Data Visualizations, IS455, at the University of Illinois - Champaign Urbana. Created primarily with information sourced from/by the [Illinois Division of Management Information](https://www.dmi.illinois.edu/stuenr/), my aim is to provide infromation and context on raw data for the enrichment of discussions around diversity at UIUC. Though UIUC is widely considered as one of the most diverse colleges in the world, there is always room for improvement. With a past project I have looked at [Racial Diveristy at UIUC](https://duanegroves.com/Racial-Diversity-at-UIUC/), for this project I wanted to focus on something different that came up in conversations from the previous which whilst giving context for the previous can also stand by itself. This was looking at Ethnic Diversity at UIUC and where our students are coming from, as to have rich discussions it is not only important to have diversity of race but also ethnicity.

---

## Foreign Students by Country, Student Level, and Sex - Spring 2023

<vegachart schema-url="{{ site.baseurl }}/assets/json/ethnic_diveristy_at_UIUC_main.json" style="width: 100%"></vegachart>

This visualization is my central interactive visualization created using Vega-lite with data from the Illinois Division of Management Information. One aspect of ethnic diversity and understanding it with adjacency to UIUC is understanding the demographics of international students we have accepted. In this visualization we can do this by visualizing what countries we are primarily accepting international students from as well as of those students of a county what student level -undergraduate, graduate, or professor - and sex they are.

To do this one will interact with the left visualization to influence the visuals displayed in the right visualization. In the left visualization there is a map which which is displaying the total number of foreign students UIUC has from that country. This can be seen through the color scale of the visualization and the color of the specific country. An interesting detail to take note of is that the colorscale is a log type color scale. This is because there are a few countries which have so many forign students attending that if using a linear type all the other counts are indistinguishable. So to see any difference in color it has been implemented with a log type scale.

In addition the left visualization has a few interactive features implemented. The first and minor interactive element is the hover effect which displays a tooltip and basic information of a country when hovered over. This information consists of the country's name as well as the total number of students from that country. The second and more prominent interactive feature is the ability to select a visualization. When a country is selected the right visualization will display a standard barchart displaying information about students from the specific country. This information involves student level and sex.

Resource(s) Used:

- Illinois Division of Management Information's Forign Students by Country, Student Level, and Sex
  - Original: https://www.dmi.illinois.edu/stuenr/#foreign
  - Hosted: https://raw.githubusercontent.com/duanegroves/is445/main/countrysp23.csv
- world-110m-country-codes (used to map country names to a code which cordinates to the mapping of the country)
  - Original: https://github.com/alisle/world-110m-country-codes
- Altair World Map
  - Original: https://raw.githubusercontent.com/vega/vega-lite-v1/master/data/data/world-110m.json

## Contextual Visualizations

#### U.S. states hosting the most international students in the academic year 2021/22

<img src="{{ site.baseurl }}/assets/pngs/U.S. states hosting the most international students in the academic year 2021:2022.png">

Having now looked at the ethnic diveristy of international students studying at the Univeristy of Illinois - Champaign Urbana (UIUC) as of Fall 2023, I thought it would be interesting to add context to this visualization by slowly zooming out of the story and picture of just UIUC. In this visualization one will be able to look at the "U.S. states hosting the most internatoinal students." Provided by the Institute of International Education and posted on Statista this visualization will be our first step in ding so.

By looking at the visualization one will be able to see that Illinois is one of the top ten states that are hosting the most intenrational students. Listed in the middle of the ten at position five, Illinois is hosting 46,599 international students according to this dataset for 2021/22. To add aditional connective information, according to the Illinois Division of Management Information as of Fall 2021 UIUC was hositng a total 11,474 of these students.

Though this may or may not seem like a lot it tells the story that UIUC is still a major player and has a non-insigificant portion of the pie when it comes to deciding where the U.S. as a whole are taking in international students. Taking in almost half of state with the 10th most international students, Arizona, UIUC's statistics representation of diveristy has the possibility to impact the numbers of nationwide international student intake. At the same time, it has the power to persist inequitable trends.

Resource(s) Used:

- Institute of Internal Education. (n.d). U.S. states hosting the most international students in the academic year 2021/22. In Statista - The Statistics Portal. Retrieved Apr 25, 2023, from https://www.statista.com/statistics/237703/us-states-hosting-the-most-international-students/.

#### Number of international students studying in the United States in 2021/22, by country of origin

<img src="{{ site.baseurl }}/assets/pngs/International students in the U.S. by country of origin 2021:22.png">

So, where is the country of origin for international students studying in the United States nation-wide then? In this data visualization one is able to see that and continue the zoomout of the visualization speciallizing on UIUC. Now able to compare UIUC international student numbers with the national international student numbers, one can start to make comparisons between the two scopes.

Plotted as a horizontal bar chart with country names as the y axis and the number of students as the x axis, it is a different way of visualizing a similiar type of data that I am with the mapped visualization. As staged before, I did this so oen can visually see the country origins, as at least personally simply names don't aid me that much. However, one can still compare the two visualizations and datasets by comparing the numbers of students from each country through hovering in the above visualization or even looking at the color scale (though harder to do with granularity).

Something that I personally noticed through this investigation of comparing the data from the two visualizations is that the patterns seem to be widely the same. That is the order of countries by the most and least students widely mimic eachother with comparable margins between countries. China by far has the most international students with India coming up second at a little over half the number. Then South Korea comes third with a significantly larger percentage when compared with the fourth largest country in the order. After the third place none of the other countries perience much change in numbers in either visualization though the order of countries may differ. Something that may be interesting is comparing two treemap like visualizaitons of these datasets.

Resource(s) Used:

- Institute of Internal Education. (n.d). Number of international students studying in the United States in 2021/22, by country of origin. In Statista - The Statistics Portal. Retrieved Apr 25, 2023, from https://www.statista.com/statistics/233880/international-students-in-the-us-by-country-of-origin/.
-

#### Domestic Students by County - Fall 2022

<vegachart schema-url="{{ site.baseurl }}/assets/json/ethnic_diveristy_at_UIUC_context1.json" style="width: 100%"></vegachart>

For the third contextual data visualization it is another custom Vega-lite visualization with slight interactivity. Aiming to once again provide context for the main driving visualizating I instead wanted to take a zoomed in picture of UIUC for this. Instead of looking at broader information on the country of origin for international students I watned to specialize on UIUC and take a look at county of origin for domestic students at UIUC.

In a similar style as I had done with the main visualization this is a map of the United States wiht a AlbersUSA projection which is separated by County. Colored by Total number of students studying at UIUC from the specific county the counties are hoverable to provide more information such as name and total count. The color is once again provided in a log scale as to give more variation of color throughout the map.

There does exist a few improvements on this visualization that I would love to make if I were able to figure it out. The first improvement I would like to make would be to make this into a dashboard like visualizaiton like the main visualization. On the left hand side I would love to provide a map of the USA broken up by state and provide the aggregate sum of the state. This would be interactable to open up a right side panel of a zoomed into picture of a state broken down further in this case by County. The second improvement I would love to make is increase accurancy of this vizualization as it currently suffers from 2 faults. The first fault of accuracy is that some counties are inflated. This is because I translating from ZipCode to County and some zipcodes exist in multiple counties so some students are counted twice. The other fault of accuracy is that in mapping form zipcode to county not all are getting mapped properly as the intermediate dataset doing this mapping does not seem to contain all zipcodes perhaps. To fix this second issue of accuracy I would have to rethink my approach, there does not exist another to map zipcode to county and using the given Vega-lite geojson I can only separate by state or county. So I would likely have to use a third part dataset that just maps purely zipcodes. I believe this would fix my issue.

Resource(s) Used:

- Illinois Division of Management Information Enrollment by Zip-code
  - Original: https://www.dmi.illinois.edu/stuenr/#zip
  - Hosted: https://github.com/duanegroves/is445/blob/main/zipcds.fa22.csv
- Zipcodes to County FIPS (Used to map zipcodes to a code which coordinates to to the mapping of a county)
  - Original: https://www.kaggle.com/datasets/danofer/zipcodes-county-fips-crosswalk
  - Hosted: https://github.com/duanegroves/is445/blob/main/ZIP-COUNTY-FIPS_2017-06.csv
- Altair US Map
  - Original: https://raw.githubusercontent.com/vega/vega-lite-v1/master/data/data/us-10m.json

<div class="left">
{% include elements/button.html link="https://github.com/duanegroves/is445" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://starboard.gg/duanegroves/is445-final-project-part-3-nAFy6ih" text="The Analysis" %}
</div>
