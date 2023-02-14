# Team AutoCrash - Chicago Car Crash Data Analysis

<h3> HvPlot and Geoviews Visualizations - Jess Greco /n

In an effort to better understand and visualize car crash data in Chicago, five maps were created using HvPlot and Geoviews. The intitial dataset was filtered down to recorded crashes from the last five years (2018-2022) in order to acheive a clear and cohesive map. There were a total of 930,155 crashes from 2018-2022. The vast majority of crashes, or 794,650 (85.4%), recorded no indication of injury, followed by 76,512 (8.2%) non-incapacitating injuries, 42,275 (4.5%) reported but nonevident injuries, 15,757 (1.7%) incapacitating injuries, and 961 (0.1%) fatal injuries. 

A map was created to display the locations of the 961 injuries from 2018-2022. Points were plotted by primary contributory cause. Of the crashes, 143 involved the car make Chevrolet. The majority of crashes (243) had a primary contributory cause that was unable to be determined. Points are dispersed fairly evenly throughout the map, with no clear clusters. 

Another map displaying fatal chrases involving the car make Chevrolet was created. Primary contributory cause was, again, mostly unable to be determined (28), followed closely by "Disregarding Traffic Signals" (24). 

Next, two maps were created showing fatal collisions from the last year (2022) and collisions resulting in non-incapacitating injuries. In 2022, there were a total of 184,055 collisions, with 223 fatal (0.12%) and 15,621 non-incapacitating (8.5%). This mirrors the five year trend in which fatal collisions make up only a small percentage of overall collisions. Only non-incapacitating iinjuries were mapped to maximize the clarity of the plotted points. A dataframe was created to compare the following variables for each collision type: Car Make, Zipcode, Primary Contributory Factor, Lighting Condition, Posted Speed Limit, and Damages. 

In both fatal and non-incapacitating collisions, Chevrolet was involved in the majority of collisiions (13.5% and 13%, respectively). The majority of fatal collisions (7.2%) and non-incapaciating collisiions (4.4%) took place in the zipcode 60619. The primary contributory factor, after "unable to determine" for fatal collisions was "Physical Condition of Driver" (15.2%) and "Failing to Yield Right-of-Way" (18.3%) for non-incapaciating collisions. Over half of fatal collisions (52%) took place in "Darkness, Lighted Road", while 60% of non0incapacitating crashes took place in "Daylight". 77% of fatal crashes, and 78.3% of non-incapacitating crashes, occured in locations where the posted speed limit was 30mph. 93% of fatal collisions involved monetary damages over $1,500, compared to 83% of non-incapacitating crashes. Overall, we can hypothesize that lighting condition may contribute to the severity of injury in a crash.

Finally, the top three locations were examined to determine where the majority of accidents (all injury types) occured from 2018-2022. Using Google Maps and coordinates from the data, points were plotted on a map to visualize these locations. The most commons location is O'Hare International Airport (1,505), followed by the S-Curve of Lakeshore Drive below Oak Street Beach (795), and the Museum of Science and Industry (655). 
  
  
  
