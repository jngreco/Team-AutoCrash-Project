# Team AutoCrash - Chicago Car Crash Data Analysis

<h3> HvPlot and Geoviews Visualizations - Jess Greco


<h5> In an effort to better understand and visualize car crash data in Chicago, five maps were created using HvPlot and Geoviews. The intitial dataset was filtered down to recorded crashes from the last five years (2018-2022) in order to acheive a clear and cohesive map. There were a total of 930,155 crashes from 2018-2022. The vast majority of crashes, or 794,650 (85.4%), resulted in no indication of injury, followed by 76,512 (8.2%) non-incapacitating injuries, 42,275 (4.5%) reported but nonevident injuries, 15,757 (1.7%) incapacitating injuries, and 961 (0.1%) fatal injuries.

A map was created to display the locations of the 961 fatal injuries from 2018-2022. Points were plotted and displayed by primary contributory cause. Of the crashes, 143 involved the car make Chevrolet. The majority of crashes (243) had a primary contributory cause that was unable to be determined at the time of the crash. Points are dispersed fairly evenly throughout the map, with no clear clusters. 

Another map displaying fatal chrases involving the car make Chevrolet was created. Primary contributory cause was, again, mostly unable to be determined at the time of the crash (28), followed closely by "Disregarding Traffic Signals" (24). 

Next, two maps were created displaying fatal collisions and collisions resulting in non-incapacitating injuries from the past year. In 2022, there were a total of 184,055 collisions, with 223 fatal (0.12%) and 15,621 non-incapacitating (8.5%) injuries as a result. This mirrors the five year trend in which fatal collisions make up only a small percentage of overall collisions in the city. Only non-incapacitating injuries were mapped to maximize the clarity of the plotted points. A dataframe was then created to compare the following variables for each collision type: Car Make, Zipcode, Primary Contributory Factor, Lighting Condition, Posted Speed Limit, and Damages. 

In both fatal and non-incapacitating collisions, Chevrolet appeared most frequently (13.5% and 13%, respectively). The majority of fatal collisions (7.2%) and non-incapaciating collisiions (4.4%) took place in the zipcode 60619. It should be noted that, with such low percentages, a correlation is unlikely. The primary contributory factor, after "unable to determine" for fatal collisions was "Physical Condition of Driver" (15.2%) and "Failing to Yield Right-of-Way" (18.3%) for non-incapaciating collisions. Over half (52%) of fatal collisiona took place in "Darkness, Lighted Road", while 60% of non-incapacitating crashes took place in "Daylight". 77% of fatal crashes, and 78.3% of non-incapacitating crashes, occured in locations where the posted speed limit was 30mph. 93% of fatal collisions involved monetary damages over $1,500, compared to 83% of non-incapacitating crashes. Preliiary analysis of these numbers suggests a correlation between lighting condition, posted speed limit, damages and the severity and frequency of car crashes with respect to each variable; however, we cannot definitively state the nature or significance, if any, of these relationships without further analysis and statistical testing, which will be covered later on.  

Finally, the three locations that appear most frequently in the data were calculated to determine where the majority of accidents (all injury types) occured from 2018-2022. Using Google Maps and longitude/latitude coordinates from the dataset, points were plotted on a map to better visualize these locations. The most commons location for vehicle crashes is O'Hare International Airport (1,505), followed by the S-Curve of Lakeshore Drive below Oak Street Beach (795), and the Museum of Science and Industry (655). We can hypothesize that these points appear the most frequently throughout the data due to the high volume of traffic, including out-of-state tourism, at each location. 
  
While the maps do not tell us with any degree of certainty what variables play a statistically significant role in both frequency and severity of vehicle collisions in Chicago, they do serve as a valuable tool for visualizing patterns and creating hypothesis for further investigation, which we discuss below. 
  
<h3> Auto Fatalities by Road Attribute - Number of Lanes and Posted Speed Limit - Michael O'Leary

<h5> In the Chicago_Data-Road-Attributes notebook, we pulled in all Chicago traffic crash data from the City of Chicago.  We filtered by the years 2018 - 2022, to ensure we have complete years for comparison and because more recent years have better data quality.  We examined the data to find what elements had value and discarded the rest, and we merged the datasets together into a single dataframe, and we renamed columns for clarity, and we cleansed data and filtered for scope.  

After cleansing, we looked at crashes, injuries and fatalities by number of lanes and found that 88% of crashes occurred on 2 or 4 lane loads - likely representing more the makeup of Chicago roadways than anything stitically valid.  We could test this if we could find the number of Chicago lane-miles of each type of road, but that data didn't appear to be available.  

We continued by looking at Chicago injuries and fatalities by number of lanes, and found that the vast majority of auto crashes did not result in injury for any number of lanes.  

Then we looked at the percentage of crashes by number of lanes which resulted in injuries of various severities, incuding fatalities.  Here we found that the percentage of crashes resulting in injuries - especially severe injuries - increased with the number of lanes.  However, there didn't appear to be a correlation between the number of lanes and fatalities.  

Next, we moved on to look at injuries and fatalities as related to the posted speed limits.  What observed that severe injuries rose with speed limit up to 40 miles per hour, then declined - and fatalities didn't show a correlation with speed limit.  

Finally, we took a look at the auto fatalies per capita in Chicago vs. the national average - and found that Chicago is signifigantly safter than the national average - with Chicago being 29% safer than the national average in 2021.  

<h3> Zip Code and Vehicle Make/Year Analysis - Connor Thomas


