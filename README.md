# The-battle-of-Neighborhoods

I have conducted This project towards completion of IBM data science professional certification.  

One of the objectives of the assignment was using FourSquare API for extracting data and clustering the data to meet the goals of the project.  

Towards accomplishing the said purpose, I have come up with the problem statement that tries to contribute towards the marketing problems faced by cooperative dairy processing units in Maharashtra. The question that can be asked using the FourSquare location data is- which areas in Pune city have high demand for processed milk for food businesses?  

This is just a minimal approach towards the broad problem.

## Introduction: 

### Problem Statement:
To plan the target market areas for cooperative dairy processing units in Maharashtra, the units need to understand the high demand pockets of commercial businesses like Cafes. Such understanding will help to plan modifications at processing and storage levels along with opening of outlets of the milk processing units at target neighborhoods for retail sales and branding.

### Background:
India is the world’s largest milk producer, accounting for ***more than 21% share*** in global milk production (FAO statistical yearbook 2010). The dairy sector in the India has shown remarkable development in the past decade. Dairy cooperatives account for the major share of the processed liquid milk marketed in India and **Maharashtra contributes the 
_highest number of cooperatives_ performing milk business in the processing sector. **

Total production of milk in Maharashtra is around 10,153 (thousand tons) for the year 2015-16. In Maharashtra there are 14,921 numbers of cooperative dairy societies and 85 dairy unions working in the state (Economic survey of Maharashtra, 2016-17).

However these cooperative dairy processing units in Maharashtra face ***constraints at procurement, processing and marketing level*** which is studied in one research paper. It was observed that at the marketing level, these units advertised their product only at local level. A very few had their own out lets at various places of Maharashtra. Majority of them did not have a wide distribution network. In turn processed milk suppliers **failed to do branding and successful retail sales.**

To obtain the sustain consumer market in food industry, cooperative units need to setup storage units and branded retail shops at **hot target pockets with high demand**. Majority of such demand in urban areas come from food outlets like Cafes. 

*This study will be the small part in this research where we will look for the clusters of high milk demand pockets like Cafes in neighbourhoods of Pune city, one of the high populous urban areas in Maharashtra. The question that can be asked using the FourSquare location data is- which areas in Pune city have high demand for processed milk for food businesses?*

## Data :

For this project we will be using two datasets and merge them to obtain all possible data on available Cafes in Pune city.
1.	Open-source dataset on restaurants of Pune on *Zomato* available on Kaggle : 
	- The data is scraped from Zomato site in one step using selenium, python and beautifulsoup. 
	- Data has usability index of 9.1 and has listing until 1 Dec., 2019.
	- The data contains names of restaurants, ratings, cuisines served, category and location details among other details.
2.	*FourSquare API* :
	- Using this API we will get the listings of venues in neighborhoods of Pune city
	- The data will contain names and categories of venues along with location information
  
## Methodology:
1.	Obtaining data: Datasets were obtained from respective sites mentioned above. The data obtained from FourSquare API was converted from JSON to pandas dataframe for further use. 
2.	Data cleaning and processing: 
	-a.	The zomato dataset was explored for features, their relevance and data types. The unnecessary features were dropped. 
	-b.	All the unique localities were extracted from zomato dataset and the coordinates were obtained using geopy.
	-c.	The list of cafes with their coordinates were obtained using FourSquare API. ‘search’ endpoint was used with ‘café’ as search query. Cafes were searched around Pune localities obtained earlier.
	-d.	Zomato and FourSquare data was merged for the common cafes and their details like ratings and number of voters.
	-e.	The NaN values were dealt accordingly by dropping data or replacing with mean values.
3.	Data visualization: The data was merged and visualized using folium on map.
4.	Clustering of Cafes: The neighbourhoods in Pune was clustered using k-means method and the clusters were analysed.
5.	Visualization of clusters on map using folium.
6. 	Analysis of clusters

## Results:

Total 63 cafes could be obtained from FourSquare data of which cutomer ratings and number of votes were available from Zomato-Pune data.
Six clusters of cafes in Pune were obtained using K-means clustering. The hot pocket for cafes consisted of 22, 19,9,8,4 and 1 cafes respectively. The clustered differ from each other in number of cafes, localities, and the average customer ratings.
![Six clusters with the distribution of customer ratings](https://github.com/sayaliba01/The-battle-of-Neighborhoods/blob/main/image1.jpg?raw=true)
The visualization on map shows the hot pockets of location for cafes in Pune.
![Map](https://github.com/sayaliba01/The-battle-of-Neighborhoods/blob/main/image2.jpg?raw=true)

## Discussion:

The clusters help to understand the distribution of cafes in Pune. When the clusters are analysed for the ratings and customer votings, it can be observed that the one cluster with highest number of cafes have medium to high ratings with high number of voters indicating the hot pocket which can serve as good strategic location for opening of retail shops and the branding and marketing of milk by cooperative dairy processing units in Maharashtra. The cluster includes the cafes mostly from high bustling localities in Pune like Senapati Bapat Road, Fergusson College Road, Kothrud, part of Aundh, Shivaji Nagar.
The other clusters have few cafes and the ratings are low to medium or medium to high but include less number of cafes.

## Conclusion:

K-Means clustering successfully clusters cafes in Pune according to location, ratings and customers. Still this project faces some limitations like only 63 Cafes were identified from merged dataset. More data can help better to plan strategies for the cause of the project.
This project forms small part of big project which will facilitate the understanding of market and demands for the processed, packaged milk in food industry like Cafes.
However, this project successfully derives the hot consumer pocket in Pune in terms of Cafes where the cooperative dairy processing units in Maharashtra can set up their retail shops and organize promotional events for sell on bulk and to attract businesses for future long term contracts.


## References:
1. Swarnakar, J.L. & Swarnakar, V.S.. (2019). Constraints in Procurement, Processing and Marketing of Milk and Milk Products –A Comparative Study with Special Emphasis to Co-Operative Dairy Processing Units of Karnataka and Maharashtra States. Asian Journal of Dairy and Food Research. 38. 10.18805/ajdfr.DR-1494. 
2. Samadhan, Khamkar & Bobade, Anita. (2016). Conceptual Review of Dairy Co-operatives in India, as an ideal economic model: The case of Dairy Co-operative from Western Maharashtra Track 31. In Proceedings: 9th Euromed Conference on Innovation, Entrepreneurship and Digital Ecosystems, Volume: ISBN: 978-9963-711-43-7
