# The-battle-of-Neighborhoods

## Introduction: 

### Problem Statement:
To plan the target market areas for cooperative dairy processing units in Maharashtra, the units need to understand the high demand pockets of commercial businesses like Cafes. Such understanding will help to plan modifications at processing and storage levels along with opening of outlets of the milk processing units at target neighborhoods for retail sales and branding.

### Background:
India is the world’s largest milk producer, accounting for more than 21% share in global milk production (FAO statistical yearbook 2010). The dairy sector in the India has shown remarkable development in the past decade. Dairy cooperatives account for the major share of the processed liquid milk marketed in India and Maharashtra contributes the highest number of cooperatives performing milk business in the processing sector. 

Total production of milk in Maharashtra is around 10,153 (thousand tons) for the year 2015-16. In Maharashtra there are 14,921 numbers of cooperative dairy societies and 85 dairy unions working in the state (Economic survey of Maharashtra, 2016-17).

However these cooperative dairy processing units in Maharashtra face constraints at procurement, processing and marketing level which is studied in one research paper. It was observed that at the marketing level, these units advertised their product only at local level. A very few had their own out lets at various places of Maharashtra. Majority of them did not have a wide distribution network. In turn processed milk suppliers failed to do branding and successful retail sales.

To obtain the sustain consumer market in food industry, cooperative units need to setup storage units and branded retail shops at hot target pockets with high demand. Majority of such demand in urban areas come from food outlets like Cafes. 

This study will be the small part in this research where we will look for the clusters of high milk demand pockets like Cafes in neighbourhoods of Pune city, one of the high populous urban areas in Maharashtra. The question that can be asked using the FourSquare location data is- which areas in Pune city have high demand for processed milk for food businesses?

## Data :

### Datasets:
For this project we will be using two datasets and merge them to obtain all possible data on available Cafes in Pune city.
1.	Open-source dataset on restaurants of Pune on Zomato available on Kaggle : 
a.	The data is scraped from Zomato site in one step using selenium, python and beautifulsoup. 
b.	Data has usability index of 9.1 and has listing until 1 Dec., 2019.
c.	The data contains names of restaurants, ratings, cuisines served, category and location details among other details.
2.	FourSquare API :
a.	Using this API we will get the listings of venues in neighborhoods of Pune city
b.	The data will contain names and categories of venues along with location information
  
### Approach:
1.	Obtaining data: Datasets will be obtained from respective sites mentioned above. The data obtained from FourSquare API will be converted from JSON to pandas dataframe for further use. 
2.	Data cleaning and processing: 
a.	The relevant data on Cafes only will be filtered out. 
b.	The columns will be analysed for the relevant features and unnecessary features will be dropped from the data.
c.	The one-hot encoding method will be used to convert categorical data to numerical data. 
d.	The NaN values will be dealt accordingly by dropping data or replacing with mean values.
e.	Incorporation of missing latitude and longitude values using Nominatim from geopy package.
3.	Data visualization: The data will be merged and visualized using folium on map.
4.	K-means clustering: The neighbourhoods in Pune will be clustered using k-means method and will be analysed.
5.	Visualization of clusters on map using folium.

## References:
1. Swarnakar, J.L. & Swarnakar, V.S.. (2019). Constraints in Procurement, Processing and Marketing of Milk and Milk Products –A Comparative Study with Special Emphasis to Co-Operative Dairy Processing Units of Karnataka and Maharashtra States. Asian Journal of Dairy and Food Research. 38. 10.18805/ajdfr.DR-1494. 
2. Samadhan, Khamkar & Bobade, Anita. (2016). Conceptual Review of Dairy Co-operatives in India, as an ideal economic model: The case of Dairy Co-operative from Western Maharashtra Track 31. In Proceedings: 9th Euromed Conference on Innovation, Entrepreneurship and Digital Ecosystems, Volume: ISBN: 978-9963-711-43-7
