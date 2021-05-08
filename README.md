# Baltimore City Food Insecurity Exploration

## Background
Food insecurity is a concerning issue in many urban environments, including Baltimore City. It increases residents’ risk of chronic illness and causes extreme stress and burden. Black and low-income Americans are disproportionately affected by food insecurity. Fundamentally, not addressing this problem will lead to continually worse health outcomes in Baltimore’s most vulnerable residents and worsen racial disparities by inhibiting the access of communities of color to basic necessities.  This project uses neighborhood-level Baltimore data to analyze what factors contribute to food insecurity and how these factors relate to health outcomes. This project also analyzes how these trends may differ across neighborhoods in Baltimore. This detailed analysis will allow policymakers to take targeted, nuanced approaches to food insecurity in the city and avoid the possibility of drawing blanket conclusions that will not serve the most vulnerable populations. Policymakers should use the analysis provided to optimize resource allocation to neighborhoods that are at greatest risk for poor health outcomes due to food insecurity.

## Business Question
_What variables relate to food insecurity and how does this differ across neighborhoods?  What can we do about it?_

## Data Sources

1. Grocery Store

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Grocery_Store%20(2).csv

This data set contains data on the grocery stores in Baltimore City.  The street address, zipcode, city, and state columns are used in the code.  This data can be found [here](https://data.baltimorecity.gov/datasets/grocery-store?geometry=-76.870%2C39.262%2C-76.376%2C39.355) on the Baltimore Open Data website.  

2. Grocery List

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/grocerylist.csv

This data set contains the addresses, latitude, and longitude of the grocery stores in Baltimore.  It was made from the manipulated Grocery Store data set downloaded from the python code.  The latitude and longitude of each address were manually entered using [LatLong.net](https://www.latlong.net/convert-address-to-lat-long.html) and [gps-coordinates.net](https://www.gps-coordinates.net/).

3. Food Vendor Locations

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Food_Vendor_Locations.csv

This data set contains data on the street food vendors in Baltimore City.  The address, latitude, longitude, and items sold columns are used in the code.  The raw data can be found [here](https://data.baltimorecity.gov/datasets/food-vendor-locations-1) on the Baltimore Open Data website. 

4. Restaurants

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Restaurants.csv

This data sets contains data on the restaurants in Baltimore City.  The number of total restaurants was used in the bar graph.  The raw data can be found [here](https://data.baltimorecity.gov/datasets/restaurants?geometry=-77.115%2C39.193%2C-76.126%2C39.379) on the Baltimore Open Data website.  

5. Charm City Circulator Data Sets

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Charm%20City%20Circulator%20-%20Blue%20Line.csv

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Charm%20City%20Circulator%20-%20Green%20Line.csv

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Charm%20City%20Circulator%20-%20Orange%20Line.csv

https://github.com/shannonpowelson/Baltimore-food-desert-analysis/blob/main/Charm%20City%20Circulator%20-%20Purple%20Line.csv

These four data sets are for the four Charm City Circulator lines.  The addresses of the bus stops for each line were found on [Moovit](https://moovitapp.com/index/en/public_transit-lines-Washington_DCBaltimore-142-1196836) and entered manually into excel.  Using these addresses, the latitude and longitude were manually entered using [LatLong.net](https://www.latlong.net/convert-address-to-lat-long.html) and [gps-coordinates.net](https://www.gps-coordinates.net/).

6. Walk Score

https://github.com/vchen19/baltimore-food-insecurity/blob/main/Walk_Score.csv

This data set contains the walk score distribution in Baltimore City.  The data can be found [here](https://data.baltimorecity.gov/datasets/bniajfi::walk-score-community-statistical-area?geometry=-77.095%2C39.192%2C-76.146%2C39.378) on the Baltimore Open Data website.

7. Average Healthy Food Availability Index

https://github.com/vchen19/baltimore-food-insecurity/blob/main/Average_Healthy_Food_Availability_Index%20(1).csv

This data set contains information on the Average Healthy Food Availability Index in Baltimore City.  The data can be found [here](https://data.baltimorecity.gov/datasets/bniajfi::average-healthy-food-availability-index?geometry=-77.095%2C39.192%2C-76.146%2C39.378) on the Baltimore Open Data website.

8. Percent of Households with No Vehicles Available - Community Statistical Area

https://github.com/vchen19/baltimore-food-insecurity/blob/main/Percent_of_Households_with_No_Vehicles_Available%20(1).csv

This data set contains information on the households with no vehicles available in Baltimore City.  The data can be found [here](https://data.baltimorecity.gov/datasets/bniajfi::percent-of-households-with-no-vehicles-available-community-statistical-area?geometry=-77.095%2C39.192%2C-76.146%2C39.378) on the Baltimore Open Data website.

9. Percent of Residents - Black/African-American (Non-Hispanic) - Community Statistical Area

https://github.com/vchen19/baltimore-food-insecurity/blob/main/Percent_of_Residents_-_Black_African-American_(Non-Hispanic).csv

This data set contains information on the distribution of Black/African-American residents in Baltimore City.  The data can be found [here](https://data.baltimorecity.gov/datasets/bniajfi::percent-of-residents-black-african-american-non-hispanic-community-statistical-area?geometry=-77.095%2C39.192%2C-76.146%2C39.378) on the Baltimore Open Data website.  

10. Percent of Residents - White/Caucasion (Non-Hispanic) - Community Statistical Area

https://github.com/vchen19/baltimore-food-insecurity/blob/main/Percent_of_Residents_-_White_Caucasian_(Non-Hispanic).csv

This data set contains information on the distribution of White/Caucasion residents in Baltimore City.  The data can be found [here](https://data.baltimorecity.gov/datasets/bniajfi::percent-of-residents-white-caucasian-non-hispanic-community-statistical-area-1?geometry=-77.095%2C39.192%2C-76.146%2C39.378) on the Baltimore Open Data website.  

11. Fast Food Outlet Density per 1,000 Residents

https://github.com/vchen19/baltimore-food-insecurity/blob/main/Fast_Food_Outlet_Density_per_1%252C000_Residents%20(2).csv

This data set contains information on the Fast Food Outlet Density per 1,000 residents.  The data can be found [here](https://data.baltimorecity.gov/datasets/bniajfi::fast-food-outlet-density-per-1000-residents?geometry=-77.095%2C39.192%2C-76.146%2C39.378) on the Baltimore Open Data website.

## Data Analysis

### Geospatial Analysis for Targeted Solutions
In order to create solutions targeted specifically at neighborhoods in Baltimore City that are at the highest risk for being food deserts, geospatial analysis is used.

First we graph the number of locations of each food source in Baltimore City.  These main food sources are grocery stores, street food vendors, and restaurants.

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/foodsourcegraph.png)

Now we map the grocery stores and free public transportation routes in Baltimore City, Maryland. The free public transportation routes are the Charm City Circulator routes.  The grocery stores are labeled with the black map markers and Charm City Circulator routes are labeled with orange, green, purple, and blue map markers.

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/grocerymap.png)

We also investigated the street food vendor locations to see if street food vendors, which have a more mobile setup, have a more widespread distribution.  The street food vendors are labeled with the light blue map markers.  

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/streetfoodvendormap.png)

This map shows that many grocery stores are inaccessible.  Only the middle of Baltimore and the area around the Inner Harbor have free public transportation options.  Street food vendors are mostly concentrated around the Charm City Circulator routes and the inner harbor and therefore do not increase accessibility to food.  

We now take other factors into consideration in order to isolate and target the areas that are most at risk for being food deserts.  The following choropleth maps were used to find at risk areas and to create solutions.  We also used a map made in [Mapbox](https://www.mapbox.com/) that shows the grocery stores (in red), the street food vendors (in yellow), the restaurants (in dark blue), and the Charm City Circulator routes (in blue, green, purple, and orange). 

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/healthy_food.png)

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/no_vehicles_map.png)

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/walkscore.png)

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/fastfood_map.png)

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/black_map.png)

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/white_map.png)

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/food_and_transportation_map.png)

Street food vendors have a mobile set up and therefore could be a solution to the food desert problem.  We explored the items sold by the street food vendors.  

![alt text](https://github.com/vchen19/baltimore-food-insecurity/blob/main/StreetFoodVendorsBaltimore.png)

As shown in the graph, the food selection is unhealthy, so the current street food vendors would not be a solution to the food desert problem.  Healthier options would need to be brought in.  

## Summary
Overall, the data analysis shows that residents living in at risk areas lack accessibility to healthy food since food sources are not close and transportation is not available.  We recommend a three stage solution.  These stages include grocery deliveries, expanding free public transportation, and establishing permanent healthy food sources in at risk areas.
