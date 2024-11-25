In this folder, I will show projects completed in my courses at USC, like Programming for Data Science or Data Science at Scale.

## Geospatial Data Handling
Used: Postgres+PostGIS, SQL, KML, XML, and ArcGIS, PostgreSQL, MongoDB Atlas

These assignments are from my Database Systems course from Spring 2024. I was tasked to work with spatial data, collecting/generating my own spatial data, visualizing it, and generating queries on it.

### Task 1: Spatial Data of 13 locations Near Me: Convex Hull, NN, using Postgres+PostGIS, PostgreSQL 
Finding 13 locations, I was tasked to generate a KML file to import these 13 locations to Google Earth with placemarks. After this, using Postgres+PostGIS, I created a SQL DB inserting all my lat and longs as ST_GeomFromText points or as geom geometry objects. With this, I was tasked to generate two SQL queries to find the Convex hull of my data points and the 4 nearest neighbors of one specific location. The results were then added to the KML file as line segments or polygons to be shown on Google Earth.

NOTE: The code and images of the convex hull and NN will not be shown for safety purposes. 

### Task 2: Using Tommy Trojan, compute a Spirograph Curve and plot in ArcGIS.
I generated a Python code that would compute the Spirograph Cruve lat and longs based on the center lat and longs of Tommy Trojan. The code computes the x and y values in radians of the curve, converts them to kilometers per degree for the lat and longs, and outputs a KML file that will be used in ArcGIS.

![ArcGIS Spirograph Screen Shot](https://github.com/user-attachments/assets/bf788c4e-863c-4ddf-9be2-f5803e44d1c0)

### Task 3: NoSQL, JSON data, MongoDB Atlas
Instead of having an XML/KML file, this time, we used our lat and longs in a JSON file and inserted it into a collection in MongoDB Atlas. We inserted our data as an array of objects, each object with information about the location. Once our data was added, we generated queries in MongoDB Atlas, such as creating a bounding box of our coordinates or specifying a tringle in our coordinates. I used $geowithin, $box, and $polygon for these queries.
I also used the coordinates of the National Parks and generated a query in MongoDB Atlas to only show the western half locations using the bounding box as well.

![Q6_National Parks](https://github.com/user-attachments/assets/0ff35339-6a43-4f8b-9699-cad7f485c771)


## Analysis of Meteorite Landings
This final course project required me to analyze a data set and generate visualizations to do analysis. I leveraged python libraries such as matplotlib, matplotlib.pypplot, seaborn, and plotly.express!

Course: Introduction to Programming for Data Informatics

Grade: A

* Analyzed a CSV file containing 46,000 Meteorite landings data up until 2016
* Coded in Python, leveraging pandas and other libraries to clean, create visualizations, and assess data

![Mass Per Meteorite ID](https://github.com/epenaloz/My-Projects-Description/assets/118321814/8527d5a8-35fb-4aa6-addf-6e0fec571b82)

![Geolocation Map](https://github.com/epenaloz/My-Projects-Description/assets/118321814/94ad13ec-0014-4f67-97e3-f254cd9b1533)


## Pixstory Analysis
I worked in a team to analyze a dataset consisting of 95k rows and 27 columns, in which our team added 17 of those columns from outside sources to gather more insights about the data.
Pixstory is a social media app whose mission is to maintain a "clean" and "truthful" platform for its users. 
Our team used Python to analyze users' location, language detection using Tika Lang Detection, Language Translation, grouping similar images together, Hate speech and term analysis, events, popular topics, and toxicity within the platform. Most of my work was determining hate speech/hate terms within the social media narratives. I generated a visualization using D3!

Course: Data Science at Scale

Grade: A

![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/9706313d-c5f2-4186-acde-e9814feddcb3)


![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/58e93f02-1e77-401c-bbf7-5c8325c62c50)


## Analysis of E-Commerce Data
* Analyzed data from a CSV file containing 190,000 lines of E-commerce data imported from Kaggle
* Coded in Python to retrieve a total number of unique items, customers, and countries. Obtained the average number of
unique items per invoice, average transaction per invoice, and total number of purchases for each item

## Analysis of Qualtrics Comments Per Provider
In my current role as a Data Management Specialist, I created a code that would gather the comments from Qualtrics, look for specific providers within the comments, and generate a PDF as a result. This process used to be done manually however, this code saved us a
a lot of time!

![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/b489bc79-89bd-4d65-9ccf-bb06839536a1)
![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/ac80c71e-b555-4f03-b143-91fc69361b0c)


