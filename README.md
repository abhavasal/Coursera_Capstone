Capstone Project - The Battle of Neighborhoods

This file makes my contribution to the final Peer Reviewed Assignment for the Coursera Capstone Project for Applied Data Science Capstone. 


Part 1 -Problem Definition

At times we are in a dilemma whether to relocate to a city on getting a promotion or not. With relocation we have to look for accommodations in safer neighborhoods for our family and schools and other amenities for our family.
As my problem statement I explore the case of person working for XYZ Corp. On getting a promotion he has the option of relocating to either Boston or Chicago, as his team works from those locations. Shifting from Dallas, he must analyze which is the best option for him in terms of cost of living index, property rent index and affordability ratio etc.
Once the city is finalized, for temporarily accommodation  we aim at suggesting different Airbnb options available. Through parameters like neighborhood, property type, different amenities, the project will try aiming at predicting price of accommodations.
With his family moving in with him he needs to look for Residential Complexes for settling down. We will analyze the crime record for the year 2018 and look for safer neighborhoods in Chicago. We will explore the neighborhoods and look for areas with amenities like park, convenience stores, Bus station, Train station nearby. The project aims at suggesting neighborhoods for staying. With his children studying in Elementary and High School. He needs to find schools in his neighborhood.
The problem can recommend other people thinking of relocating and suggest them ways to explore the neighborhood and eventually settling down.


Part 2 - Describe the data 
1.	.In this section, I will describe the data used to solve the problem as described previously.
The website https://www.numbeo.com/ was scrapped to extract data about of cost of living index and property price index for all the major world cities. Rows corresponding to Boston and Chicago was filtered and analyzed visually. Using BeautifulSoup and Requests, the results the results were retrieved. 
2.	Data Chicago Airbnb listings data is downloaded from http://insideairbnb.com/get-the-data.html. The data behind the Inside Airbnb site is sourced from publicly available information from the Airbnb site. The file listings – provides detailed listings showing 96 attributes for each of the listings. Some of the attributes used in the analysis are  price (continuous), longitude), latitude (continuous), property_type (categorical), is_superhost (categorical), neighborhood , ratings (continuous) ,reviews are some of them.



3.	Chicago is divided into 77 community areas. Community areas are distinct from the more numerous neighborhoods in Chicago. Community areas often encompass groups of neighborhoods. Although many community areas contain more than one neighborhood, they may also share the same name, or parts of the name, of some of their individual neighborhoods.
Wikipedia site https://en.wikipedia.org/wiki/Community_areas_in_Chicago was used to extract names of Community Areas and neighborhoods with in those areas.
4.	We used open source Chicago Crime data from https://data.cityofchicago.org  to provide the user with crime data for the year 2018.
A record looks like this 
ID  11561837
Case Number   JC110056
Date   12/31/2018 11:59:00 PM
Block   013XX W 72ND ST
IUCR  1153
Primary Type   DECEPTIVE PRACTICE
Description FINANCIAL IDENTITY THEFT OVER $ 300
Location Description
Arrest
Domestic
Beat 0734
District 007
Ward     6
Community Area  67
FBI Code 11
X Coordinate   1168573
Y Coordinate     1857018
Year     2018
Updated On            01/17/2019 02:26:36 PM
Latitude 41.763181359
Longitude-87.657709477
Location
5.	We will Query the FourSqaure website www.foursquare.com to explore the neighborhood of Chicago Use the FourSquare API to look for Residential Complexes in finalized neighborhoods
Use the FourSquare API to search for schools in nearby neighborhood

The project aims at suggesting which city to shift to in terms of better quality of life and having less crime rate.
The study will help in identifying and recommending neighborhood seeing the needs of his family and crime rate in that neighborhood using the Foursquare API. 
For immediate relocation the project will also recommend Airbnb accommodations available in those neighborhood

url=’https://api.foursquare.com/v2/venues/explore?&client_id={}&client_secret={}&v={}&ll={},{}&radius={}&limit={}'.format(  CLIENT_ID, CLIENT_SECRET, VERSION,  neighborhood_latitude,     neighborhood_longitude,  radius,     LIMIT)
Send the GET request and examine the results
results = requests.get(url).json()