<h5> In the Zipcodes Python notebook, we use the latitude and longitude information stroed for each crash to merge our dataset together with geographical data from <https://www.arcgis.com/home/item.html?id=8d2012a2016e484dafaac0451f9aea24>. This allows us to add the zip code along with population data for each of our crash locations. Now grouping by zip codes, we are able to find the number of crashes and average injury/fatality rates for each of the zip codes in our dataset to visualize with bar and scatter plots.

First looking simply at the number of crashes for each zip code, we can see the zip codes with the highest number of crashes (60629, 60619, 60632, 60620) are all clustered around either highway interchange I-57/I-94 or Midway airport. This can very likely be explained by the large volume of traffic flowing through these areas along with the atypical paths vehicles may be travelling on compared to a normal road.

Looking next at average fatalities per crash for each zip code, we can see a large spike in 60633, 60636, and 60617. Checking our means with Python's ANOVA test, we obtain  **test statistic: 6.898** and **pvalue: 7.509e-51**, thus confirming a significant difference in fatality rates for Chicago's zip codes. Like the last set of zip codes with high total crashes, the high outliers here are also clustered near highway interchange I-57/I-94. Further investigation would be needed to see what may be causing these differences compared to the rest of our data.

After evaluating our information for each zip code individually, we then focused on differences in injuries/fatalities tied to population and population density. Creating scatter plots comparing both population and population density to total number of crashes and total, severe, and fatal injury rates, we were able to find a number of significant correlations within our data. The first is between Population and Number of Crashes. This is strong correlation with **r-value: 0.761** and **p-value: 1.394e-15**, and is not unexpected, as a higher number of residents would very liekly be tied to both a higher number of cars on the road and a higher number of crashes. We also see a correlation when looking at Population Density and Number of Crashes. This time, however, it is a negligible correlation with **r-value: 0.260** and **p-value: 0.023**. This, again, could be explained with similar reasoning as before, but with an understandably smaller impact as we have normalized by area for each zip code. Finally, we obtain another negligible correlation between Population Density and Average Injuries per Crash with **r-value: -0.254** and **p-value: 0.027**. This time, however, we have a slight negative correlation whereas the previous two were both positive. This slight downward trend could be partially explained by places with higher population densities having slower rates of travel due to heavy traffic. Thus, while there may be a large number of crashes in highly populated areas, they are less likely to head to injury.

Next looking at vehicle makes, we filtered our data down to a subset including the major manufacturers (Chevrolet, Ford, Nissan, Honda, Toyota, Dodge, Hyundai, Jeep, Volkswagen, Chrysler, Buick, Lexus, Tesla) to then group our data and find the total recorded number of crashes and injury/fatality rates for each vehicle make in our list. Taking an initial look at the total number of recorded crashes for each vehicle make, we see most of our data comes from Chevrolet, Toyota, Ford, and Nissan. This is less likely to be tied to any safety-value of these manufacturers, but instead simply due to their overall popularity.

Looking at the injury and fatality rates for recorded crashes from each of these vehicle makes, we can see a large disparity for both rates between the highest and lowest values from our data. For injury rate, we have a minimum at **Tesla: 0.162** and maximum at **Chrysler: 0.235**. Running an ANOVA test here we obtain **test statistic: 32.787** and **pvalue: 9.638e-77**, confirming that there is a significant difference between the injury rates for our different vehicle makes. Similarly for fatality rate, we again have a minimum with **Tesla: 0.0005** and maximum with **Chrysler: 0.0018**. Running another ANOVA test, we obtain **test statistic: 2.317** and **pvalue: 0.006**, again confirming a significant difference between the fatality rates for our different vehicle makes.

Looking further at the vehicle makes with the highest injury rate and fatality rates, for both cases the top 4 are Dodge, Chevrolet, Buick, and Chrysler, with Chrysler coming in at the maximum in both cases as seen above. While this initial inquiry may not tell us why these vehicle makes have a significantly higher injury and fatality rate than their competitors, it does provide us with a useful baseline for further investigation into the saftey standards present for these vehicles and what may be lacking compared to others.

Finally grouping our data be Vehicle Year, we can again examine the total number of crashes along with the injury and fatality rates across the different years of manufacture in our dataset. With this grouping, however, we are hindered by the fact that a large majority of vehicles on the road will have been made within the last few decades. Thus our non-normalized data will be skewed towards the most recent years of manufacture in particular. This can be seen in our bar chart for Total Number of Crashes by Vehicle Year. Incidentally, there is a dip in values around 2009-2010 before it picks back up to the usual rate.  This may potentially be explained by the economic recession that took place during that time period, which could have led to less purchase of cars from those specific years until the economy improved again.

Looking at the injury and fatality rates for each of these years, however, we cannot find any significant trends within our data. This may contradict our initial assumption that vehicle safety should improve over time, but that may also have been partially influenced by our skewed dataset. Further inquiry with a wider timeframe would be necessary to draw conclusions.

# Age & Gender Relationships - Paul Brown
##### This is a brief overview of the relationships of age and gender to car crash data. # The data was pulled from the City of Chicago Data Portal at https://data.cityofchicago.org/ , # and focuses on the most recent complete year, 2022. # For this exercise, I merged vehicle and driver CSV files from the City of Chicago Data Portal, and cleaned them with the following actions: Removing rows for gender with unknown variables to reduce it to a binary value. The data provided on the portal was more akin to NaN or unknown values, rather than any specific non-binary association. # I also removed outliers from the age data, where the data most likely represented input errors again, such as negative age values (-47) or values too high to be plausible (130). # Data was also limited to the previous five years, as this allowed a small enough dataset to manipulate, while mitigating PC errors associated with low memory.
